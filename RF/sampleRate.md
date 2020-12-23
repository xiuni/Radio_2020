# NR 5G 带宽与采样率的关系
+ 30K SCS NR5G
|带宽|采样率|RB数量|RE数量|NFFT|
|:---|:---|:---|:---|:---|
|100M|122.88M|273|3276|4096|
|80M|122.88M|217|2604|4096|
|60M|122.88M|162|1944|4096|
|50M|61.44M|133|1596|2048|
|40M|61.44M|106|1273|2048|
|20M|30.72M|51|612|1024|

+ 每个 sample 的周期多长？
	- 5G_NR_100M, 1s = 12288000*100 UTU  1s/122.88M = 12288000*100 UTU/122880000 = 10 UTU
	- 5G_NR_50M, 1s/61.44MHz,  所以一个sample 的周期 就是 20UTU，
	- 5G_NR_20M, 1s/30.72MHz, 所以一个sample 的周期 就是 40UTU，

+ NFFT = SampleRate/SCS

# CP 长度计算
- Ts
- Tc
- K=Ts/Tc = 64 (SCS= 30Khz)
- 1 UTU = 1.6Tc, 1 Ts = 40 UTU
- $$ N_(cp,l)^u = 512K *2^-u $$


# 一个symbol 的时间
- 30Khz 一个slot 10ms/20 = 0.5ms = 500us = 6144000 UTU
- 一个slot 14 个symbol，所以平均来说， 每个symbol的时间长度为： 500us/14 约等于 35.7us
- 精确地说， 第一个symbol 的CP 长度不同( 相差 16*K Tc = 640UTU )：
	- Tsymbol(first) =  44480 UTU = 36.198us
	- Tsymbol(2~14) = 43840 UTU =  35.677us

