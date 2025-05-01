# Assignment02-RakBnAli96

### 1. 🚀 Clone the Repo
```bash
https://github.com/RakBnAli96/assignment02-RakBnAli96.git
```
Since We need to make a change in the Kernal and Update 
### 2.  First we need to Run the Docker Container 


```bash
docker run --name cse4001 -it eribeirofit/cse4001:latest
```
### 3.  Exec into Docker Container
 
```bash
root@631602b3294b:~/os161# ls
root  src  toolbuild  tools
```

### 3. Navigate into the Directory cd ~/os161/src/kern

```bash
root@631602b3294b:~/os161/src/kern# ls
Makefile  arch  build  compile  conf  dev  fs  gdbscripts  include  lib  main  proc  syscall  test  thread  vfs  vm
```
### 4. Now we have to make A Change in Kernal 
```bash
grep -r "Put-your-group-name-here" .
./main/main.c:	kprintf("Put-your-group-name-here's system version %s (%s #%d)\n",
Binary file ./compile/DUMBVM/main.o matches
Binary file ./compile/DUMBVM/kernel matches
```
### 4. Open This File and Add Your Name  In This File  nano main/main.c 
I Have updated the Code of function.c function.h and main.c according to the instructions.

### 5. Now we have to Move Inside Directory
```bash
  cd ~/os161/src/kern/conf
root@631602b3294b:~/os161/src/kern/conf# ls
DUMBVM  DUMBVM-OPT  GENERIC  GENERIC-OPT  conf.kern  config  newvers.sh

```

### 6 Execution of DUMBVM
```bash
./config DUMBVM
Configuration DUMBVM
Generating files... opt-dumbvm.h opt-hangman.h opt-net.h opt-netfs.h opt-noasserts.h opt-semfs.h opt-sfs.h files.mk Makefile autoconf.h autoconf.c
Remember to make depend

```
### 7 Execute bmake depend
```bash
 cd ../compile/DUMBVM
root@631602b3294b:~/os161/src/kern/compile/DUMBVM# bmake depend
bmake includelinks
`includelinks' is up to date.
rm -f .depend.* || true
bmake realdepend
Configuration in ../compile/DUMBVM done
Remember to make depend
cat .depend.__printf.c .depend.snprintf.c .depend.atoi.c .depend.bzero.c .depend.memcpy.c .depend.memmove.c .depend.memset.c .depend.strcat.c .depend.strchr.c .depend.strcmp.c .depend.strcpy.c .depend.strlen.c .depend.strrchr.c .depend.strtok_r.c .depend.autoconf.c .depend.beep.c .depend.console.c .depend.random.c .depend.rtclock.c .depend.beep_ltimer.c .depend.con_lser.c .depend.emu.c .depend.emu_att.c .depend.lamebus.c .depend.lhd.c .depend.lhd_att.c .depend.lrandom.c .depend.lrandom_att.c .depend.lser.c .depend.lser_att.c .depend.ltimer.c .depend.ltimer_att.c .depend.ltrace.c .depend.ltrace_att.c .depend.random_lrandom.c .depend.rtclock_ltimer.c .depend.semfs_fsops.c .depend.semfs_obj.c .depend.semfs_vnops.c .depend.sfs_balloc.c .depend.sfs_bmap.c .depend.sfs_dir.c .depend.sfs_fsops.c .depend.sfs_inode.c .depend.sfs_io.c .depend.sfs_vnops.c .depend.array.c .depend.bitmap.c .depend.bswap.c .depend.kgets.c .depend.kprintf.c .depend.misc.c .depend.time.c .depend.uio.c .depend.main.c .depend.menu.c .depend.proc.c .depend.loadelf.c .depend.runprogram.c .depend.time_syscalls.c .depend.arraytest.c .depend.bitmaptest.c .depend.fstest.c .depend.kmalloctest.c .depend.semunit.c .depend.synchtest.c .depend.threadlisttest.c .depend.threadtest.c .depend.tt3.c .depend.clock.c .depend.spinlock.c .depend.spl.c .depend.synch.c .depend.thread.c .depend.threadlist.c .depend.device.c .depend.devnull.c .depend.vfscwd.c .depend.vfsfail.c .depend.vfslist.c .depend.vfslookup.c .depend.vfspath.c .depend.vnode.c .depend.kmalloc.c .depend.adddi3.c .depend.anddi3.c .depend.ashldi3.c .depend.ashrdi3.c .depend.cmpdi2.c .depend.divdi3.c .depend.iordi3.c .depend.lshldi3.c .depend.lshrdi3.c .depend.moddi3.c .depend.muldi3.c .depend.negdi2.c .depend.notdi2.c .depend.qdivrem.c .depend.subdi3.c .depend.ucmpdi2.c .depend.udivdi3.c .depend.umoddi3.c .depend.xordi3.c .depend.setjmp.S .depend.trap.c .depend.syscall.c .depend.cpu.c .depend.switch.S .depend.switchframe.c .depend.thread_machdep.c .depend.threadstart.S .depend.dumbvm.c .depend.ram.c .depend.copyinout.c .depend.cache-mips161.S .depend.exception-mips1.S .depend.tlb-mips161.S .depend.lamebus_machdep.c .depend.start.S > .depend
```
### 7 Execute bmake 
```bash
root@631602b3294b:~/os161/src/kern/compile/DUMBVM#  bmake
mips-harvard-os161-gcc -g -Og -Wall -W -Wwrite-strings -Wmissing-prototypes -Werror -std=gnu99 -mno-abicalls -fno-pic -ffixed-23 -nostdinc -I../../include -I../../dev -I. -Iincludelinks -ffreestanding -D_KERNEL -c ../../compile/DUMBVM/autoconf.c
mips-harvard-os161-gcc -g -Og -Wall -W -Wwrite-strings -Wmissing-prototypes -Werror -std=gnu99 -mno-abicalls -fno-pic -ffixed-23 -nostdinc -I../../include -I../../dev -I. -Iincludelinks -ffreestanding -D_KERNEL -c ../../main/main.c
../../conf/newvers.sh DUMBVM
mips-harvard-os161-gcc -g -Og -Wall -W -Wwrite-strings -Wmissing-prototypes -Werror -std=gnu99 -mno-abicalls -fno-pic -ffixed-23 -nostdinc -I../../include -I../../dev -I. -Iincludelinks -ffreestanding -D_KERNEL -c vers.c
mips-harvard-os161-ld   -nostdlib -T ../../arch/mips/conf/ldscript __printf.o snprintf.o atoi.o bzero.o memcpy.o memmove.o memset.o strcat.o strchr.o strcmp.o strcpy.o strlen.o strrchr.o strtok_r.o autoconf.o beep.o console.o random.o rtclock.o beep_ltimer.o con_lser.o emu.o emu_att.o lamebus.o lhd.o lhd_att.o lrandom.o lrandom_att.o lser.o lser_att.o ltimer.o ltimer_att.o ltrace.o ltrace_att.o random_lrandom.o rtclock_ltimer.o semfs_fsops.o semfs_obj.o semfs_vnops.o sfs_balloc.o sfs_bmap.o sfs_dir.o sfs_fsops.o sfs_inode.o sfs_io.o sfs_vnops.o array.o bitmap.o bswap.o kgets.o kprintf.o misc.o time.o uio.o main.o menu.o proc.o loadelf.o runprogram.o time_syscalls.o arraytest.o bitmaptest.o fstest.o kmalloctest.o semunit.o synchtest.o threadlisttest.o threadtest.o tt3.o clock.o spinlock.o spl.o synch.o thread.o threadlist.o device.o devnull.o vfscwd.o vfsfail.o vfslist.o vfslookup.o vfspath.o vnode.o kmalloc.o adddi3.o anddi3.o ashldi3.o ashrdi3.o cmpdi2.o divdi3.o iordi3.o lshldi3.o lshrdi3.o moddi3.o muldi3.o negdi2.o notdi2.o qdivrem.o subdi3.o ucmpdi2.o udivdi3.o umoddi3.o xordi3.o setjmp.o trap.o syscall.o cpu.o switch.o switchframe.o thread_machdep.o threadstart.o dumbvm.o ram.o copyinout.o cache-mips161.o exception-mips1.o tlb-mips161.o lamebus_machdep.o start.o vers.o -o kernel
*** This is DUMBVM build #2 ***
mips-harvard-os161-size kernel
   text	   data	    bss	    dec	    hex	filename
 146044	    192	   6976	 153212	  2567c	kernel
```
### 8 Execute bmake install  
```bash
root@631602b3294b:~/os161/src/kern/compile/DUMBVM# bmake install
[ -d /root/os161/root ] || mkdir /root/os161/root
cp kernel /root/os161/root/kernel-DUMBVM
rm -f /root/os161/root/kernel
ln -s kernel-DUMBVM /root/os161/root/kernel
```
### 8 Go inside a Directory cd ~/os161/root
```bash
root@631602b3294b:~/os161/src/kern/compile/DUMBVM# cd ~/os161/root
```
### 9 Execute Your Final Command 
```bash
root@631602b3294b:~/os161/root# sys161 kernel
sys161: System/161 release 2.0.8, compiled Aug 14 2022 20:57:14

OS/161 base system version 2.0.3
Copyright (c) 2000, 2001-2005, 2008-2011, 2013, 2014
   President and Fellows of Harvard College.  All rights reserved.

Rak Alsharif  system version 0 (DUMBVM #2)

356k physical memory available
Device probe...
lamebus0 (system main bus)
emu0 at lamebus0
ltrace0 at lamebus0
ltimer0 at lamebus0
beep0 at ltimer0
rtclock0 at ltimer0
lrandom0 at lamebus0
random0 at lrandom0
lhd0 at lamebus0
lhd1 at lamebus0
lser0 at lamebus0
con0 at lser0

cpu0: MIPS/161 (System/161 2.x) features 0x0
OS/161 kernel [? for menu]: 
```

As you Notice our System Name is Changed into
```bash
 Rak Alsharif  system version 0 (DUMBVM #2)
```
## License

[MIT](https://choosealicense.com/licenses/mit/)