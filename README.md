# modify_ulimit

## 脚本描述
Author:       Apt
Version:      1.0
Date:         2023.02.21
Description:  批量修改 ulimit 配置项


## 脚本开发逻辑
1. 检查当前的配置内容；
2. 备份原配置文件并加上时间戳；
3. 修改ulimit配置数值，比预设值小的话则修改为预设值，比预设值大则不修改；
    core 102400
    nofile 65535
    nproc 65535
4. 输出修改后的配置内容；

## 其他说明
预设值设置文件路径：
roles/modify_limits_conf/defaults/main.yml
