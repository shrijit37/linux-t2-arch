linux-t2 — BCM4377 D3-ACK suspend quirk ∕ T2 Macs
========

Arch Linux package for Linux kernel with bleeding edge T2 Mac support.

This fork carries one quirk on top of the community linux-t2 kernel:
a BCM4377 Wi-Fi suspend fix for T2 Macs where the chip never acknowledges
HOST_D3_INFORM. Without it system suspend aborts; with it the mailbox
interrupt is masked and resume cold-reprobes instead.

Tested on: MacBookPro16,3 (A2289) · MacBookPro15,4 (A2159) ·
MacBookAir9,1 (Intel 2020, A2179). Applies to any T2 Mac with the
BCM4377 (Wi-Fi/BT combo) — all other models see no change.

Tracked upstream: https://github.com/NoaHimesaka1873/linux-t2-arch

To build yourself:

```sh
git clone https://github.com/shrijit37/linux-t2-arch
cd linux-t2-arch
makepkg -si
```

Or you can `sudo pacman -U` the packages Github CI builds, which can be
found on the releases page, or nothing if you have followed T2Linux guide
properly, even better!