# Linux /proc 系统文件的学习笔记
所有的文件都是内核产生的镜像文件，在打开时才会生成信息

### files
+  /proc/devices  列出所有已经载入内核的主设备号和对应驱动
+  /proc/version  系统版本信息 uname 命令就读取次文件
+  /proc/cpuinfo   cpu 信息
+  /proc/meminfo   内存信息
+  /proc/modules  当前内核加载的模块列表 可是使用lsmod察看
+  /proc/swaps    swaps 信息         
+  /proc/uptime   系统启动时间
+  /proc/loadavg   负载信息
+  /proc/interrupts 中断的信息和对应设备
+  /proc/ioports    硬件设备对应的内存位置分配表
+  /proc/kcore     是物理内存。 alias
                   使用ls -h 显示的大小是物理内存的大小，但是有
                   可能和实际的大小不同（why?) kcore 不占用实际
                   的硬盘大小 du -h = 0
+ /proc/partitions 系统目前的所有分区

### /pid/ info see  proc(5) man page
+  modules 当前内核加载的模块列表 可是使用lsmod察看

#### /proc/sys/ 系统参数配置，系统状态，优化系统
+  /proc/sys/kernel/        内核的配置以及参数
+  /proc/sys/net/           网络的配置和状态
+  /proc/sys/fs/            文件系统

#### process Entries {{{
所有的进程的信息都已自己的pid为文件名在/proc/中
`
+  /proc/pid/cmdline  包含进程的参数列表
+  /proc/pid/environ  进程的环境
+  /proc/pid/maps     进程的地址映射信息
+  /proc/pid/stat     包含大量的进程状态和统计信息
+  /proc/pid/statm    包含进程的内存使用信息
+  /proc/pid/status   包含大量的进程状态和统计信息,格式化过的人类可读的
+  /proc/pid/limits   进程的资源限制信息
+  /proc/pid/cwd -> /home/zhaoli/xpoker/Logic    一个符号链接，指向当前的工作目录
+  /proc/pid/exe -> /home/zhaoli/xpoker/Logic/Logic 一个符号链接 指向进程的执行文件
+  /proc/pid/root -> /                              一个符号链接 指向当前的root 目录
+  /proc/pid/fd    进程打开的所有文件

+  /proc/pid/attr
+  /proc/pid/autogroup
+  /proc/pid/auxv
+  /proc/pid/cgroup
+  /proc/pid/clear_refs
+  /proc/pid/comm
+  /proc/pid/coredump_filter
+  /proc/pid/cpuset
+  /proc/pid/fdinfo
+  /proc/pid/io
+  /proc/pid/latency
+  /proc/pid/loginuid
+  /proc/pid/mem
+  /proc/pid/mountinfo
+  /proc/pid/mounts
+  /proc/pid/mountstats
+  /proc/pid/net
+  /proc/pid/ns
+  /proc/pid/numa_maps
+  /proc/pid/oom_adj
+  /proc/pid/oom_score
+  /proc/pid/oom_score_adj
+  /proc/pid/pagemap
+  /proc/pid/personality
+  /proc/pid/sched
+  /proc/pid/schedstat
+  /proc/pid/sessionid
+  /proc/pid/smaps
+  /proc/pid/stack
+  /proc/pid/syscall
+  /proc/pid/task

}}}
#### /proc/self
  是一个链接，指向自己(当前进程)的/proc/pid 目录, 为方便的进程查找自己的信息，
  .e.g 你有bash 终端cat /proc/self 这是这个self就是bash进程自己
`
set vim:foldmethod=marker
