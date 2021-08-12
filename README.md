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
## Access
  We grant access to the tool and its code for research purposes. Please send an email to lyz_cs@pku.edu.cn with subject `[SCSlicer] code access` and specify in the body your `gitlab` username, so we can grant you access to a private repository that we use for the project. We will keep your data confidential.
 
## Publication
  For more details about SCSlicer, please refer to our DSN-W paper:  
["Automatically Constructing Peer Slices via Semantic- and Context-Aware Security Checks in the Linux Kernel"](https://ieeexplore.ieee.org/document/9502447 "SCSlicer")

## Cite
```bibtex
@INPROCEEDINGS{SCSlicer,
  author={Liu, Yongzhi and Chen, Xiarun and Yang, Zhou and Wen, Weiping},
  booktitle={2021 51st Annual IEEE/IFIP International Conference on Dependable Systems and Networks Workshops (DSN-W)}, 
  title={Automatically Constructing Peer Slices via Semanticand Context-Aware Security Checks in the Linux Kernel}, 
  year={2021},
  volume={},
  number={},
  pages={108-113},
  doi={10.1109/DSN-W52860.2021.00028}}
```
