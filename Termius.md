## 安装教学

链接好路由器
复制好订阅号

termius先配置192.168.31.1的telnet登入方式，设置账号root密码及
```
https://ax6s-wifi-key.vercel.app/
```
对应路由器DN编号算出的密码
telnet设置好ssh，复制回车这三行
```
nvram set ssh_en=1 & nvram set uart_en=1 & nvram set boot_wait=on & nvram set bootdelay=3 & nvram set flag_try_sys1_failed=0 & nvram set flag_try_sys2_failed=1
nvram set flag_boot_rootfs=0 & nvram set "boot_fw1=run boot_rd_img;bootm"
nvram set flag_boot_success=1 & nvram commit & /etc/init.d/dropbear enable & /etc/init.d/dropbear start
```

接着账号密码连接选择ssh链接，安装源，如果不行官方找其它源
```
export url='http://shellclash.cf/' && wget -q -O /tmp/install.sh $url/install.sh  && sh /tmp/install.sh && source /etc/profile &> /dev/null
```
其它源参考ShellClash的github
教学参考，恩山论坛的一个整理集教学，不过这个shellclash安装源，下载解压失败，还其它源即可
```
https://qust.me/post/ax6s/
```

本机使用订阅号的可在官方网站下载，对应的客户端，及参考网站上的教学
