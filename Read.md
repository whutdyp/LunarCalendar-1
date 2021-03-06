下面描述的是阳历换算阴历的算法原理。

阳历，有很强的规律性。每年12个月，1、3、5、7、8、10、12月都为31天；2月份平年28天，能被4除尽的年份里为29天，但1900年为28天；其余月份为31天。

阴历，却没有这些规律可循。阴历分大小月，大月30天，小月29天，但一年中哪个月为大月，哪个月为小月，却是不定的。阴历每十年有4个润年，但哪一年为润年也是不定的。而润月中，哪个润月为大月，哪个为小月也是不定的。因此，推算阴历就没有一个统一的算法。

阴历是要靠天文观测的，因此上面这些不确定的数据，是可以从天文台得到的。

0x04bd8

要推算阴历，就要根据这些数据来推。

上面共15行，每行10个数据。每个数据代表一年，从阳历1900.1.31日起，为第一个数据年的开始，即阳历1900.1.31＝阴历0.1.1。150个数据可推150年的阴历，因此目前最大只能推算到2049年，以后的推导，还需要从天文台得到新的数据后才能推导，否则将出现误差。

要推算阴历，关键是理解这些数据的意义。

拿第一个数据来说，代表阳历1900.1.31为始的阴历0年，0x04bd8是5个16进制数，共20bit。

前4位，即0在这一年是润年时才有意义，它代表这年润月的大小月，为1则润大月，为0则润小月。
中间12位，即4bd，每位代表一个月，为1则为大月，为0则为小月。
最后4位，即8，代表这一年的润月月份，为0则不润。首4位要与末4位搭配使用。
