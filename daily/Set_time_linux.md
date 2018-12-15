### 一、查看当前服务器时区&列出时区并设置时区

```
# timedatectl
# timedatectl list-timezones
# timedatectl set-timezone Asia/Shanghai
```
### 二、时间时区概念理解
> GMT、UTC、CST、DST
```
UTC：

整个地球分为二十四时区，每个时区都有自己的本地时间，在国际无线电通信场合，为了统一起见，使用一个统一的时间，称为通用协调时(UTC:Universal Time Coordinated)。

GMT：

格林威治标准时间 (Greenwich Mean Time)指位于英国伦敦郊区的皇家格林尼治天文台的标准时间，因为本初子午线被定义在通过那里的经线(UTC与GMT时间基本相同)。

CST：

中国标准时间 (China Standard Time)

GMT + 8 = UTC + 8 = CST

DST：

夏令时(Daylight Saving Time) 指在夏天太阳升起的比较早时，将时间拨快一小时，以提早日光的使用（中国不使用）。
```

### 三、将系统时间写入硬件时间
```
hwclock --systohc
```
