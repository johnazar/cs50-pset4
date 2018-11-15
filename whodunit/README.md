# Questions

## What's `stdint.h`?

header shall declare sets of integer types having specified widths, and shall define corresponding sets of macros. It shall also define macros that specify limits of integer types corresponding to types defined in other standard headers.


## What's the point of using `uint8_t`, `uint32_t`, `int32_t`, and `uint16_t` in a program?

It’s easier to have aliases to use interchangeably for explicit fixed width integers. Specifies the number of bytes because one system an int might be a long in another.

## How many bytes is a `BYTE`, a `DWORD`, a `LONG`, and a `WORD`, respectively?

BYTE uint8_t = 1 byte unsigned integer
DWORD uint32_t = 4 byte unsigned integer
LONG int32_t = 4 byte signed integer
WORD uint16_t = 2 byte unsigned integer
## What (in ASCII, decimal, or hexadecimal) must the first two bytes of any BMP file be? Leading bytes used to identify file formats (with high probability) are generally called "magic numbers."

The file type; must be BM (ASCII).
0x42 0x4D in hexadecimal.

## What's the difference between `bfSize` and `biSize`?

bfSize is the size of, in bytes, of the bitmap file. bfSize = biSizeImage + 54
biSize is the number of bytes required by the structure. (BITMAPINFOHEADER) 40 bytes.

## What does it mean if `biHeight` is negative?

The height of the bitmap, in pixels. If biHeight is positive, the bitmap is a bottom-up DIB and its origin is the lower-left corner. If biHeight is negative, the bitmap is a top-down DIB and its origin is the upper-left corner.

If biHeight is negative, indicating a top-down DIB, biCompression must be either BI_RGB or BI_BITFIELDS. Top-down DIBs cannot be compressed.

## What field in `BITMAPINFOHEADER` specifies the BMP's color depth (i.e., bits per pixel)?

biBitCount

## Why might `fopen` return `NULL` in lines 24 and 32 of `copy.c`?

If the file cannot be found.

## Why is the third argument to `fread` always `1` in our code?

http://www.tutorialspoint.com/c_standard_library/c_function_fread.htm
The third argument of fread is the number of elements, each one with a size of <size> bytes.
Since we are looking through each struct one at a time we put the third argument as 1 every time.

## What value does line 65 of `copy.c` assign to `padding` if `bi.biWidth` is `3`?

int padding =  (4 - (bi.biWidth * sizeof(RGBTRIPLE)) % 4) % 4;
RGBTRIPLE is 3 bytes (24 bits)
3 % 4 is 3
Padding = 3

## What does `fseek` do?

Sets the file position indicator for the file stream to the value pointed to by offset.

## What is `SEEK_CUR`?

How you set the offset to be relative to the current position indicator instead of the start or end.

## Whodunit?

TODO
