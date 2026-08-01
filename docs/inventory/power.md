# Power

What the stack draws, by level. Useful for sizing a UPS, choosing where a power strip is needed, and knowing what a piece of gear actually costs to leave running.

**Rated** is the manufacturer's maximum, linked to its source. It is a ceiling, not a typical figure, and real draw is usually well under it. **Measured** is a reading taken at the outlet, with the date it was taken. The two are not interchangeable, so they stay in separate columns.

PoE devices draw through whatever powers them, so an access point's rated figure does not appear at its own outlet — it shows up in the budget of the injector or switch feeding it. Those rows note the source.

## Downstairs (ingress closet)

| Device | Rated | Measured | On | Notes |
|--------|-------|----------|----|-------|
| [gateway (USG)](https://dl.ubnt.com/datasheets/unifi/UniFi_Security_Gateway_DS.pdf) | 7 W | | | 12 V DC adapter |
| [switch-gateway (US-8-60W)](https://techspecs.ui.com/unifi/switching/us-8-60w) | 12 W | | | Excludes PoE output; 48 W PoE budget |
| [ap-kids (UK-Ultra)](https://techspecs.ui.com/unifi/wifi/uk-ultra) | 8 W | | | PoE from switch-gateway |

## Main (media cabinet)

| Device | Rated | Measured | On | Notes |
|--------|-------|----------|----|-------|
| [switch-media (USW-Flex-2.5G-5)](https://techspecs.ui.com/unifi/switching/usw-flex-2-5g-5) | 5 W | | | 5 W on USB-C, 6.4 W on PoE input; confirm which it uses |
| [ap-media (UAP-FlexHD)](https://techspecs.ui.com/unifi/wifi/uap-flexhd) | 10.5 W | | | PoE from its own injector |
| Samsung QN90F 43" | | | | |
| Xbox One S | | | | |
| Nintendo Switch | | | | |

## Upstairs

| Device | Rated | Measured | On | Notes |
|--------|-------|----------|----|-------|
| [switch-macmini (USW-Flex-2.5G-5)](https://techspecs.ui.com/unifi/switching/usw-flex-2-5g-5) | 5 W | | | 5 W on USB-C, 6.4 W on PoE input; confirm which it uses |
| macmini (2018) | | | | Measure idle and under Emby transcode separately |
| 18 TB drive (primary) | | | | |
| 18 TB drive (Time Machine clone) | | | | |

## Shelf

| Device | Rated | Measured | On | Notes |
|--------|-------|----------|----|-------|
| [UAP-AC-PRO](https://techspecs.ui.com/unifi/wifi/uap-ac-pro) | 9 W | | | Spare |

## Taking a measurement

Read at the outlet with a plug-in meter. Two figures are worth having for anything that varies with load: idle, and under the work it actually does. For the macmini that means an Emby transcode; for the gateway it means IPS running at line rate.

Totals are deliberately absent until enough rows are measured that a sum means something. Adding up rated maximums would overstate the real draw by a wide margin.

## Pending

The [Gateway Upgrade](/decisions/gateway-upgrade) changes several of these rows. Rated figures for the incoming hardware are in that record; measurements get taken and added here once it is installed.
