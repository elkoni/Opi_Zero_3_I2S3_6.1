# Opi_Zero_3_I2S3_6.1
Orange Pi Zero 3 ( Allwinner H618 )  kernel 6.1.31-sun50iw9 I2S3 DT overlay

This DT overlay extends Opi_Zero_3_I2S3 repo to support 6.1.31 kernel based images.

Check [this picture](https://github.com/elkoni/Opi_Zero_3_I2S3/blob/main/OpiZero3_I2S_3_mixer.JPG) 
for ahubdam mixer settings.

DTS file "v2" fixes some errors with ubuntu jammy server 6.1 image.


It's been discovered, that LRCK freq and BCLK freq are half of needded  
48kHz and 3.072 MHz. A kernel pathch is provided to correct this ( ahub.patch ).  
Place patch in orangepi-build/userpatches/kernel/sun50iw9-next/ folder.  
There are some limits - pulseaudio default-sample-format should be s24le or s32le.  
The ahub driver seems to be work-in-progress, because HDMI audio is affected too.  

Upd:
A mode advanced patch can be used: https://github.com/warpme/minimyth2/blob/master/script/kernel/linux-6.5/files/0617-0608-sound-soc-sunxi-fix-no-Rch-and-slow-24bit.patch  

[Example image](https://drive.google.com/file/d/1IGGYXiJOH4IBwNMbRh2KacJHDskBaXr2/view?usp=drive_link) .  
Seems wpa_supplicant is missing.  
[Another one ( server )](https://drive.google.com/file/d/12EO4HEJs_PYDNvSbGz3h3Xyr2x2iXt5v/view?usp=drive_link) .  


