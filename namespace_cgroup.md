# namespace and cgroup
#### namespace实现在视图的上隔离
#### cgroup实现了资源的隔离
linux cgroups, linux control group, 作用就是，限制一个进程组能够使用的资源上限，包括cpu,内存，磁盘，网络带宽等
cgroups给用户暴露出来的接口是文件系统，即它以文件和目录的方式组织在操作系统的/sys/fs/cgroup路径下，我们可以使用命令展示出来：
> mount -t cgroup
