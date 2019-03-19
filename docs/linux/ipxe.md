# IPXE

## Netboot.xyz

Sometimes you can not be bothered to download the ISO for a linux install.

You can use [netboot.xyz](https://netboot.xyz) To download the initrd and kernel directly from the vendors. Otherwise you can use [the downloadable ISO](https://netboot.xyz/downloads/) to boot from.

If your boot envioment already contains IPXE, you can use



````
    dhcp #To obtain IP addr
    chain --autofree http://boot.netboot.xyz #to chainboot to IPXE
````