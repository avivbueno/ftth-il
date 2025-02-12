# Israeli FTTH Plan Technical Details

Fiber-to-the-Home (FTTH) in Israel is provided to private consumers by several different telecom companies:

  - [Bezeq](https://www.bezeq.co.il/)
  - [Partner](https://www.partner.co.il/)
  - [Cellcom](https://cellcom.co.il/)
  - [Unlimited](https://www.unlimited.net.il/)

Each uses slightly different infrastructure and configurations. This repository documents the technical details for each telecom. Additionally, the goal for this repo is to provide details on the performance of each provider so that private customers can make smart decisions that consider which provider offers the best service.

## Partner

Partner markets their service as "private fiber" which means they use P2P instead of GPON. Effectively, most users do not notice significant performance speedup.

The fiber connection used is a single-mode simplex BiDi (WDM) LC-terminated fiber that uses 1490nm wavelength for TX and 1310nm for RX.

The reference SFP module that Partner provides is the [OPKAS1004](datasheets/OPKAS1004%20-%20DS_SFP-31W2Bah-DR(OPKAS1004)_SP.pdf).

### Devices

| Image | Model | Description | Status |
| ----- | ----- | ----------- | ------ |
| <img src="imgs/OPKAS1004.01.png" width="100"> | [OPKAS1004](datasheets/OPKAS1004%20-%20DS_SFP-31W2Bah-DR(OPKAS1004)_SP.pdf) | SFP-31W2Bah(SM-10)-TX1490 RX1310-Purpule | :heavy_check_mark: Reference |
| <img src="imgs/75336.main.jpg" width="100"> | [FS.com #75336](https://www.fs.com/products/75336.html) | Generic Compatible 1000BASE-BX BiDi SFP 1490nm-TX/1310nm-RX 10km DOM LC SMF Transceiver Module | :heavy_check_mark: Tested |
| <img src="imgs/40442.main.jpg" width="100"> | [FS.com #40442](https://www.fs.com/products/40442.html) | LC UPC to LC UPC Simplex OS2 Single Mode PVC (OFNR) 2.0mm Fiber Optic Patch Cable | :heavy_check_mark: Tested |

## Bezeq

Bezeq deploys GPON networks, and [publishes the following devices](datasheets/gpon.pdf) that are tested and "approved" for use:

```
|     Manufacturer        |     Appliance Type |     Model          | Supported Firmware Versions                                                    |
|-------------------------|--------------------|--------------------|--------------------------------------------------------------------------------|
|     Nokia               |     SFP ONT        |     G-010S-A       |     3FE47111AGAA92        3FE46398BGCB22                                       |
|     Nokia               |     SFP ONT        |     G-010S-Q       |     3FE49494AOCK21                                                             |
|     CIG                 |     SFP ONT        |     G97-S          |     R4.2.104.035a                                                              |
|     HT                  |     SFP ONT        |     HT-25SPON      |     V1.0.2.3                                                                   |
|     Adtran              |     BRIDGE ONT     |     SDX611         |     V1.3.4      V1.3.5                                                         |
|     Nokia               |     BRIDGE ONT     |     G-010G-P/Q     |     3FE45655AOCK88        3FE45655BOCK71                                       |
|     ZTE                 |     BRIDGE ONT     |     F601           |     V6.0.1P1T12                                                                |
|     HALNY               |     BRIDGE ONT     |     HL-1GE         |     V2.0.22b                                                                   |
|     Heights Telecom     |     CPE GW ONT     |     CPE-B2         |     BZG_360.1011                                                               |
|     Heights Telecom     |     CPE GW ONT     |     HT-360AXG      |     XF_360.13003                                                               |
|     Heights Telecom     |     CPE GW ONT     |     HT-360AXI      |     YES_H_1303                                                                 |
|     Accel               |     CPE GW ONT     |     FAST5670       |     SGFs10000219                                                               |
|     Accel               |     CPE GW ONT     |     Fast5657IL     |     SGDg100000099      SGDg100000102      SGDg100000106      SGDg100000108     |
|     Accel               |     CPE GW ONT     |     Fast5670IL     |     SGFz10000005                                                               |
|     Accel               |     CPE GW ONT     |     Fast5670IL     |     SGFx10000017                                                               |
|     Accel               |     CPE GW ONT     |     FAST5670       |     SGFy10000075                                                               |
|     HALNY               |     CPE GW ONT     |     HL-4GQVS2      |     V3.0.18                                                                    |
|     Technicolor         |     CPE GW ONT     |     FGA2233        |     2233.19.4.1                                                                |
```

The Nokia G-010S-A has been partially reverse engineered as documented in https://github.com/hwti/G-010S-A (also see the [official datasheet](datasheets/ale-gpon-nokia-ont-g-010s-a-datasheet-en.pdf))

Another datasheet available is for the [CIG G97-S](datasheets/G-97S_DataSheet_V2.pdf)

There is a long thread at https://htmag.co.il/phpbb/viewtopic.php?f=62&t=367574 which documents usage of Bezeq GPON with custom 2.5G equipment (Hebrew) 
