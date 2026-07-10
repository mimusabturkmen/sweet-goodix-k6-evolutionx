# Redmi Note 10 Pro / sweet - Goodix GT9896 K6 support for Evolution X

This repository documents the Goodix GT9896 K6 touchscreen work used for an unofficial Evolution X build for Xiaomi Redmi Note 10 Pro / sweet.

## Status

Tested on Xiaomi Redmi Note 10 Pro / sweet with Goodix GT9896 K6 panel.

Working:
- ROM boots
- Touchscreen works in system
- Touchscreen works in OrangeFox recovery
- Wi-Fi works
- SIM / mobile network works
- Brightness and rotation look normal after reboot

## Build

- ROM: Evolution X 16.0 / 11.8 unofficial
- Device: sweet
- Kernel: LineageOS sm6150 kernel base
- Main fix: Goodix K6 coordinate normalization in kernel driver

## Goodix K6 changes

- Import Goodix GT9896 K6 driver/firmware changes
- Enable `CONFIG_TOUCHSCREEN_GOODIX_GTX9896_K6=y`
- Normalize K6 coordinates in kernel driver:
  - `x >>= 3`
  - `y >>= 3`

## Important notes

Do not flash Magisk as a recovery ZIP on this build. In testing, Magisk 30.7 recovery flash caused grey/black screen behavior. If root is needed, use Magisk APK boot.img patch method and keep the clean boot.img available for recovery.

## Files not included

This repository does not include:
- ROM ZIP
- boot/recovery/dtbo/vbmeta images
- proprietary vendor blobs
- out/ build directory
- private keys or credentials
