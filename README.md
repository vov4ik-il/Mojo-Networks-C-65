# Mojo-Networks-C-65
OpenWRT support to Mojo Networks C-65 (Airtight C-65)

Flashing Instructions:
1. Setup TFTP sevrer with adress 192.168.1.100/24 on your local machine connected to Mojo Networks C-65 device.
2. Download "openwrt-ath79-generic-airtight_c-65-initramfs-kernel.bin" and "openwrt-ath79-generic-airtight_c-65-squashfs-sysupgrade.bin"
3. Verify chcksums - do it as the device will be bricked if this step is skipped and there was a problem with downloading.
4. Rename "openwrt-ath79-generic-airtight_c-65-initramfs-kernel.bin" it to "c65_atnboot.bin" and put it in TFTP server root directory.
5. Powercycle the unit (very short power interruption is required, less than 1 second or it might not work)
6. Wait about 90 seconds for the ram image to load.
7. Open a web browser and navigate to 192.168.1.1 for the router Web Interface and login with a blank password.
8. In the top menu click "System" -> "Backup/Flash Firmware"
9. Select "firmware" in "Save mtdblock contents" and click "Save mtdblock" - this is your only chance to save your current firmware to be able to go back to the original state!!! I would do it twice to make sure the file is not corrupt due to ethernet error!
 10. In "Flash new firmware image" browse and select "openwrt-ath79-generic-airtight_c-65-squashfs-sysupgrade.bin".
 11. Untick "Keep settings" and click "Flash firmware..."
12. Verify checksum with the original and click "Proceed"
13. Wait about 150 seconds for the router to flash (if you interrupt the power - you can brick it, however it is 80% recoverable if you repeat from step 5)
14. You just gave a new life to your Mojo Networks C-65 Wireless Access Point. Enjoy and considre donating to the project.

Back to original firmware:
1. Flash the file you had backed up in step 9 of flashing instructions.

Known limitations in this release:
1. Wireless 5G LED behavior is inverted (steady "on" means the radio is disabled).
2. Only one 16Mb flash chip is available (the unit has 2).
