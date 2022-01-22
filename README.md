# Computer-Architecture

- mid 3/3 cache
- final 5/12  pipline


- 重要!!!!! TA review session alexander !!!!!!


- computer architecture CAS room 229 Thursday

## first week  1/20

text book  1.2

eight great ideas in computer architecture

this 8 great ideas that computer architectures have been invented in the last 60 years of computer design:

1. Design for Moore's Law:
- the one constant for computer designers is  rapid change, which is driven largely by Moore's Law.
- as computer designs can take years, the resources available per chip can esaily double or qudruple between the start and finish of the project.
- computer architects must anticipate where the technology will be when the design finishes rather than design for where it starts.
- we use an "up and to the right" Moore's Las graph to represent designing for rapid change.

2. Use abstraction to simplify design:
- A major productivity technuque for hardware and software is to use abstractions to represne tht design at different levels of representation;
- lower-level details are hiddento offer a simpler model at higher levels.
3. Make the common case fast:
- making the common case fast will tend to enheance performance better than optimizing the rare case.
4. Performance via parallelism
- computer architects have offered designs that get more performance by performing operatins  in parallel.
5. Performance via pipelining
- memory need to b
6. Performance via Prediction
7.  Hierarchy of Memories
8. Dependability via redundancy


## 2.4 Signed and Unsigned Numbers

### base 2 numbers (binary number)

- First, let's review how a computer represents numbers.
- Humans are taught to think in base 10, but numbers may be represneted in any base.
  - for example, 123 base 10 = 1111011 base 2.

- Numbers are kept in computer hardware as a series of **high and low electronic signals**,
- and so they are considered base 2 numbers.
- **(base 10 numbers are called decimal numbers , base 2 numbers are called binary numbers.)**

- A single digit of a binary number is thus the "atom" of computing, since all information is composed of binary digits or bits.
- This fundamental building block can be one of 2 values,
- which can be thought of as several alternatives:
 - high or low
 - on or off
 - true or false
 - 1 or 0

- Generalizing the point, in any number base, the value of ith digit d is 
  - d x Base i
  - where i starts at 0 and increases from right to left.
  - THis representatin leads to an obvious way to number the bits in the word:
    - simply use the power of the base for that bit.
    - we subscript decimal numbers with ten and binary numbers with two
    - for example 
      - 1011two
      - represents:
      - (1x2^3) + (0x2^2) + (1x2^1) + (1x2^0)ten
      -  = 8 + 0 +2 +1
      -  = 11
 
 - we nuber the bits 0,1,2,3,4,5...31(32 bits wide) from right to left in a word.
 - The drawing below shows the numbering of bits with a MIPS word and the placement of the number 1011 two: 

### least significant bit(leftmost) & most significant bit(right most)
- Since words are drawn vertically as well as horizontally, 
- leftmost and rightmost may be unclear.
  - Hence, the pharse least significant bit is used to refer to the right most bit (bit 0 above)
  - and most significant bit to the leftmost bit (bit 31).

- The MIPS word is 32 bits long, so we can represent **2^32 different 32-bit patterns**.
- it is natural to let these combination represent the numbers from 0 to 2^32-1 (4,294,967,295 ten):


- That is, 32-bit binary numbers can be represented in terms of the bit value times a power of 2
- (here xi means the ith bit of x):
   - (x31 x 2^31) + (x30 x 2^30) + (x29 x 2^29) + ... + (x1 x 2^1) + (x0 x 2^0)
   - for reasons we will shortly see,
   - these positive numbers are called unsigned numbers. 

- Keep in mind thay the binary bit patterns above are simply representatives of numbers.
- Numbers really have an infinite number of digits, with almost all being 0 except for a few of the rightmost digits.
- We just don't normally show leading 0s.

### overflow
- Hardware can be designed to add, substract, multiply, and divide these binary bit patterns.
- if the number that is the proper result of such operations cannot be represented by these rightmost hardware bits,
- overflow is said to have occured.
- It's up to the programming language, the operating system, and the program to determine what to do if overflow occurs.

### sign and magnitude
- Computer programs calculate bothe positive and negative numbers,
- so we need a representation that distinguishes the positive from the negative.
- The most obvious solution is to add a seperate sign, which conveniently can be represneted in a single bit,
- the name for this representation is sign and magnitude.

- sign and magnitude represnetation has several shortcomings.
  - 1. it's not obvious where to put the sign bit.
  - 2. adders for sign and magnitude may need an extra step to set the sign because we can't know in advance what the proper sign will be.
  - 3. a seperative sign bit means that sign and magnitude has both a positive and negative zero, which can lead to problems for inattentive programmers.

- In the search for a more attractive alternative, the question arose as to what would be the result for unsigned numbers if we tried to subtract a large number from small one.
- The answer is that it would try to borrow from a string of leading 0s, so the result would have a string of leading 1s.

###  two's complement :
- Given that there was not obvius better alternative, the final solution was to pick the representation that made the hardware simple:
  - **leading 0s means positive, and leading 1s mean negative.**
  - This convention for representing signed binary numbers is called two's complement representation:  


- The positive half of the numbers, from 0 to 2,147,483,647 (2^31-1),
- use the sam representation as before.
- The following bit pattern(1000...000 two) represents the most negative number -2,147,483,647 ten(1000...0001 two) down to -1ten(1111...1111two).

- Two's complemenmt does have one negative number, -2,147,483,648 ten,
-  that has no corresponding positive number.
-  Such imbalance was also a worry to the inattentive programmer,
-  but sign and magnutude had problems for both the programmer and the hardward designer.
-  Consequently, every computer today used two's complement binary representatios for signed numbers.

### A sign bit
- Two's complement representation has the advantage that **all negative numbers have a 1 in the most significant bit.**
- hardware needs to test only this bit to see if a number is positive or negative
- (with the number 0 considered positive).
-  by recognizing the role of the sign bit, 
-  we can represent positive and negative 32-bit numbers in terms of the bit value times a power of 2:

    - (x31 X -2^31) + (x30 X 2^30) + (x29 X 2^29) + ... + (x1 X 2^1) + (x0 X 2^0)
    - This sign bit is multiplied by -2^31, and the rest of the bits are then multiplied by positive versions of their respective base values.
        
 




## 2.5 Representing instructions in the computer

## chapter 4 processor
- MIPS(microprocessor without interlocked pipelined statges) architecture:
  - is a reduced instruction set computer (RISC) instruction set architecture (ISA)
  - developed by MIPS computer systems
- Instruction set architecture (ISA):
  - is the interface between the computer's software and hardware and also can be viewed as the progtammer's view of the machine.
  - computers do not understand high-level progtamming languages such as java, c++.
  - A processor only understand instructions encoded in some numerical fashion, usually as binary numbers.
  - **compliers translate those hight level languages into instruction that the processor can understand.**
  
  - Beside instructions, the ISA defines items in the computer that are available to a program
  -  --e.g., data types, registers, addressing modes, and memory.
   - instructions locate these available items with register indexes( or names) and memory addressing modes.
   
  - The ISA of a computer is usually described in **a small instruction manual,**
  -  which describes how the instructions are encoded.
  -  Also, it may define short(vaguely) mnemonic names for the instructions.
  -  The name can be recongnized by a software development called an assembler
     - assembler:
     - is a computer program that translates a human-readable software programs to isolate and correct malfunction in binary computer programs.  

- A good ISA:
  - ISAs vary in quality and completeness.
  - A good ISA compromises between programmer convenience(how easy the code is to understand)
  - , size of the code(how much code is required to do a specific action),
  - cost of the computer to interpret the instructions(more complexity means more hardware needed to decode and execute the instructions),
  - and speed of the computer(with nore complex decoding hardware comes loger decode time).

### Example: Binary to Decimal Conversion
- Q: 
- What is the decimal value of this 32-bit two's complement number?
-  1111 1111 1111 1111 1111 1111 1111 1100two

- A:
- Substituting the number's bit values into the formula above:
- (1x-2^31) + (1x 2^30) + (1x2^29) + ... + (1x2^1) + (0x2^1) + (0x2*0)
- = -2^31 + 2^30 + 2^29 +...+ 2^2 + 0 + 0
- = -2,147,483,648ten + 2,147,483,644ten
- = -4ten

- We'll see a shortcut to simplify conversion from negative to positive soon.

- Just as an operation on unsigned numbers can overflow the capacity of hardware to represent the result,
- so can an operation on two's complement numbers.
- Overflow occurs when the leftmost retained bit of the binary bit pattern is not the same as the infinite number of digits to the left(the sign bit is incorrect):
  - a 0 on the left of the bit pattern when the number is negative or a 1 when the number is positive.

### Hardware/ Software Interface

Signed load & unsigned load:

- Signed vs unsigned applies **to loads and to arithemetic.**
- The function of a signed load is to copy the sign repeatedly to fill the rest of the register-- called sign extension -- but its purpose it to place a correct representation of the number within that register.
- Unsigned loads simply fill with 0s to the left of the data,
- since the number represented by the bit patten is unsigned.

- When loading a 32-bit word into a 32-bit register, the point is moot;
- signed and unsigned loads are identical.
- MIPS does offer flavors of byte loads:
  - load byte(1b) treats the byte as a signed number and thus sign-extends to fill the 24 left-most bits of the register,
  - while load byte unsigned (1bu) works with unsigned integers.
- Since C progtams almost always use bytes to represent characters rather than consider bytes as very short signed integers,
- 1bu is used practically exclusively for byte loads.
-  

## chapter 5 memory heirarchy
- piplining

