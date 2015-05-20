## Crontab

__命令__

```sh
# 创建 (/var/spool/cron/<filename>)
crontab <filename>
# 列出crontab文件
crontab -l
# 编辑
crontab -e
# 删除
crontab -r
# $HOME下有备份
```

__crontab中的输出配置__

crontab中经常配置运行脚本输出为：`>/dev/null 2>&1`，来避免crontab运行中有内容输出。

shell命令的结果可以通过`>`的形式来定义输出

* `/dev/null` 代表空设备文件
* `>` 代表重定向到哪里，例如：`echo "123" > /home/123.txt`
* `1` 表示stdout标准输出，系统默认值是1，所以`>/dev/null`等同于`1>/dev/null`
* `2` 表示stderr标准错误
* `&` 表示等同于的意思，`2>&1`，表示2的输出重定向等同于1

那么重定向输出语句的含义：

* `1>/dev/null` 首先表示标准输出重定向到空设备文件，也就是不输出任何信息到终端，不显示任何信息。
* `2>&1` 表示标准错误输出重定向等同于标准输出，因为之前标准输出已经重定向到了空设备文件，所以标准错误输出也重定向到空设备文件。

__格式__

* | * | * | * | * | command to be executed
- | - | - | - | - | ----------------------
minute [0-59] | hour [0-23] | day of month [1-31] | month [1-12] | day of week [0-7] | 需要执行的命令

__写法__

```sh
* * * * * /path/to/your/cmd.sh
@hourly /path/to/your/cmd.sh
```

string | meaning
------ | -------
@reboot   | Run once, at startup.
@yearly   | Run once a year, "0 0 1 1 *".
@annually | (same as @yearly)
@monthly  | Run once a month, "0 0 1 * *".
@weekly   | Run once a week, "0 0 * * 0".
@daily    | Run once a day, "0 0 * * *".
@midnight | (same as @daily)
@hourly   | Run once an hour, "0 * * * *".
