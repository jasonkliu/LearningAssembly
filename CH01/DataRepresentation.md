Data Representation
===================

Most computers use a binary or two's complement numbering system.  
Decimal system: `123 = 1*10^2 + 2*10^1 + 3*10^0 = 100 + 20 + 3.`  
Binary system: Usually uses +0V and +5V to signify changes, but works the same.  
`11001 (binary) = 1*2^4 + 1*2^3 + 1*2^0 = 16 + 8 + 1`.  
You can put infinite numbers of zeros in front of a binary number without changing
the value; however, here, we'll use a multiples of 8 bits to represent numbers.  
The rightmost bit in a binary number is position 0, then count successively to the left.  
Bit zero is the *low order* (L.O.) bit, and the left-most bit is the *high order* (H.O.) bit.  

### Data Types
Bit - one or zero, but can also represent two different things.  
Nibble - four bits: BCD (Binary Coded Decimal) or hexadecimal. 16 different values.  
Byte - eight bits: main memory and I/O are all bytes. To access anything smaller, you
read the byte containing the data and mask out unwanted bits. 256 different values.
Most important usage: character code. 128 defined ASCII codes, everything else gives you
another 128 random things like Greek letters.
Word - sixteen bits: 65536 values, segment values.  
Double word - thirty-two bits, -2,147,483,648..2,147,483,647, segmented addresses.

### Hexadecimal
To convert hexadecimal to binary, just look up each character code and its representation
into binary and concatenate all of the digits.  
To convert binary to hexadecimal, first pad the number so it has a multiple of four bits in the number. Then separate into blocks of four and then transform them into hex.

### Two's complement
H.O. (high order) bit of a number is a sign bit. If H.O. is 0, the number is positive; 
if the H.O. is 1, then the number is negative. To convert a positive number to a negative
number, invert all the bits in the number (NOT function) then add one to the result. Remember that if you try to negate the smallest negative number: (-32768..+32767), we cannot have +32768 so we cannot negate the smallest negative number. To add numbers,
ignore the carry out of the H.O. bit and just add the values.

### Sign and Zero extension