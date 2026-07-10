
# Build notes



Environment:

- Ubuntu 24.04 VM

- Evolution X manifest branch: bka

- Device: sweet

- Lunch target: lineage_sweet-bp4a-userdebug

- Build command: m evolution



Important locale exports:



```bash

export LANG=C.UTF-8

export LC_ALL=C.UTF-8

export LANGUAGE=C



Without this, Turkish locale may generate invalid Java sources such as ınt instead of int.



Build result:



BUILD_RESULT=0

Package completed successfully

