# afl-patches
Patches to afl to fix bugs or add enhancements


## Introduction

All patches are for the current version afl-2.52b and can be applied in the extracted afl directory (patch -p0 < patch.diff).


## Patches

### Fixes

**afl-llvm-fix.diff**		- afl-clang: fix to afl llvm for SIGCHLD in the forkserver (by kcwu(at)csie(dot)org)

**afl-llvm-fix2.diff**		- afl-clang: fix to afl llvm to remove target binary optimisation and use g++ for compiling (needed for LLVM 5.0+) (by mh(at)mh-sec(dot)de)

**afl-sort-all_uniq-fix.diff**	- afl-cmin: fix sort (by legarrec(dot)vincent(at)gmail(dot)com)


### Enhancements / Features

**afl-fuzz-context_sensitive.diff**		- afl-fuzz: patch that reimplements Angora Fuzzer's context sensitive branch coverage extension. (by heiko(dot)eissfeldt(at)hexco(dot)de)

**laf-intel.diff**				- afl-clang-fast/afl-clang-fast++: implements laf-intel (rewriting memcmp/strcmp for easier solving) (by heiko(dot)eissfeldt(at)hexco(dot)de)

**afl-llvm-optimize.diff**			- afl-clang-fast/afl-clang-fast++: only instrument blocks that are relevant, ~5-10%% less blocks to instrument equals more speed and less map pollution. (by mh(at)mh-sec(dot)de)

**afl-fuzz-tmpdir.diff**			- afl-fuzz: patch that adds AFL_TMPDIR where the .cur_input file will be written to. If you do not want your -o folder on a ramdisk this is what you want. (by mh(at)mh-sec(dot)de)

**afl-tmpfs.diff**				- afl-fuzz: patch that uses tmpfs for the .cur_input file, basically the same idea that my patch uses, but maybe easier. (by jjudin(at)iki(dot)fi)

**afl-fuzz-79x24.diff**                         - afl-fuzz: lower the terminal requirements to 79x24 to display the status screen. (by heiko(dot)eissfeldt(at)hexco(dot)de)

**afl-fuzz-fileextensionopt.diff**		- afl-fuzz: cmdline option to force the input file to have a specific extension

**afl-qemu-optimize-entrypoint.diff**		- afl-qemu: fixes entrypoint detection for ARM thumb (by markh(dot)sj(at)gmail(dot)com plus adds AFL_ENTRYPOINT that lets you specify any point you want for the forkserver (gives more speed) (by mh(at)mh-sec(dot)de)

**afl-qemu-optimize-logconditional.diff**	- afl-qemu: only log destinations of calls and conditional jumps. patch is only for INTEL and ARM. makes it a bit slower but helpful for large targets that fill up the map otherwise (by mh(at)mh-sec(dot)de)

**afl-qemu-optimize-map.diff**			- afl-qemu: removes 2 instructions from afl_log at a cost of 64kb.  (by mh(at)mh-sec(dot)de)

**afl-qemu-speed.diff**				- afl-qemu: fixes afl/qemu to allow caching, x3 speed improvement. (by abiondo on github)

**afl-qemu-ppc64.diff**				- afl-qemu: afl's patch is broken for PPC, william(dot)barsse(at)airbus(dot)com fixed it.

**afl-as-AFL_INST_RATIO.diff**			- afl-as: do not divide by 3 with sanitizer if AFL_INST_RATIO is manually set.  (by legarrec(dot)vincent(at)gmail(dot)com)

**afl-cmin-reduce-dataset.diff**		- afl-cmin: rather small dataset of testcase instead of small testcase.  (by legarrec(dot)vincent(at)gmail(dot)com)
