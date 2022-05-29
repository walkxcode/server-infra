<h1 align="center">
  💾 Connecting NAS Storage
</h1>

<details>
<summary><b>Table of Contents</b></summary>

- [Mounting](#mounting)
- [Auto Mount on boot](#auto-mount-on-boot)

</details>

## Mounting
```bash
sudo apt install nfs-common
```

```bash
sudo mkdir /data && \
sudo mkdir /data/nas
```

```bash
sudo mount -t nfs 10.0.0.4:/volume1/shared /data/nas
```

## Auto Mount on boot
```bash
sudo nano /etc/fstab
```

1. Add the following line
```txt
10.0.0.4:/volume1/shared /data/nas nfs rsize=8192,wsize=8192,timeo=14,intr
```
2. Press <kbd>Ctrl</kbd>+<kbd>X</kbd> and press <kbd>Y</kbd> to close and save

