Added mangopi-sbc MQ Dual board level files for Tina Linux SDK D1-H

Copy board level files from mangopi: https://github.com/mangopi-sbc/Tina-Linux


# USE

## First: download and install Tina Linux SDK for D1-H

Tina Linux SDK install tutorial: https://d1.docs.aw-ol.com/study/study_3getsdk/

Another way to download SDK: https://bbs.aw-ol.com/topic/1034/

## Then: add Tina-on-patch: 

### Follow the README file: https://github.com/YuzukiHD/TinaAddons

Now D1-H SDK supports T113 chips, but it only supports Nezha T113 board.

To support Mangopi MQ-Dual, one more step is needed to be done.

## Download this repo and go to root of Tina Linux

``` sh
git@github.com:sky-shine/t113_mangopi_dts.git
```
## Then place files to SDK

``` sh
cp -r t113_mangopi_dts/device/config/chips/t113/configs/mq_r device/config/chips/t113/configs

cp -r t113_mangopi_dts/target/allwinner/t113-mq_r/ target/allwinner

#delete board file folder
rm -rf t113_mangopi_dts
``` 
## Now run:

``` sh
source build/envsetup.sh
lunch
```
You might see:
``` sh
4. t113_mq_r-tina
``` 
