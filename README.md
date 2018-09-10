# Elastic_HH Sketch

## Introduction
Finding heavy hitters has been of vital importance in network measurement. In all the recent works in finding heavy hitters, the Elastic sketch achieves the highest accuracy and fastest speed. However, we find that there is still room for improvement of the Elastic sketch in finding heavy hitters. In this paper, we propose a tailored Elastic to enhance the sketch only for finding heavy hitters at the cost of losing the generality of Elastic. To tailor Elastic, we abandon the light part, and change the eviction strategy.
Experimental results show that compared with the standard Elastic, our tailored Elastic reduces the error rate 5.7～8.1 times, and increases the speed 2.5 times.

## About this repo
- `data`: traces for test, each 13 bytes in a trace is a five tuple: (SrcIP:SrcPort, DstIP:DstPort, protocol)

- `src`: contains codes of Elastic_HH sketch and other algorithms implemented on CPU, all of which can be used to detect heavy hitters. They are  SpaceSaving, Count/CM sketch with a min-heap (CountHeap/CMHeap), Elastic and Elastic_HH, respectively. The codes of measuring their accuracy are also added in these algorithms'  .cpp file.

- `src_for_speed`: algorithms in this folder are the same as those in `src`. The codes in this folder aim at measuring their speed.   

  For all the algorithms, the default memory size is 300KB and can be modified. Besides, codes used to print out the estimated heavy hitters are commented out. If you want to see related results, just modify it.

## Requirements
- SIMD instructions are used in Elastic and Elastic_HH sketches to achieve higher speed, so the CPU must support AVX2 instruction set.
- g++

## How to make
- `cd ./src/demo; make;` then you can find executable file and test the metrics of accuracy of the above algorithms in `demo`.
- Executable file: `./elastic.out; ./elastic_out;./cmheap.out; ./countheap; ./spacesaving.out ` are all followed by  three parameters: the name of output file, algorithms' label name and tested metrics' model name. We use 1~7 to represent the task of measuring ARE, AAE, PR, RR, F1 score, AE's CDF and RE's CDF, respectively.  
- `cd ./src_for_speed/demo; make;` then you can find executable file and test he metrics of speed of  the above algorithms in `demo`. Executable files' names are the same as those in folder `./src/demo`, but only followed by two parameters: the name of output file, algorithms' label name.


