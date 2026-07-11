# Redmi Note 10 Pro sweet — Goodix K6 test results

## Result

Verified working.

## Included fixes

- Goodix GT9896 K6 touchscreen driver support
- Goodix K6 firmware
- 3-bit fixed-point coordinate normalization
- Continuous-splash DMS handoff fix

## Boot tests passed

- Flash sonrası ilk boot
- 5 system reboot
- 5 cold boot
- 60 Hz reboot
- 120 Hz reboot
- Charger-connected cold boot
- Charger-disconnected cold boot
- Repeated screen lock and wake
- Doze / ambient display test

## Previous failure

During continuous splash handoff, DSI_MODE_FLAG_DMS was added on the
first frame. dsi_display_prepare() rejected that state with -EINVAL,
causing controller reset, kickoff and display corruption failures.

## Excluded experiments

- Forced 60 Hz
- Doze hard-disable
- K6 OFF commands in LP mode
- Boot animation changes
- Gamma target-mode experiment

## Magisk compatibility

Verified working.

- Installed through OrangeFox recovery
- Root access confirmed with `su -c id`
- System reboot tests passed
- Cold boot tests passed
- No display corruption or black-screen regression observed

The earlier display failures initially attributed to Magisk were caused by
the continuous-splash DMS handoff bug.
