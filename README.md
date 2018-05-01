# afl-patches
Patches to afl to fix bugs or add enhancements


## Introduction

All patches are for the current version afl2.52b and can be applied in the extracted afl directory (-p0).


## Todo

Add https://gitlab.com/laf-intel/laf-llvm-pass


## Patches

### Fixes

**afl-llvm-fix.diff**		- aflc-lang: fix to afl llvm for SIGCHLD in the forkserver (by Kuang-che Wu <kcwu(at)csie(dot)org>)

**afl-sort-all_uniq-fix.diff**	- afl-cmin: fix sort (by legarrec(dot)vincent(at)gmail(dot)com)


### Enhancements / Features

**afl-fuzz-tmpdir.diff**			- afl-fuzz: patch that adds AFL_TMPDIR where the .cur_input file will be written to. If you do not want your -o folder on a ramdisk this is what you want. (by mh(at)mh-sec(dot)de)

**afl_qemu_optimize_entrypoint.diff**		- afl-qemu: fixes entrypoint detection for ARM thumb (by Marc Harris <markh(dot)sj(at)gmail(dot)com> plus adds AFL_ENTRYPOINT that lets you specify any point you want for the forkserver (gives more speed) (by mh(at)mh-sec(dot)de)

**afl_qemu_optimize_logconditional.diff**	- afl-qemu: only log destinations of calls and conditional jumps. patch is only for INTEL and ARM. makes it a bit slower but helpful for large targets that fill up the map otherwise (by mh(at)mh-sec(dot)de)

**afl_qemu_optimize_map.diff**			- afl-qemu: removes 2 instructions from afl_log at a cost of 64kb.  (by mh(at)mh-sec(dot)de)

**afl-as-AFL_INST_RATIO.diff**			- afl-afl: do not divise by 3 with sanitizer if AFL_INST_RATIO is manually set.  (by legarrec(dot)vincent(at)gmail(dot)com)

**afl-cmin-reduce-dataset.diff**		- afl-cmin: rather small dataset of testcase instead of small testcase.  (by legarrec(dot)vincent(at)gmail(dot)com)

