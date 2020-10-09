# BCDpacks
BCD-Binary coded decimal types

******Unpacked Decimal Data:-

Unpacked Decimal use one byte to store one digit or character.   but since there are only 1 digit and a byte can hold 256 different values this is a bit wasteful.
ex:-
  1). 5 ---> 00000101

******Packed Decimal Data:-

Packed decimal uses the fact that 4bits can store 16different values. So you can store two digits in a byte (top 4bits and bottom 4bits). This is still a bit wasteful since you only use half the capacity. But it's pretty easy to extract the two digits with just shift and mask operations.

Pretty much the only place you would see BCD these days is in some low level hardware where you want to read/x-mit a digit without using a microprocessor at all. 

ex:-
1. 58---> 0101 1000

*****Zoned Decimal Data:-

The following applies to zoned decimal data representation:

A zoned decimal representation stores a decimal digit in the low order nibble of each byte. For all but the byte containing the sign, the high-order nibble is the numeric zone nibble (F on EBCDIC and 3 on ASCII).

The sign can be merged into a byte with a digit, or it can be separate, depending on the representation. But the standard zoned decimal format and informat expects the sign to be merged into the last byte.

The EBCDIC and ASCII zoned decimal formats produce the same printable representation of numbers. There are two nibbles per byte, each indicated by a hexadecimal digit. For example,  the value 15 is stored in two bytes. The first byte contains the hexadecimal value F1 and the second byte contains the hexadecimal value C5.
