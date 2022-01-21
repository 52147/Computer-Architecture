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

- First, let's review how a computer represents numbers.
- Humans are taught to think in base 10, but numbers may be represneted in any base.
  - for example, 123 base 10 = 1111011 base 2.

- Numbers are kept in computer hardware as a series of high and low electronic signals,
- and so they are considered base 2 numbers.
- (base 10 numbers are called decimal numbers , base 2 numbers are called binary numbers.)

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
  - THis representatin leads to an obvious way to number the bits 

## 2.5 Representing instructions in the computer

## chapter 4 processor
- MIPS(microprocessor without interlocked pipelined statges) architecture:
  - is a reduced instruction set computer (RISC) instruction set architecture (ISA)
  - developed by MIPS computer systems
- Instruction set architecture (ISA):
  - is the interface between the computer's software and hardware and also can be viewed as the progtammer's view of the machine.
  - computers do not understand high-level progtamming languages such as java, c++.
  - A processor only understand instructions encoded in some numerical fashion, usually as binary numbers.
  - compliers translate those hight level languages into instruction that the processor can understand.
  
  - Beside instructions, the ISA defines items in the computer that are available to a program
  -  --e.g., data types, registers, addressing modes, and memory.
   - instructions locate these available items with register indexes( or names) and memory addressing modes.
   
  - The ISA of a computer is usually described in a small instruction manual,
  -  which describes how the instructions are encoded.
  -  Also, it may define short(vaguely) mnemonic names for the instructions.
  -  The name can be recongnized by a software development called an assembler/
     - assembler:
     - is a computer program that translates a human-readable software programs to isolate and correct malfunction in binary computer programs.  


- ISAs vary in quality and completeness.
- A good ISA compromises between programmer convenience(how easy the code is to understand)
- , size of the code(how much code is required to do a specific action),
- cost of the computer to interpret the instructions(more complexity means more hardware needed to decode and execute the instructions),
- and speed of the computer(with nore complex decoding hardware comes loger decode time).

## chapter 5 memory heirarchy
- piplining

