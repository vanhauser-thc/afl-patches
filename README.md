# afl-patches
Patches to afl to fix bugs or add enhancements

## Patches

### Fixes

afl-llvm-fix.diff	- aflc-lang: fix to afl llvm for SIGCHLD in the forkserver (by Kuang-che Wu <kcwu(at)csie(dot)org>)


### Enhancements / Features

afl-fuzz-tmpdir.diff	- afl-fuzz: patch that adds AFL_TMPDIR where the .cur_input file will be written to. If you do not want your -o folder on a ramdisk this is what you want. (by mh(at)mh-sec(dot)de)

afl_qemu_optimize_entrypoint.diff	- afl-qemu: fixes entrypoint detection for ARM thumb (by Marc Harris <markh(dot)sj(at)gmail(dot)com> plus adds AFL_ENTRYPOINT that lets you specify any point you want for the forkserver (gives more speed) (by mh(at)mh-sec(dot)de)

afl_qemu_optimize_logconditional.diff	- afl-qemu: only log destinations of calls and conditional jumps. patch is only for INTEL and ARM. makes it a bit slower but helpful for large targets that fill up the map otherwise (by mh(at)mh-sec(dot)de)

afl_qemu_optimize_map.diff		- afl-qemu: removes 2 intstructions from afl_log at a cost of 64kb.  (by mh(at)mh-sec(dot)de)

