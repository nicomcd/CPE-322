*I pledge my Honor that I have abided by the Stevens Honor System*

- Go to the GitHub repository of Digital System Design (DSD)
- Study VHDL and GHDL
- Go to the GHDL folder
- Install GHDL and GTKWave
- Run the Half Adder example
- Run another example such as D Flip-Flop or 4-to-1 Multiplexer
- Document the results on your GitHub repository
- Option 1: EDA Playground
- Option 2: Icarus Verilog
- Option 3: SmartSim on Raspberry Pi

I ran all of the files because it took a long time to set this up, and I wanted to know what everything looked like:

## Hello, World
---
```
$ ghdl -h
$ ghdl -v
$ ghdl -a hello.vhdl
$ ghdl -e hello_world
$ ghdl -r hello_world
Hello world!
```

![Hello, World](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1hello_world.png)

## Half Adder
---
```
$ ghdl -a ha.vhdl
$ ghdl -a ha_tb.vhdl
$ ghdl -e ha_tb
$ ghdl -r ha_tb --vcd=ha.vcd
ha_tb.vhdl:47:5:@5ns:(assertion error): Reached end of test
$ gtkwave ha.vcd
```

![Half Adder](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1ha_tb.png)

## Full Adder
---
```
$ ghdl -a adder.vhdl
$ ghdl -a adder_tb.vhdl
$ ghdl -e adder_tb
$ ghdl -r adder_tb --vcd=adder.vcd
adder_tb.vhdl:54:5:@8ns(assertion note): end of test
$ gtkwave adder.vcd
```

![Adder](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1adder_tb.png)

## D Flip-Flop
---
```
$ ghdl -a dff.vhdl
$ ghdl -a dff_tb.vhdl
$ ghdl -e dff_tb
$ ghdl -r dff_tb --vcd=dff.vcd
$ gtkwave dff.vcd
```
![D Flip Flop](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1flipflopD.png)

## T Flip-Flop
---
```
$ ghdl -a tff.vhdl
$ ghdl -a tff_tb.vhdl
$ ghdl -e tff_tb
$ ghdl -r tff_tb --vcd=tff.vcd
$ gtkwave tff.vcd
```

![T Flip Flop](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1tflipflop.png)

## 4-to-1 Multiplexer
---
```
$ ghdl -a mux.vhdl
$ ghdl -a mux_tb.vhdl
$ ghdl -e mux_tb
$ ghdl -r mux_tb --vcd=mux.vcd
$ gtkwave mux.vcd
```


![4 to 1 Multiplexer](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab14mux.png)

## 1-to-4 Demultiplexer
---
```
$ ghdl -a demux.vhdl
$ ghdl -a demux_tb.vhdl
$ ghdl -e demux_tb
$ ghdl -r demux_tb --vcd=demux.vcd
$ gtkwave demux.vcd
```

![1 to 4 Demultiplexer](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1demux.png)

## SR Flip-Flop
---
```
$ ghdl -a --ieee=synopsys sr_ff.vhdl
$ ghdl -a --ieee=synopsys sr_ff_tb.vhdl
$ ghdl -e --ieee=synopsys sr_ff_tb
$ ghdl -r --ieee=synopsys sr_ff_tb --stop-time=100ns --vcd=sr_ff.vcd
```

![SR Flip Flop](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1srflipflop.png)

## 8-Bit Square Root
---
```
$ ghdl -a --ieee=synopsys sqrt8.vhdl
$ ghdl -e --ieee=synopsys sqrt8
$ ghdl -r --ieee=synopsys sqrt8 --stop-time=512ns > sqrt8.out
$ cat sqrt8.out
sqrt( 00000000 )= 0000
sqrt( 00000001 )= 0001
sqrt( 00000010 )= 0001
sqrt( 00000011 )= 0001
sqrt( 00000100 )= 0010
sqrt( 00000101 )= 0010
sqrt( 00000110 )= 0010
sqrt( 00000111 )= 0010
sqrt( 00001000 )= 0010
sqrt( 00001001 )= 0011
sqrt( 00001010 )= 0011
sqrt( 00001011 )= 0011
sqrt( 00001100 )= 0011
sqrt( 00001101 )= 0011
sqrt( 00001110 )= 0011
sqrt( 00001111 )= 0011
sqrt( 00010000 )= 0100
sqrt( 00010001 )= 0100
sqrt( 00010010 )= 0100
sqrt( 00010011 )= 0100
sqrt( 00010100 )= 0100
sqrt( 00010101 )= 0100
sqrt( 00010110 )= 0100
sqrt( 00010111 )= 0100
sqrt( 00011000 )= 0100
sqrt( 00011001 )= 0101
sqrt( 00011010 )= 0101
sqrt( 00011011 )= 0101
sqrt( 00011100 )= 0101
sqrt( 00011101 )= 0101
sqrt( 00011110 )= 0101
sqrt( 00011111 )= 0101
sqrt( 00100000 )= 0101
sqrt( 00100001 )= 0101
sqrt( 00100010 )= 0101
sqrt( 00100011 )= 0101
sqrt( 00100100 )= 0110
sqrt( 00100101 )= 0110
sqrt( 00100110 )= 0110
sqrt( 00100111 )= 0110
sqrt( 00101000 )= 0110
sqrt( 00101001 )= 0110
sqrt( 00101010 )= 0110
sqrt( 00101011 )= 0110
sqrt( 00101100 )= 0110
sqrt( 00101101 )= 0110
sqrt( 00101110 )= 0110
sqrt( 00101111 )= 0110
sqrt( 00110000 )= 0110
sqrt( 00110001 )= 0111
sqrt( 00110010 )= 0111
sqrt( 00110011 )= 0111
sqrt( 00110100 )= 0111
sqrt( 00110101 )= 0111
sqrt( 00110110 )= 0111
sqrt( 00110111 )= 0111
sqrt( 00111000 )= 0111
sqrt( 00111001 )= 0111
sqrt( 00111010 )= 0111
sqrt( 00111011 )= 0111
sqrt( 00111100 )= 0111
sqrt( 00111101 )= 0111
sqrt( 00111110 )= 0111
sqrt( 00111111 )= 0111
sqrt( 01000000 )= 1000
sqrt( 01000001 )= 1000
sqrt( 01000010 )= 1000
sqrt( 01000011 )= 1000
sqrt( 01000100 )= 1000
sqrt( 01000101 )= 1000
sqrt( 01000110 )= 1000
sqrt( 01000111 )= 1000
sqrt( 01001000 )= 1000
sqrt( 01001001 )= 1000
sqrt( 01001010 )= 1000
sqrt( 01001011 )= 1000
sqrt( 01001100 )= 1000
sqrt( 01001101 )= 1000
sqrt( 01001110 )= 1000
sqrt( 01001111 )= 1000
sqrt( 01010000 )= 1000
sqrt( 01010001 )= 1001
sqrt( 01010010 )= 1001
sqrt( 01010011 )= 1001
sqrt( 01010100 )= 1001
sqrt( 01010101 )= 1001
sqrt( 01010110 )= 1001
sqrt( 01010111 )= 1001
sqrt( 01011000 )= 1001
sqrt( 01011001 )= 1001
sqrt( 01011010 )= 1001
sqrt( 01011011 )= 1001
sqrt( 01011100 )= 1001
sqrt( 01011101 )= 1001
sqrt( 01011110 )= 1001
sqrt( 01011111 )= 1001
sqrt( 01100000 )= 1001
sqrt( 01100001 )= 1001
sqrt( 01100010 )= 1001
sqrt( 01100011 )= 1001
sqrt( 01100100 )= 1010
sqrt( 01100101 )= 1010
sqrt( 01100110 )= 1010
sqrt( 01100111 )= 1010
sqrt( 01101000 )= 1010
sqrt( 01101001 )= 1010
sqrt( 01101010 )= 1010
sqrt( 01101011 )= 1010
sqrt( 01101100 )= 1010
sqrt( 01101101 )= 1010
sqrt( 01101110 )= 1010
sqrt( 01101111 )= 1010
sqrt( 01110000 )= 1010
sqrt( 01110001 )= 1010
sqrt( 01110010 )= 1010
sqrt( 01110011 )= 1010
sqrt( 01110100 )= 1010
sqrt( 01110101 )= 1010
sqrt( 01110110 )= 1010
sqrt( 01110111 )= 1010
sqrt( 01111000 )= 1010
sqrt( 01111001 )= 1011
sqrt( 01111010 )= 1011
sqrt( 01111011 )= 1011
sqrt( 01111100 )= 1011
sqrt( 01111101 )= 1011
sqrt( 01111110 )= 1011
sqrt( 01111111 )= 1011
sqrt( 10000000 )= 1011
sqrt( 10000001 )= 1011
sqrt( 10000010 )= 1011
sqrt( 10000011 )= 1011
sqrt( 10000100 )= 1011
sqrt( 10000101 )= 1011
sqrt( 10000110 )= 1011
sqrt( 10000111 )= 1011
sqrt( 10001000 )= 1011
sqrt( 10001001 )= 1011
sqrt( 10001010 )= 1011
sqrt( 10001011 )= 1011
sqrt( 10001100 )= 1011
sqrt( 10001101 )= 1011
sqrt( 10001110 )= 1011
sqrt( 10001111 )= 1011
sqrt( 10010000 )= 1100
sqrt( 10010001 )= 1100
sqrt( 10010010 )= 1100
sqrt( 10010011 )= 1100
sqrt( 10010100 )= 1100
sqrt( 10010101 )= 1100
sqrt( 10010110 )= 1100
sqrt( 10010111 )= 1100
sqrt( 10011000 )= 1100
sqrt( 10011001 )= 1100
sqrt( 10011010 )= 1100
sqrt( 10011011 )= 1100
sqrt( 10011100 )= 1100
sqrt( 10011101 )= 1100
sqrt( 10011110 )= 1100
sqrt( 10011111 )= 1100
sqrt( 10100000 )= 1100
sqrt( 10100001 )= 1100
sqrt( 10100010 )= 1100
sqrt( 10100011 )= 1100
sqrt( 10100100 )= 1100
sqrt( 10100101 )= 1100
sqrt( 10100110 )= 1100
sqrt( 10100111 )= 1100
sqrt( 10101000 )= 1100
sqrt( 10101001 )= 1101
sqrt( 10101010 )= 1101
sqrt( 10101011 )= 1101
sqrt( 10101100 )= 1101
sqrt( 10101101 )= 1101
sqrt( 10101110 )= 1101
sqrt( 10101111 )= 1101
sqrt( 10110000 )= 1101
sqrt( 10110001 )= 1101
sqrt( 10110010 )= 1101
sqrt( 10110011 )= 1101
sqrt( 10110100 )= 1101
sqrt( 10110101 )= 1101
sqrt( 10110110 )= 1101
sqrt( 10110111 )= 1101
sqrt( 10111000 )= 1101
sqrt( 10111001 )= 1101
sqrt( 10111010 )= 1101
sqrt( 10111011 )= 1101
sqrt( 10111100 )= 1101
sqrt( 10111101 )= 1101
sqrt( 10111110 )= 1101
sqrt( 10111111 )= 1101
sqrt( 11000000 )= 1101
sqrt( 11000001 )= 1101
sqrt( 11000010 )= 1101
sqrt( 11000011 )= 1101
sqrt( 11000100 )= 1110
sqrt( 11000101 )= 1110
sqrt( 11000110 )= 1110
sqrt( 11000111 )= 1110
sqrt( 11001000 )= 1110
sqrt( 11001001 )= 1110
sqrt( 11001010 )= 1110
sqrt( 11001011 )= 1110
sqrt( 11001100 )= 1110
sqrt( 11001101 )= 1110
sqrt( 11001110 )= 1110
sqrt( 11001111 )= 1110
sqrt( 11010000 )= 1110
sqrt( 11010001 )= 1110
sqrt( 11010010 )= 1110
sqrt( 11010011 )= 1110
sqrt( 11010100 )= 1110
sqrt( 11010101 )= 1110
sqrt( 11010110 )= 1110
sqrt( 11010111 )= 1110
sqrt( 11011000 )= 1110
sqrt( 11011001 )= 1110
sqrt( 11011010 )= 1110
sqrt( 11011011 )= 1110
sqrt( 11011100 )= 1110
sqrt( 11011101 )= 1110
sqrt( 11011110 )= 1110
sqrt( 11011111 )= 1110
sqrt( 11100000 )= 1110
sqrt( 11100001 )= 1111
sqrt( 11100010 )= 1111
sqrt( 11100011 )= 1111
sqrt( 11100100 )= 1111
sqrt( 11100101 )= 1111
sqrt( 11100110 )= 1111
sqrt( 11100111 )= 1111
sqrt( 11101000 )= 1111
sqrt( 11101001 )= 1111
sqrt( 11101010 )= 1111
sqrt( 11101011 )= 1111
sqrt( 11101100 )= 1111
sqrt( 11101101 )= 1111
sqrt( 11101110 )= 1111
sqrt( 11101111 )= 1111
sqrt( 11110000 )= 1111
sqrt( 11110001 )= 1111
sqrt( 11110010 )= 1111
sqrt( 11110011 )= 1111
sqrt( 11110100 )= 1111
sqrt( 11110101 )= 1111
sqrt( 11110110 )= 1111
sqrt( 11110111 )= 1111
sqrt( 11111000 )= 1111
sqrt( 11111001 )= 1111
sqrt( 11111010 )= 1111
sqrt( 11111011 )= 1111
sqrt( 11111100 )= 1111
sqrt( 11111101 )= 1111
sqrt( 11111110 )= 1111
sqrt( 11111111 )= 1111
$ ghdl -r --ieee=synopsys sqrt8 --stop-time=512ns --vcd=sqrt8.vcd
```

![8 bit part 1](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1sqrt81.png)
![8 bit part 2](https://github.com/nicomcd/Engineering-Design-VI/blob/main/Images/Lab1sqrt82.png)
