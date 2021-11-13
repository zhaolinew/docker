## mount namespace是容器中第一个namespace
1. 开启mount namespace;
2. 指行mount挂载volume;
3. chroot改变进程的根目录.

## docker，最核心的原理就是为待创建的用户进程：
1. 启用linux namespace配置；
2. 设置批定的cgroup能数；
3. 切换进程的根目录（change root）.
## docker使用overlay2做为unionFS实现
/var/lib/docker/overlay2目录，通过docker inspect命令可以查看到镜像在该目录下生成的各种目录文件，
- LowerDir：指向镜像层；
- UpperDir：指向容器层，在容器中创建文件后，文件出现在此目录；
- MergedDir：容器挂载点 ，lowerdir和upperdir整合起来提供统一的视图给容器，作为根文件系统；
- WorkDir：用于实现copy_up操作。
