# PKCS#11 Settings

This file contains information related to PKCS#11 for communication with underlying hardware crypto device.

````toml
# Unique name of the hardware crypto profile.
name = "hardware_crypto_profile"

# PKCS#11 module name. Update the module name with actual value
module_name = "/opt/homebrew/opt/softhsm/lib/softhsm/libsofthsm2.so"

# PKCS#11 slot. Update the slot value with actual value
slot = 535428866

# PKCS#11 pin.
pin = "<PIN>"
````
