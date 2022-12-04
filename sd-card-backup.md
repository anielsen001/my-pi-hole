
## copy image with dd
```
sudo dd if=/dev/mmcblk0 of=sdimage.img bs=4M
```

## shrink image
```
sudo ~/sw/PiShrink/pishrink.sh sdimage.img
```