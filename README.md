# SCSlicer
 SCSlicer: Automatically Constructing Peer Slices via Semantic- and Context-Aware Security Checks in the Linux Kernel.

## What is SCSlicer?
 `SCSlicer` is a slicer to construct peer slices in complex and large operating system kernels. Here is the basic idea of how it works.
   
  1. Identifying security checks to find SCCSs and SCFs.

  2. Finding the source and use of critical variables.

  3. Using the three slicing criterions proposed in our paper to construct security check peer slices.
 
## Dependency
  llvm 10.0

## Prepare LLVM bitcode files of OS kernels
- Install the python library wllvm.
- Use wllvm to generate bitcode files
```sh
  # Compile the code with options: -O0, -g, -fno-inline
  $ export LLVM_COMPILER=clang
  $ export LLVM_COMPILER_PATH=*llvm_cur_path*/bin
  $ make defconfig/allyesconfig
  $ make -j8 CC=wllvm
```

## A running example
```sh
  # To analyze a single bitcode file, say "test.bc", run:
  $ ./slicer/build/lib/kanalyzer -sl ./test.bc
```
## Publication
  For more details about SCSlicer, please refer to our DSN-W paper:  
["Automatically Constructing Peer Slices via Semantic- and Context-Aware Security Checks in the Linux Kernel"](https://conferences.computer.org/dsnpub/pdfs/DSN-W2021-3GVHu2G8Nh8yRXXQD8x0pf/395000a108/395000a108.pdf "SCSlicer")

## Cite
```bibtex
@INPROCEEDINGS{SCSlicer21,
  AUTHOR =       {Yongzhi Liu, Xiarun Chen, Zhou Yang and Weiping Wen},
  TITLE =        {Automatically Constructing Peer Slices via Semantic- and Context-Aware Security Checks in the Linux Kernel},
  BOOKTITLE =    {Proc. IEEE/IFIP International Conference on Dependable Systems and Networks Workshops(DSN-W)},
  YEAR =         {2021},
}
```

