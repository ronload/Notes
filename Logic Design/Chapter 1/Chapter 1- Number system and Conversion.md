# Chapter 1: Number system and Conversion

## Analog VS Digital Signal

### What is signal?
1. A transmission of data.
2. We  interact with signal with form music,power lines(電線), telephone.
3. This means the use of antennas(天線), satellites(衛星), and of course wires(電線).
4. These signals can be transferred in the form of "Analog" and "Digital".

#### What is analog?
>The process of taking an audio or video signal(in most cases, the human voice) and translating it into elctronic pulse.

#### What is digital 
>Breaking signals into binary format where the audio or video data is represented by a series of "1"s and "0"s.

## Analog Signal
1. First used in 1800's, they were used in conjunction with copper telephone lines to transmit conversations.
2. This involved using 2 conductors for each lines, sent and reseive.
3. But increasing number of people started using telephone making analog too expensive and troublesome to maintain.
4. Due to the way analog signals work, we found that it take too much noise:
	1. Factors: air condition unit, fluorescent light, magnetic fields.
	2. There are methods of separating or "filtering noise from analog signals. However, they are not accurate.
	3. Noise sometimes called "distortion" or "clipping".

## Analog to Digital 
+ Step 1. Analog sensor in the cell phone pick up your voice.
+ Step 2. An **analog to digital** converter chip converts your voice.
+ Step 3. The **DSP** compresses the digital signals and removes noise.
+ Step 4. An **digital to analog** converter chip in listener's cellphone changes the digital signals back to analog voice.
+ Step 5. Your voice exits the cellphone through the speaker.

## Digital Signal

1. Are **discrete waveforms**.
2. The signals takes 2 basic form: on/1, off/2
3. The signals is very uniform in composition.

## Analog VS Digital

Here we see the main advantage of digital over analog, Since the dignal is very uniform, **noise has not severely altered its shape or amplitude**. The digitals signals shows a far less change to the actual waveform than the previous analog signal.

1. Digitals systems work with discrete quantities, in many cases they can be designed so that for a given input, the output is exactly corret.
2. Ex. If we multiply two 5-digit numbers using a digital multiplier, the 10-digits product will be correct in all 10-digits. On the other hand, output of an analog multiplier will have an error ranging from a fraction of one percent to a few percent depending on the accuracy of the component used in construction of the multiplier.
3. If we need 20-digit component, we can redesign in digital, but in analog it is due to the accuracy of the component, it is not possible.

## Digital System and Switching Circuits

1. Appication of digital system: computation, data processing, control system communications , measurements

2. Digital systems are capable of greater accuracy and reliability than analog system, many tasks formally done by analog systems are now being performed by digital systems.
3. In a digital system, the physical quantities or signals can assume only be descrete values, while in analog systems the phphysical quantities may be very continuously over a specified value.

> Digital systems may be constrained to take only two values such as 0 volts and 5 volts, while the output voltage from an analog system might be allowed to assume any value in the range of -10 to +10 volts.

## Adventages and Disadventages of Digital Systems

### Adventages:

1. Generally easier to design.
2. Information storage is easier.
3. Accuracy and precision are easier to maintain throughout the system.
4. Operations can be programmed.
5. Digital circuits are less affected by noise.
6. More digital circuitry can be fabricated on IC chips.

### Real Problems or Disadvantages

1. The real word is analog.
2. Processing digitized signals takes time.

## Design Digital System

1. The design of digital systems may be divided roughly into three parts:

   1. System design

   2. Logic design

   3. Circuit design

2. What is system design?

   Breaking the overall system into subsystems and specifying the characteristics of each subsystems.

3. What is logic design?

   Logic design involves determinijng how to interconnect basic **logical building** blocks to perform a specific function.

4. What is circuit design?

   Circuit design involves specifying the interconnection of specific components such as **resistors, diodes** and **transistors** to form a gate, flip flop, or other logic building block.

### Switching Circuits

1. A switching circuit have one or more **inputs** and one or more **outputs** which take on discrete values.
2. Many digital system's subsystems take the form of a switching circuit.

<img src="figure 1.1.png">

### Types of Switching Circuits: Combinational, Sequential

#### Combinational circuit: 

The output value depend only on the present value of the input and **not** on the past values.

#### Sequential circuit

The outputs depends on **both** the **present** and **past** input values. THe sequential circuit is said **have memory** because it must **remember** something about the past sequence of inputs, while a combinational circuit has no memory.

### Combinational Circuits

1. The basic building blocks used to construct combinational circuits are **logic gates**.
2. The logic designers must determine how to interconnect these gates in order to convert the citcuit input signals into the desited output signals.
3. The relationship betweem these input and output signals can be described mathematically using **Bolean Algebra** and show how they can be used to  describe the behavior of circuits of **logic gates**.
4. We will be using hardware desceiptional languague such as *VHDL* or *Verilog*.

## Number Systems

### 3 Systems for representing negtive numbers in binary

1. Sign and Magnitude: Most significant bit is the sign.

   Ex. $-5_{10} = 1101_2$

2. 1's Complement: $\overline{N} = (2^2-1)-N$

   Ex: $-5_{10} = (2^4-1)-5 = 10_{10} = 1010_2$

3. 2's Complement: $N^* = 2^n-N$

   Ex. $-5_{10} = 2^4-5 = 11_{10} = 1010_2$

> n : word length

### 1's Complement

1. Example: 5 - 6

   $5 - 6 = 5 + (-6) = 0101_2 + 1001_2 = 1100_2 = -1$

2. Example: -5 + 6

   $(-5) + 6 = 1010_2 + 0110_2 = (1)0000_2 \rArr 0001$ (end-around carry)

3. Example: (-5) + (-6)

   $(-5) + (-6) = 1010_2 + 1001_2 = (1)0011 \rArr 0100$ (end-around carry)

   > Wrong answer because of the overflow

### 2's Complement

1. Example: 3 + 4

   $3 + 4  = 0011_2 + 0100_2 = 0111_2 = 7$

2. Example: 5 + 6

   $5 + 6 = 0101_2 + 0110_2 = 1011_2$

   > Wrong answer because of overflow (+11 requires 5 bits including the sign)

3. Example: (-5) + (-6)

   $(-5) + (-6) = 1011_2 + 1010_2 = (1)0101$

   > Wrong answer because of the overflow (-11 requires 5 bits including the sign)

**當計算結果超過$2^{n-1}$時，會出現溢位錯誤**

<img src="table 1-1.png" width="80%">
