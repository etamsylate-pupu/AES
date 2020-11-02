#### description

Windows 10环境；C语言实现ECB、CBC、CFB、OFB四种工作模式的AES加解密，并生成 5MB 的随机测试数据，连续加密、解密 20 次，输出每种模式的加密和解密的总时间（毫秒）和速度（MByte/ 秒）

des_plain.txt：明文文件，32字节，256bit。

16进制表示为：43727970746F67726170687920616E64204E6574776F726B5365637572697479

des_key.txt：密钥文件，16字节，128bit。

16进制表示为：57696C6C69616D5374616C6C696E6773 

des_iv.txt：向量文件，16字节，128bit。

16进制表示为：5072656E7469636548616C6C496E632E 

des_Cipher.txt：密文文件，32字节，256bit。用来保存密文

​	ECB模式：DB727AC6624F3699CBFC4F0F890832B8A4B1DCA1F52EF8E4CE0FD12E307476C6

​	CBC模式：9B0048990511252F5E1088663F8CB038A21952EAC6D2C27546369FCA0136BF04

​	CFB模式：EAC2DD6334E8FA07FDAB477ABA1628A93AFAAAD753B7E05CD59548A2927BDA97

​	OFB模式：EA4641614F3CDECD2161737A39551FE2E43A54E563ED8E6B7580879BE72A5391

#### step

1. 运行.c文件，生成.exe文件（已提供.exe文件，可不运行.c文件）；

2. 打开cmd，进入.exe文件所在目录；

3. 命令行指定明文文件、密钥文件、初始化向量文件的位置和名称、加密的操作模式以及加密完成后密文文件的位置和名称

   命令行具体格式为：e1aes -p plainfile -k keyfile [-v vifile] -m mode -c cipherfile 

   参数： 

   ​		-p plainfile 指定明文文件的位置和名称

   ​		-k keyfile 指定密钥文件的位置和名称 

   ​		-v vifile 指定初始化向量文件的位置和名称

   ​		-m mode 指定加密的操作模式

   ​		-c cipherfile 指定密文文件的位置和名称 

   eg：AES.exe -p AES_plain.txt -k AES_key.txt -v AES_iv.txt -m ECB -c AES_Cipher.txt

#### result

​	CFB和OFB分组为8位，ECB和CBC分组为128位，后者与前者相比连续20次加解密总时间倍数大致为16

 

 
