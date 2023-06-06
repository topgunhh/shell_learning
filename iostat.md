## iostat
```[topgun@localhost shell_learning]$ iostat
Linux 3.10.0-1160.el7.x86_64 (localhost.localdomain)    06/06/2023      _x86_64_        (8 CPU)

avg-cpu:  %user   %nice %system %iowait  %steal   %idle
           0.01    0.00    0.01    0.00    0.00   99.99

Device:            tps    kB_read/s    kB_wrtn/s    kB_read    kB_wrtn
vda               0.05         1.21         1.13     412966     385847
scd0              0.00         0.00         0.00       1028          0
dm-0              0.04         0.89         0.62     302991     211254
dm-1              0.00         0.01         0.00       2204          0
dm-2              0.01         0.23         0.51      77967     172504
```



```
[topgun@localhost shell_learning]$ cat 1.txt | tac | sed -n '1,/Device/p' | sed '$d' | tac | grep -v "^$" | awk '{print $4}' | xargs | sed "s/ /+/g" | bc
2.15

# sed -n '1,/Device/p'  : 打印第一行到Device 所在行
# sed '$d'              ：去掉最后一行
# grep -v "^$"          ：过滤出空行，取反
# tac                   ：反向输出
# xargs                 ：多行变单行
# bc                    ：将得出的值传给bc
```