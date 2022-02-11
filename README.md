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
- the one constant for computer designers is rapid change, which is driven largely by Moore's Law.
- as computer designs can take years, the resources available per chip can esaily double or qudruple between the start and finish of the project.
- computer architects must anticipate where the technology will be when the design finishes rather than design for where it starts.
- we use an "up and to the right" Moore's Law graph to represent designing for rapid change.

2. Use abstraction to simplify design:
- A major productivity technuque for hardware and software is to use abstractions to represent tht design at different levels of representation;
- lower-level details are hidden to offer a simpler model at higher levels.

3. Make the common case fast:
- making the common case fast will tend to enheance performance better than optimizing the rare case.

4. Performance via parallelism
- computer architects have offered designs that get more performance by performing operatins in parallel.

5. Performance via pipelining
- memory need to b

6. Performance via Prediction

7. Hierarchy of Memories

8. Dependability via redundancy

### abstraction

- A typical application, such as a word processor or a large database system, may consist of millions of lines of code and rely on sophisticated software libraries that implement complex functions in support of the application.
- As we will see, the hardware in a computer can only execute extremely simple low-level instruction.
- To go from a complex application to the simple instructions involves several layers of software that interpret or translate high-level oparations into simple computer instructions,
- an example of the great idea of abstraction.
- Figure 1.3 shows that these layers of software are organized primarily in a hierarchical fashion, with applications being the outermost ring and a variety of system software sitting between the hardware and application software.
- There are many types of systems software, but two types of systems software are central to every conputer system today:
  - 1. an operating system(os)
  - 2. and a compiler

1. operating system:
   - A operating system interfaces between a user's program and the hardware and provides a variety of services and supervisory functions.
   - Among the most important functions are:
     - 1. handling basic input and output operations
     - 2. allocating stroage and memory
     - 3. providing for protected sharing of the computer among multiple applications using it simultaneously.
     - Examples of operating systems in use today are Linux, iOS, and Windows.

2. Compilers: 
   - Compilers perform another vital function:
     - the translation of a program written in a high-leval language, such as C, C++, Java, or Visual Basic into instructions that the hardware can execute.
     - Given the sophistication of modern programming languages and the simplicity of the instructions executed by the hardware, the translation from a high-level language program to hardware instructions is comples.
  
#### From a high-level language to the language of hardware

##### machine language(instruction: binary number): computer can understand
- To actually speak to electronic hardware, you need to send **electric signals.**
- The easiest signals for computers to understand are on and of,
- and so the computer alphabet is just two letters.
- The 2 symbols for these two letters are the numbers 0 and 1, and we commonly think of the **computer language as number in base 2, or binary numbers.**
- We refer to each "letter" as a binary digit or bit.
- Computer are slaves to our commands, which are called instructions.
- **Instructions, which are just collections of bits that the computer understand and obeys.**


##### assembly language: assembler translate a symbolic version of instruction into binary number
- The first programmers communicated to computers in a binary numbers,
- but this was so tedious that they quickly invented new notations that were closer to the way humans think.
- At first, these notatin were translated to binary by hand, but this process was stil tiresome. 
- Using the computer to help program the computer, the pioneers invented programs to translte from symbolic notation to binary.
- **This first of these programs was named an assembler.**
- **This program translates a symbolic version of an instruction into the binary version.**
  - For example, the programmer would write 
    -  add A, B
    -  and the assembler would translate this notation into
    -  1000110010100000
    -  This instruction tells the computer to add the two numbers A and B.
    -  The name coined for this symbolic language, still used today, is assemnly language.
    -  In contrast, the binary language that the machine understands is the machine language.

- The recognition that a program could be written to translate a more powerful language into computer instructions was ont of the great breakthroughs in the early days of computing.
- Progtammers today owe their productivity to the creation of high-level progtamminh languages and compilers
- that translate programs in such languages into instructions.
- figures 1.4 shows the relationships among these programs and languages,
- which are more examples of the power of abstraction.

  - high-level language program (in C)
  - => compiler =>
  - assembly language program (for MIPS)
  - => assembler =>
  - Binary machine language program (for MIPS)
  
-figure 1.4 : C program compiled into assembly language and then assenbled into binary machine language.
   

- A compiler enables a programmer to write this high-level language expression:
  - A + B

- The compiler would compile it into this assembly language statement:
  - add A, B

  - As shown above, the assembler would translate this statement into the binary instructions
  - that tell the computer to add the two numbers A and B.
   
### High-level programming languages's benefits

- High-level programming languages offer several important benefits.

- 1. First, they allow the programmer to think in a more natural language,
  - using English words and algerbraic notation, resulting in programs that look much more like text than like tables of cryptic symbols.
- 2. The second advantage of programminh languages is improved progtammer productivity.
- 3. The final advantage is that programminh languages allow programs to be independent of the computer on which they were developed,
  - since compiler and assemblers can translate high-level language programs to be the binary instructions of any computer.

- These three advantages are so strong that today little programming is done in assembly language.

### 1.4 open the covers of your computer

-figure 1.5 The organization of a computer:
- The five classic compoents of a computer are
- 1. input : writes data to memory
- 2. output : reads data from memory
- 3. memory
- 4. datapath
- 5. control : sends the signals that determine the operations of the datapath, memory, input, and output
   - data path and control sometimes combined and called the processpr
   - processor: gets insturctions and data from memory.


- Two key components of computers are input devices, such as the micro phone, and output devices, such as the speaker.
- input feeds the computer, and output is the result of computation sent to the user.
- Some dvices, such as wireless networks, provide both input and output to the computer.

### Open Apple ipad 2
- Figure 1.7 shows the contents of the Apple iPad 2 tablet computer.

### I/O devices
- Unsurprisingly, of the five classic components of the computer, I/O dominates this reading device.
- The list of I/O devices includes a capacitive multitouch LCD display, front facing camera, rear facing camera, microphone, headphone jack, speakers, accelerometer, gyroscope, Wi-Fi network, and Bluetooth network.
- The datapath, control, and memory are a tiny portion of the components.

### integrated circuits (chips)
- The small rectangles in Figure 1.8 contain the devices that drive our advancing technology, called integrated circuits and nicknamed chips.
### processor(CPU central processor unit)
- The A5 package seen in the middle of in Figure 1.8 contains two ARM processors that operate eith a clock rate of 1 GHz.
- The processor is the active part of the computer, following the instructions of a program to the letter.
- It adds numbers, tests numbers, sgnals I/O devices to activate, and so on.

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
- if the number that is the proper result of such operations **cannot be represented by these rightmost hardware bits,**
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

#### Signed load & unsigned load:

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

#### memory addresses start at 0
- Unlike the numbers discussed above, memory addresses naturally start at 0 and continue to the largest address.
- Put another way, negative address make no sense.
- Thus, programs want to deal sometimes with numbers that can be positive or negative and sometimes with numbers that can be only positive.

- Some programming languages reflect this distinction.
- C, for example, names the former integers(declared as int in the program)
- and the latter unsigned integers(unsigned int).
- Some c style guides even recommend declaring the former as signed int to keep the distiction clear. 


- Let's examine 2 useful shortcuts when working with two's complement numbers.
- The first shortcut is a quick way to negate a two's complement binary number.
- **Simply invert every 0 to 1 and every 1 to 0, then add one to the result.**
- This shortcut is based on the observation that the sum of a number and its inberted representation must be 111 ... 111two, 
- which represens -1.
- **Since x + x' = -1,**
- **therefore x + x' + 1 = 0 or x' + 1 = -x**
- **(We use the notation x' to mean invert every bit in x from 0 to 1 and vice versa.)**

### Example : Negation Shortcut

- Negate 2ten, and then check the result by negating -2ten.
- 2 ten = 0000 0000 0000 0000 0000 0000 0000 0010two

- **x' + 1 = -x**
- negate 2ten + 1 = - 2ten
- Negating this number by inverting the bits and adding one,
  - 1111 1111 1111 1111 1111 1111 1111 1101two + 1two
  - = 1111 1111 1111 1111 1111 1111 1111 1110two
  - = -2ten

- (-x)' + 1 = x
- negate (-2ten) + 1 = 2ten
- Goint the other direction,
  - 1111 1111 1111 1111 1111 1111 1111 1110two
  - is first inverted and then incremented:
  - 0000 0000 0000 0000 0000 0000 0000 0001two + 1two
  - = 0000 0000 0000 0000 0000 0000 0000 0010two
  - = 2ten

### sign extension:
- Our next shortcut tells us how to convert a binary number represented in b bits to a number represented with nore than n bits.
  - For example, the immediate filed in the load, store, branch, add, and set on less than instructions contains a two's complement 16-bit number,
  - representing -32,768ten (-2^15) to 32,767ten (2^15-1).

- **To add the immediate field to a 32-bit register, the computer must convert that 16 bit number to its 32-bit equivalent.**
- The shortcut is to take the most significant bit from the smaller quantity
- --the sign bit--and replicate it to fill the new bits of the larger quantity.
- The old nonsign bits are simply copied into the right portion of the new word.
- This shortcut is commonly called sign extension.

### Example: Sign extension shortcut
- Convert 16-bit binary versions of 2ten and -2ten to 32-bit binary numbers.

- The 16-bit binary version of the number 2 is
- 0000 0000 0000 0010two = 2ten

- It is converted to a 32-bit number by making 16 copies of the value in the most significant bit(0) and placing that in the left-hand half of the word.
- The right half gets the old value:
- 0000 0000 0000 0000 0000 0000 0000 0010two = 2ten
- Let's negate the 16-bit version of 2 using the earlier shortcut. Thus,
- 0000 0000 0000 0010two
- becomes
- 1111 1111 1111 1101two + 1two
- = 1111 1111 1111 1110two

- Creating a 32-bit version of the negative number means copying the sign bit 16 times and placing it on the left:
- 1111 1111 1111 1111 1111 1111 1111 1110two = -2ten 

- This trick works because positive two's complement numbers really have an infinite number of 0s on the left and negative two's complement numbers have an infinite number of 1s.
- The binary bit pattern representing a number hides leading bits to fit the width of the hardware; sign extension simply restores some of them.


### Summary
- The main point of this section is that we need to represent both positive and negative integers within a computer word,
- and although there are pros and cons to any option, the unanimous choice since 1965 has been two's complement.

#### Elaboration: signed decimal numbers(-)
- For signed decimal numbers, we used "-" to represent negative 
- because there no limits to the size of a decimal number.
- Given a fixed word size, 
- binary and hexadecimal(16 base) bit strings can encode the sign;
- hence we do not normally use "+" or "-" with binary or hexadecimal notation.

- Check yourself: 
- Q:
- What is the decimal value of the 64-bit two's complement number?
- 1111 1111 1111 1111 1111 1111 1111 1111 1111 1111 1111 1111 1111 1111 1111 1000two
- A: -8ten

- Explantation:
- 1 x -2^63 + 1 x 2^62 +...+ 1 x 2^4 + 0 x 2^3 + 0 x 2^2 + 0 x 2^1 + 0 x 2^0
- = -... + ... + 8 + 0 + 0 + 0
- = -8ten

### Elaboration: one's complement
- Two's complement gets its name from the rule that the unsigned sum of an n-bit number and its n-bit negative is 2^n;
- hence, the negation or complement of a number x is 2^n - x, or its "two's complement."


- A third alternative representation to two's complement and sign and magnitude is called one's complement.
- The neagtive of a one's complement is found by inverting each bit,
- from 0 to 1 and from 1 to 0, or x'.
- This relation helps explain its name since the complement of x is 2^n - x - 1.
- It was also an attempt to be a better solution than sign and magnitude,
- and several early scientific computer did use the notation.

- This representation is similar to two's complement except that it also has two 0s:
  - 00 ... 00two is positive 0 and 11 ... 11two is negative 0.
  - The most negative number, 10 ... 000two, represents -2,147,483,647ten,
  - and so the positives and negatives are balanced.
  - One's complement adders did need an extra step to subtract a number,
  - and hence two's complement dominates today.

- A notation that represents the most negative value by 10 ... 000two
- and the most positive value by 01 ... 11two,
- leaving an equal number of negatives and positives but ending up with two zeros,
- one positive(00...00two) and one negative(11 ... 11two).
- The term is also used to mean the inversion of every bit in a pattern:
- 0 to 1 and 1 to 0.


### biased notation
- A final notation, which we will look at when we discuss floating point in Chapter 3, 
- is to represent the most negative value by 00 ... 000two and the most positive value by 11 ... 11two,
- with 0 typically having the value 10 ... 00two.
- This is called a biased notation,
- since it biases the number such that the number plus the bias has a non-negative representation.


- A notation that represents the most negative value by 00 ... 000two and the most positive value by 11 ... 11two, with 0 typically having the value 10 ... 00two, thereby biasing the number such that the number plus the bias has a non-negative representation.


## 2.5 Representing instructions in the computer

- Instructions are kept in the computer as a series of high and low electronic signals and may be represented as numbers,
- and placing these numbers side by side by forms the instruction.

- Since registers are reffered to in instructions,
- there must be a convention to map register names into numbers.
- In MIPS assembly language,
  - registers $s0 to $s7 map onto registers 16 to 23, 
  - and registers $t0 to $t7 map onto registers 8 to 15.
  - Hence, $s0 means register 16, $s1 means register 17, $s2 means register 18,...
  - , $t0 means register 8, $t1 means register 9, and so on.

- We'ss describe the convention for the rest of the 32 registers in the following sections.

### Translating a MIPS assembly instruction into a machine instruction

- Let's do the next step in the refinement of the MIPS language as an exampole.

- We'll show the real MIPS language versopm of the instruction represented symbolically as
  - add $t0,$s1,$s2
  - first as a combination of decimal numbers and then of binary numbers.

- The decimal representation is
  - 0 17  18  8  0  32
   - Each of these segaments of an instruction is called a field.
   - The first and last fild(containing 0 and 32 in this case):
     -  in combination tell the MIPS computer that this instruction performs addition.
   - The second field:
     -  gives the number of the register that is the first source operand of the addition operation (17 = $s1),
   - and the thrid field:
     - gives the other source operand for the addition(18 = $s2)
   - The fourth field:
     - contoans the number of the register that is to receive the sum (8 = $t0).
   - The fifth field:
     - is unused in this instuction, so it is set to 0.
   - Thus, this instruction adds register $s1 to $s2 and places the sum in register $t0.

- This instruction can also be represented as field of binary numbers as opposed to decimal:
  - 000000  10001  10010  01000 00000 100000
  - 6 bits   5 bits   5 bits  5 bits  5 bits  6 bits
  
### MIPS instrucion(32 bits)
- This layout of the instruction is called instructio format.
- As you can see from counting the number of bits, this MIPS takses exactly 32 bits -- the same size as data word.
- In keeping with our design principlr that simplicity facors regularity,
  - all MIPS instructions are 32 bits long.

### machine code: a sequenne of numeric version of instuctions(machine language)
- **To distinguish it from assembly language, we call the numeric version of instuctions machine language and a sequenne of such instructions machine code.**
- We avoid to write and read string of binary numbers by using a higher base than binary that converts easily into binary.
- Since almost all computer data sizes are multiples of 4, hexadecimal(base 16) numbers are popular.
- Since base 16 is a power of 2, we can trivially convert by replacing each group of 4 binary digits by a single hexadecimal digit, and vice versa.
- Figure 2.4 converts between hexadecimal and binary.

- Because we frequently deal with different base, to avoid confusion we will subscript 
  - base 10: decimal numbers with ten,
  - base 2: binary numbers with two,
  - base 16: hexadecimal number with hex.
  - (if ther is no subscript, the default is base 10.)
  - By the way, C and Java use the notation 0xnnnn for hexadecimal numbers.  

#### Example: Binary to hecadecimal and back
- Convert the following hecadecimal and binary numbers into the other base:
- eca8 6420hex
- 0001 0011 0101 0111 1001 1011 1101 1111two

#### MIPS field
- MIPS field are given nemes to make them easier to discuss:
  - op rs rt rd shamt funct
  - 6 bits 5bits 5bits 5bits 6bits
  - Here is the meaning of each name of the fields in MIPS instruction:
    - 1. op: Basic operation of the instrucion, traditionally called the *opcode.*
    - 2. rs: The first register source operand.
    - 3. rt: The second register source operand.
    - 4. rd: The register destination operand. It gets the result of the operation.
    - 5. shamt: Shift amount
- opcode: The field that denotes the operation and format of an instuction.

- A problem occurs when an instruction needs longer field than those shown above.
  - For example, the load word instuction must specify 2 registers and a constant.
  - If the address were to use one of the 5-bit fields in the format above, the constant within the load word instruction would be limited to only 2^5 or 32.
  - This constant is used to select elements from arrays or data structures,
  - and it often needs to be much larger than 32.
  - This 5-bit field is too small to be useful.

- Hence, we have a confilct between the desire to keep all instructions the same length and 
- the desire to have a single instruction format.
- This leads us to the final hardwarw design principle:
  - Design Principle 3: Good design demands good compromises.

- The compromise chosen by the MIPS designers is to keep all instructions the same length,
- thereby requiring different kinds of instruction formats for different kinds of instruction.
  - For example,
  - 1. R - format:
      - the format above is called R-type(for register) or R-format.
  - 2. I - format:
      -  A second type of instruction format is called I-type(for immediate) or I-format 
      - and is used by the immediate and data transfer instructions.
      - The fields of I-format are
        - |  op  |  rs  |  rt  |  constant or address   |
        - 6 bits   5 bits 5 bits    16 bits
        - The 16-bit address means a load word instruction can load any word within a region of ± 2^15 or 32768 bytes (± 2^13 or 8192 words) of the address in the base register rs.
        - Similarly, add immediate is limited to constants no longer than ±2^15.
        - We see that more than 32 registers would be difficult in this format, 
        - as the rs and rt fields would each need another bit,
        - making it harder to fit everything in one word.

- Let's look at the load word instruction from page 71:
  - 1w   $t0,32($s3)  # Temporary reg $t0 gets A[8]
  - Here, 19(for $s3) is placed in the rs field, 
  - 8(for $t0) is placed in the rt field,
  - and 32 is placed in the address field.
  - Note that the meaning of the rt field has changed for this instruction:
    - in a load word instruction,
    - the rt field specifies the destination register,
    - which receives the result of the load.

### multiple formats(I, R formats) -> keep the format similar

- Although multuple formats complicate the hardware,
- we can reduce the complexity by keeping the formats similar.
  - For example,
  - the first three field of the R-type and I-type formats are the same size and have the same names;
  - the length of the fourth field in I-type is equal to the sum of the lengths of the last three of R-type.
  
 - In case you were wondering, the formats are distiguished by the values in the first field:
   - each format is assigned a distinct set of values in the first field(op)
   - so that the hardware knows whethter to treat the last half of the instruction
   - as three field(R-type) or as a single field(I-type).
   - Figure 2.5 shows the numbers used in each field for the MIPS instructions covered so far.

| instruction   | Format | op     | rs | rt | rd  | shamt | funct | address |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| add           |  R   | 0     | reg | reg | reg |  0  | 32ten | n.a.    |
| sub(subtract)  |  R   | 0     | reg | reg | reg |  0  | 34ten | n.a.    |
| add immediate  |  I   | 8ten  | reg | reg | n.a. | n.a. | n.a. | constant |
| lw(load word)  |  I   | 35ten | reg | reg | n.a. | n.a. | n.a. | address |
| sw(store woed) |  I   | 43ten | reg | reg | na.a | n.a. | n.a. | address |

- Figure 2.5 MIPS instruction encoding.
- In the table above, 
- "reg" means a register number between 0 and 31,
- "address" means a 16-bit address,
- and "n.a." (not applicable) means this field does not appear in this format.
- Note that add and sub insturctions have the same value in the op field;
- the hardware uses the funct field to decide the variant of the opreation:
  - add(32) or subtract (34). 


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




## chapter 5 memory heirarchy
- piplining


#### Temporal locality(locality in time) : 

- The principle stating that if a data location is referenced then it will tend to be referenced again soon.

#### Spatial locality (locality in space):
- If an item is referenced, items whose address are close by will tend to be referenced soon.
- If a data location is referenced, data locations with nearby addresses will tend to be referenced soon.

#### The basic structure of the memory hierarchy

| instruction   | Format | op     | rs | rt | rd  | shamt | funct | address |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| add           |  R   | 0     | reg | reg | reg |  0  | 32ten | n.a.    |
| sub(subtract)  |  R   | 0     | reg | reg | reg |  0  | 34ten | n.a.    |
| add immediate  |  I   | 8ten  | reg | reg | n.a. | n.a. | n.a. | constant |
| lw(load word)  |  I   | 35ten | reg | reg | n.a. | n.a. | n.a. | address |
| sw(store woed) |  I   | 43ten | reg | reg | na.a | n.a. | n.a. | address |

- Figure 5.1 memory hierarchy:
  - By implementinh the memory system as a hierarchy, the user has the illustration of a memory that is as large as the largest level of the hierarchy,
  - but can be accessed as if it were all built from the fastest memory.
  - Flash memory has replaced disks in many personal mobile devices,
  - and may lead to a new level in the storage hierarchy for desktop and server computers.

- Memory hirearchy:
  - A structure that used multiple levels of memories;
  - as the distance from the processor increase,
  - the size of the memories and the access time both increase.

#### data
- data is copied between only two adjacent levels at a time.

- Figure 5.2 Every pair of levels in the memory hierarchy can be thought of as having upper and lower level.
- Within each level, the unit of information that is present or not is called a block or a line.
- Usually we transfer an entire block when we copy something between levels.

1. block (or line):
   - The minimum unit of information that can be either present or not present in a cache.
2. hit rate:
   - The fraction of memory accessed found in a level of the memory hierarchy.
3. miss rate:
   - The fraction of memory accessed not found in a level of the memory hierarchy.
4. miss penalty:
   - The time required to fetch a block into a level of the memory hierarchy from the lower level,
   - including the time to access the block,
   - transmit it from one level to the other, 
   - insert it in the level that experienced the miss, 
   - and then pass the block to the requestor.
   
#### The upper level:
- The upper level--the one closer to the processor-- is smaller and faster than   the lower level,
  since the upper level uses technology that is more expensive.
- Figure 5.2 shows that the minimum unit of information that can be either present or not present in the two-level hierarchy is called a block or a line.

- If the data requested by the processor appears in some block in the upper level, this is called a hit.
- If the data is not found in the upper level, the request is called a miss.
- The lower level in the hierarchy is then accessed to retrieve the block containing the requested data.
- The hit rate, or hit ratio, is the fraction of memory accesses found in the upper level;
- it is often used as a measure of the performance of the memory hierarchy.
- The miss rate (1-hit rate) is the fraction


## MIPS R2000 Assembly Language
### Branch instruction
- Branch instruction use a signed 16-bit instruction offset field; hence, they can jump 2^15 -1 instructions(not bytes) forward or 2^15 instructions backward.
- jump instruction:
  - contains a 26-bit address field.
- In actual MIPS processors, branch instructions are delays branches, which do not transfer control until the instruction following the branch(its "delay slot") has executed.
- Delayed branches affect the offset calculation,
- since it must be computed relative to the address of the delay slot instruction(PC + 4), which is when the branch occurs.
- SPIM does not simulatee this delay slot,
-  unless the -bare or -delay_branch flags are specified.
-  In assembly code, offsets are not usually specified as numbers.
-  Instead, an instruction brach to a label, and the assembler computes the distance between the branch and the target instructions.
-  In MIPS-32, all actual (not pseudo) 
