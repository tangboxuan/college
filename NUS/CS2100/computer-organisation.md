    github.com/tangboxuan

## Number Systems

|System|Value|-x|Negation|Addition|Overflow
|:---:|:---:|:---:|:---:|:---:|:---:
|Sign & Magnitude|||Invert first bit|
|1s Complement|+ve: same as 2s<br>-ve: 2s + 1|2^n - x - 1|Invert all bits|If MSB carry out: +=1|Result opposite sign of A and B|
|2s Complement|if x[i]==1: += 2^i<br>except 1st num: minus|2^n - x|Invert all bits + 1|Ignore MSB carry out|MSB carry in != MSB carry out<br>Result opposite sign of A and B|
|Excess-n|x-n
|IEEE 754|(Sign) (1.Mantissa) x 2^Exponent||Invert first bit|1: Sign<br>8: Ex-127 Exp|---<br>23: Mantissa

|System|-2|-1|0|1|2
|:---:|:---:|:---:|:---:|:---:|:---:
|Sign & Magnitude|10000010|10000001|00000000|00000001|00000010
|1s Complement|11111101|11111110|0000/1111|00000001|00000010
|2s Complement|11111110|11111111|00000000|00000001|00000010
|Excess-127|01111101|01111110|01111111|10000000|10000001|

## MIPS


|Operation| RR1| RR2| WR| WD| Opr1| Opr2| Address| Write Data|
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:
|lw $a, x($b)|	$b|	$a|	$a|	Mem([$b] +x)| [$b]|	x|	[$b] + x	|[$a]|
|beq $a,$b, immd|	$a|	$b|	$b|	? |	[$a]|	[$b]|	[$a] - [$b]|	[$b]|
|sub $a, $b, $c|	$b|	$c|	$a|	[$b] – [$c]|	[$b]|	[$c]|	[$b] – [$c]|	[$c]|
|addi $a, $b, immd|	$b|	$a|	$a| [$b] + immd| [$b]| immd| [$b]	+ immd| [$a]						

<div style="page-break-after: always;"></div>

![MIPS](images/mips.jpg)

<div style="page-break-after: always;"></div>

![Control](images/control.png)
![Datapath](images/pipeline.png)

<div style="page-break-after: always;"></div>

![Add: Chong Wen Hao](images/dp_add.png)
![BEQ: Chong Wen Hao](images/dp_beq.png)
![LW: Chong Wen Hao](images/dp_lw.png)
![SW: Chong Wen Hao](images/dp_sw.png)

<div style="page-break-after: always;"></div>

![ALUcontrol](images/ALUcontrol.png)
![ALU](images/ALU.png)

<table><tr><td>

|Dependency|Solution|Inst|Stall|
|:---:|:---:|:---:|:---:|
|Data|None|add|2|
|Data|None|lw|2|
|Data|Fwd|add|0|
|Data|Fwd|lw|1|
|Control|None|ALL|3|

</td><td>

|Dependency|Solution|Inst|Stall|
|:---:|:---:|:---:|:---:|
|Control|Early||1|
|Control|Early|add|2|
|Control|Early|lw|3|
|Control|Predict|YES|0|
|Control|Delay|?|0|

</td></tr></table>

<div style="page-break-after: always;"></div>

## Boolean Algebra
<img src="images/boolean_law.png" width="80%">
<img src="images/boolean_theorem.png" width="90%">

<table><tr><td>

<img src="images/minterm_maxterm.png" width="800px">

</td><td>

**Duality**: If the AND/OR operators and 0/1 identity elements are interchanged, it remainds valid  
x+1 = 1 -> x.0 = 0
</td></tr></table>
<div style="page-break-after: always;"></div>

## Logic Circuits   
<table><tr><td>

![NAND Logic](images/nand.png)

</td><td>

![NOR Logic](images/nor.png)

</td><td>

SOP
1. AND-OR
1. NAND-NAND

POS
1. OR-AND
1. NOR-NOR

</td></tr></table>
<table><tr><td>

![K2 Map](images/k2.png)

</td><td>

![K3 Map](images/k3.png)

</td><td>

![K4 Map](images/k4.png)

</td></tr></table>

![Half Adder](images/half_adder.png)
![Full Adder](images/full_adder.png)
![Magnitude Comparator](images/magnitude_comparator.png)
<div style="page-break-after: always;"></div>

## Functions using MSI
### Demultiplexers are similar to a decoder (select) with enable (data)  
### Multiplexers are similar to a decoder (select) added with 2^n input lines (input)  
![Decode Functions](images/decode_functions.png)
![Mux Functions](images/mux_functions.png)

<div style="page-break-after: always;"></div>

## Sequential Logic
![Flip Flop Characteristics Table](images/flip_flop_table.png)
![Flip Flop Excitation Table](images/excitation_table.png)
<div style="page-break-after: always;"></div>

## Cache
![Write Policy](images/write_cache.png)
![Direct Mapped Cache](images/direct_cache.png)
![Set Associative Cache](images/set_cache.png)
![Fully Associative Cache](images/full_cache.png)

<table><tr><td>

|Miss|Description|
|:---:|:---:|
|Compulsory|First access to a block
|Conflict|Block has been replaced in cache
|Capacity|Cache cannot contain all blocks

</td><td>

|Replacement Policy|
|:---:|
|Least Recently Used
|First In First Out
|Random Replacement
|Least Frequently Used

</td></tr></table>
<div style="page-break-after: always;"></div>

## Links

[IEEE 754 to Decimal](https://babbage.cs.qc.cuny.edu/IEEE-754.old/32bit.html)  
[Decimal to IEEE 754](https://www.ultimatesolver.com/en/ieee-754)  
[Hexadecimal-Binary-Decimal](https://www.rapidtables.com/convert/number/binary-to-hex.html)  
[XOR](http://xor.pw/#)  
[Bitwise Calculator](https://miniwebtool.com/bitwise-calculator/)  
[MIPS to Hexadecimal](https://www.eg.bucknell.edu/~csci320/mips_web/)  