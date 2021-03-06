# 8080
Intel 8080 Emulator implemented in golang

## Table of Contents
  * [Usage](#usage)
  * [Disassembler](#disassembler)
     * [Example output](#example-output)

## Usage
The following commands are available:

* `make help` to get help
* `make` to build the binary (in bin/)
* `make test` to run tests
* `make vendor` to retrieve dependencies
* `make lint` to run golint
* `make fmt` to run gofmt
* `make clean`

## Disassembler

[8080 reference](8080reference.md)

### Example output
Run disassembler on the invaders.h ROM file.

```
0000 NOP
0001 NOP
0002 NOP
0003 JMP 	$18d4
0005 NOP
0006 NOP
0007 NOP
0008 PUSH 	PSW
000a PUSH 	D
000c JMP 	$008c
000e NOP
000f NOP
0010 PUSH 	PSW
0012 PUSH 	D
0014 MVI 	A,#$80
0017 MOV 	M,D
001a RNZ
001b RIM
001c DCR 	M
001e CALL 	$db17
0020 IN 	$01
0022 RRC
0023 JC 	$0067
0025 NOP
0026 LDA 	$20ea
0028 RIM
0029 ANA 	A
002b MOV 	B,D
002e XCHG
002f RIM
0030 CPI 	#$99
0032 JZ 	$003e
0034 NOP
0035 ADI 	#$01
0037 DAA
0038 STA 	$20eb
003a RIM
003b CALL 	$1947
003d DAD 	D
003f STA 	$20ea

/*
0000000 00 00 00 c3 d4 18 00 00 f5 c5 d5 e5 c3 8c 00 00
0000010 f5 c5 d5 e5 3e 80 32 72 20 21 c0 20 35 cd cd 17
0000020 db 01 0f da 67 00 3a ea 20 a7 ca 42 00 3a eb 20
0000030 fe 99 ca 3e 00 c6 01 27 32 eb 20 cd 47 19 af 32
*/
```