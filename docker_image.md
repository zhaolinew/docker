## mount namespace是容器中第一个namespace
1. 开启mount namespace;
2. 指行mount挂载volume;
3. chroot改变进程的根目录.

## docker，最核心的原理就是为待创建的用户进程：
1. 启用linux namespace配置；
2. 设置批定的cgroup能数；
3. 切换进程的根目录（change root）.
