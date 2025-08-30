# CSCE 3600 – Recitation 1: ASCII Bits & Bytes

Converts a single **printable ASCII character** into its **decimal**, **hexadecimal**, and **8-bit binary** representation using C and bitwise operations.

## Overview
This program:
- Prompts the user for one printable ASCII character.
- Prints its value in:
  - Decimal (`dec`)
  - Hexadecimal (`hex`, uppercase)
  - Binary (`bin`, 8 digits, including leading zeros)

The binary output is produced via right shifts and a bitmask (`& 1`) inside a `for` loop decrementing from bit 7 to bit 0.

## File
- `rec01.c`

## Build & Run
On macOS (local testing)

gcc rec01.c -o rec01
./rec01

Usage
Program prompts:
Enter an ASCII character: A
Sample Output
Input: A
dec -- 65
hex -- 41
bin -- 01000001
Input: a
dec -- 97
hex -- 61
bin -- 01100001
Implementation Notes
Input stored as unsigned char for predictable, non-negative integer behavior and clean bitwise shifts.
Binary printing uses:
for (int i = 7; i >= 0; i--) {
    int bit = (ch >> i) & 1;
    printf("%d", bit);
}
printf("\n");
Hex uses %X to match the assignment’s sample output.
Repo Structure
csce3600-rec01/
├─ rec01.c
└─ README.md


