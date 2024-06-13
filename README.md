
# # DELL-OPTIPLEX-3020-MT-Hackintosh

Hackintosh for Build Up PC Dell Optiplex 3020 Mini Tower 

[![](https://github.com/anggamdev/m910s-rx550-lexa/blob/main/Lenovo%20ThinkCentre%20M910s.jpg)](http:https://github.com/anggamdev/m910s-rx550-lexa/blob/main/Lenovo%20ThinkCentre%20M910s.jpg//)
### Boot :

- OpenCore
- macOS BigSur 11.7.10
- Boot Mode : UEFI

### Tested Specifications :
- Intel® H81 Chipset
- Processor Intel® Core™ i3-4150 Haswell / Core™ i5-4570 Haswell
- Integrated Intel® HD Graphics 4400 / 4600
- Storage : SSD SATA Colorfull 240GB
- Storage : Hardisk 2.5 Seagate 1TB 
- RAM : V-Gen 2x8GB DDR3 1600MHz
- Audio: Realtek ALC662
- Ethernet Card:  Realtek® RTL8151GD
- Bootloader OpenCore 0.9.7
- OS BigSur 11.7.10
- [Installer Olarila](https://www.olarila.com/topic/6278-olarila-vanilla-images-macos-installer/)




### Work :
- QE/CI Intel® HD Graphics 4400 / 4600 Haswell
- Restart and Shutdown
- Sleep and Wake
- CPU Power Management
- Ethernet
- Audio Jack and Internal Mic (Front & Rear)
- Display Output : Display Port 
- Brightness : use [Monitor Control](https://github.com/MonitorControl/MonitorControl#readme "Monitor Control")
- All USB Ports
- Etc

### Not Work :-(

- d-Sub/VGA Port

### [Download EFI](https://github.com/anggamdev/m910s-rx550-lexa/releases/tag/0.1) 

## Note :
- Please Generate SMBIOS with Tutorial [https://dortania.github.io/OpenCore-Install-Guide/extras/smbios-support.html#imac](http:https://dortania.github.io/OpenCore-Install-Guide/extras/smbios-support.html#imac// "https://dortania.github.io/OpenCore-Install-Guide/extras/smbios-support.html#imac")

## Important !!

- Boot into the USB drive. OpenCore should launch now, giving you some boot options
- Quickly press an up or down arrow, because OC will boot the default option after a few seconds, and we are not ready to boot the installer yet.
- If you've booted Clover on this machine before, choose Reset NVRAM to clear the NVRAM variables. It is the last boot option in OpenCore.
- Select modGRUBShell.efi

Now you should be in a grub shell, which is indicated by the

```
grub>
``` 

prompt. We need to execute all the commands below. Pay special attention to run the commands that are meant for your computer. If you mismatch these commands, reset the motherboard, as applying the wrong variables will cause undefined behavior. See note after the section on how to do it. Keep in mind, resetting the NVRAM via OpenCore will not affect these values.



### Disable CFG Lock:

``` 
setup_var 0xD9E 0x0  
```

### Set DVMT pre-alloc to 64MB

``` 
setup_var 0x263 0x2
``` 

### Enable EHCI hand-off

``` 
setup_var 0x2 0x1
setup_var 0x144 0x1
setup_var 0x15A 0x2
setup_var 0x146 0x0
setup_var 0x147 0x0

```

### Reboot

``` 
reboot
```

Thanks to varszegimarcell 
