# csc347-ens211-lab-11-sequence-detector-solved
**TO GET THIS SOLUTION VISIT:** [CSC347-ENS211 Lab 11-Sequence Detector Solved](https://www.ankitcodinghub.com/product/csc347-ens211-lab-11-sequence-detector-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;94130&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;2&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (2 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CSC347-ENS211 Lab 11-Sequence Detector Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (2 votes)    </div>
    </div>
&nbsp;

<strong>Objective </strong>

The objective of this lab is to design a synchronous sequence detector that detects a bit-pattern “110”.

We want to design a circuit which detects (110) sequences in a string of bits coming through an input line (i.e., the input is a serial bit stream). Once the (110) sequence is detected, output becomes (1), otherwise it stays as (0). A sample input and output bit streams (sequence) are given below. First bit coming to the input is the one shown on the far left.

Example Input bit stream: &nbsp;&nbsp;&nbsp;&nbsp; x=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0100110010100010110100

Example Output bit stream: &nbsp; y=&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0000010000000000010000

<table>
<tbody>
<tr>
<td width="27">
<table width="100%">
<tbody>
<tr>
<td>1</td>
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
The diagram of the sequence detector is shown below. Beside the clock, input x and output y, it has a reset input to force the detector into the initial state (“00”). The circuit also output the present state.

<table>
<tbody>
<tr>
<td width="27">
<table width="100%">
<tbody>
<tr>
<td>1</td>
</tr>
</tbody>
</table>
</td>
</tr>
</tbody>
</table>
<strong>Lab Procedure</strong>

&nbsp;

<ol>
<li>Derive the State Diagram for a <strong>Moore</strong> “110” sequence detector:</li>
</ol>
&nbsp;

<ol start="2">
<li>Write a Verilog code to implement the sequence detector in behavioral level</li>
</ol>
&nbsp;

module sequence_detector(clock, reset, x, y, state);

<em>// input</em>

input clock, reset, x;

<em>// output</em>

output y;

output [1:0] state; <em>// state is 2-bit</em>

reg [1:0] state;

&nbsp;

always @( posedge clock, posedge reset ) <em>// state machine</em>

if (reset)

state &lt;= 2’b00; <em>// reset state</em>

else

case (state)

2’b00: if(x)state &lt;= 2’b01; &nbsp; else state &lt;= 2’b00;

2’b01: if(x)state &lt;= 2’b10; &nbsp; else state &lt;= 2’b00;

2’b10: if(x)state &lt;= 2’b10; &nbsp; else state &lt;= 2’b11;

2’b11: if(x)state &lt;= 2’b01; &nbsp; else state &lt;= 2’b00;

endcase

&nbsp;

<em>// output y at state “11”</em>

assign &nbsp;y = state[1] &amp; state[0]; <em>// state[1] is the MSB</em>

endmodule

&nbsp;

&nbsp;

&nbsp;

<ol start="3">
<li>On the EDAplayground.com, create a Verilog testbench to test your sequence detector and perform the simulation to check if the results are correct. You should generate the input stimuli (x, reset) as shown in the below timing diagram and produce the corresponding outputs (y, state).</li>
</ol>
<strong>&nbsp; </strong>module test;

reg clock, x, reset;

wire y;

wire [1:0] state;

&nbsp;

<em>// instantiate the uut</em>

sequence_detector uut(clock, reset, x, y, state);

&nbsp;

<em>//generating the clock signal</em>

initial

begin

clock = 0; <em>// clock starts low</em>

forever #5 clock = ~clock; <em>// toggle clock</em>

#200 $finish; <em>// stop simulation after 200 clock cycles</em>

end

&nbsp;

initial

begin

$dumpfile(“dump.vcd”); $dumpvars(1,test);

<em>// monitor the state, x, and y signals</em>

$monitor(“state = %b x = %b y = %b “, state,x,y);

&nbsp;

<em>// Initalize inputs</em>

&nbsp;

x = 0; reset = 1;

&nbsp;

#13 &nbsp;reset = 0; <em>// hold reset low for 13 clock cycles</em>

#10 &nbsp; x = 1; <em>// set x high for 10 clock cycles</em>

#10 &nbsp; x = 0; <em>// set x low for 10 clock cycles</em>

#10 &nbsp; x = 1;

#10 &nbsp; x = 1;

#10 &nbsp; x = 0;

#10 &nbsp; x = 1;

#10 &nbsp; x = 0;

#10 &nbsp; x = 0;

#10 &nbsp; x = 1;

#10 &nbsp; x = 1;

#10 &nbsp; x = 1;

#10 &nbsp; x = 0;

#10 &nbsp; x = 0;

#10 $finish; &nbsp;<em>// stop simulation after 200 clock cycles &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;</em>

end

endmodule

&nbsp;

&nbsp;

<strong>Homework</strong>: design a FSM machine for detecting sequence “001” by deriving a state diagram and implement it using Verilog.

&nbsp;

<strong><u>Submission Instructions:</u></strong>

<u>Lab work submission</u>

<ol>
<li>Take a screenshot of your wavefroms.</li>
<li>Add the following information as comments to the beginning of your code. Make sure to click the “Save” button to save your project, then take a screenshot of your code.</li>
</ol>
// Author:&nbsp;&nbsp;&nbsp; Name

// Lab 11:&nbsp; put the title here

// Link to your project

&nbsp;

<ol start="3">
<li>Copy the link of your design from the address bar of the browser.</li>
<li>On the Blackboard, click on Lab 11. Attach the screenshot from the first two steps and paste the link from Step 3 into the Comments area, then click the “Submit” button.</li>
</ol>
<u>&nbsp;</u>

<u>Lab report submission</u>

<ol start="5">
<li>Lab report is needed for this lab. Please follow the guidelines and sample report on the Blackboard when you are writing your lab reports. Click on <strong>Lab 11 Report Submission</strong> to submit your report. It is due one week after the lab is done.1</li>
</ol>
