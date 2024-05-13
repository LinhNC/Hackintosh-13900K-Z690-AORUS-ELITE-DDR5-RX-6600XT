## Sunset rEFInd Theme

[rEFInd](http://www.rodsbooks.com/refind/) is a boot manager for UEFI systems and scans for kernels & EFI at boot.

![rEFInd Sunset 1](https://i.imgur.com/TcoNQeg.jpg)

![rEFInd Sunset 2](https://i.imgur.com/2NBuuaR.jpg)

### Usage

 1. Locate your refind EFI directory. This is commonly `/boot/EFI/refind`
    though it will depend on where you mount your ESP and where rEFInd is
    installed.

 2. Create a folder called `themes` inside it, if it doesn't already exist

 3. Clone this repository into the `themes` directory.

 4. To enable the theme add `include themes/rEFInd-sunset/theme.conf` at the end of
    `refind.conf`.
    
Entries should be autodetected and shown with the proper icons.

Manual entry can be done via `menuentry` option.

Example:

```
menuentry "Windows" {
	icon /EFI/refind/themes/rEFInd-sunset/icons/os_windows.png
	loader /EFI/Microsoft/Boot/bootmgfw.efi
}
```

Other examples are in the `refind.conf` file.

### Attributions

OS Icons are from [munlik's](https://github.com/munlik/refind-theme-regular) repository and self made.
