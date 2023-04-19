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
git clone git@github.com:sky-shine/t113_mangopi_dts.git
```
## Then place files to SDK

``` sh
cp -r t113_mangopi_dts/device/config/chips/t113/configs/mq_r device/config/chips/t113/configs

cp -r t113_mangopi_dts/target/allwinner/t113-mq_r target/allwinner

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

Some package changes might be useful...

[fw_printenv stdout to null](https://github.com/mangopi-sbc/tina-package/commit/7f4072cfded97aef8d6ace123056f9f8a7dcebfc)

[change sockets from /etc/wifi to /var](https://github.com/mangopi-sbc/tina-package/commit/4a81e6d966dec48163d68ec35942d5fc1ef94e87)

[change the endev to event2](https://github.com/mangopi-sbc/tina-package/commit/5fc4928fb92380939a024b02127c8715d74212db)
