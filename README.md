# modify_ulimit

## 脚本描述
Author:       Apt
Version:      1.3
Date:         2023.03.26
Description:  批量修改 ulimit 配置项


## 实现功能
1. 备份原文件
2. 修改 /etc/security/limits.conf 配置文件，配置 core、nofile、nproc 的值。预期值：
    core 102400
    nofile 65535
    nproc 65535
3. 3个参数值如果没有配置全局则加上，如果配置了则判断是否符合标准预期，如果小于预期则修改成预期值，如果大于预期值则不再进行修改。
4. 如果3个参数值额外针对用户进行了配置，则先配置的值是否符合标准预期，如果小于预期则修改成预期值，如果大于预期值则不再进行修改。


## 脚本代码逻辑
1. 检查当前的配置内容；
2. 备份原配置文件并加上时间戳；
3. 修改配置参数数值，比预设值小的话则修改为预设值，比预设值大则不修改；
    core 102400
    nofile 65535
    nproc 65535
4. 输出修改后的配置内容；


## 其他说明
预设值设置文件路径：
roles/modify_limits_conf/defaults/main.yml
