<h1 align="center">
  📝 Configuring the OS
</h1>

<details>
<summary><b>Table of Contents</b></summary>

- [1. Updating the system](#1-updating-the-system)
- [2. Changing the SSH port](#2-changing-the-ssh-port)
- [3. Installing useful applications](#3-installing-useful-applications)
- [4. Installing and Configuring Samba](#4-installing-and-configuring-samba)
- [5. Reboot the system](#5-reboot-the-system)

</details>

## 1. Updating the system
```bash
sudo apt update && sudo apt full-upgrade -y
```

## 2. Changing the SSH port
```bash
sudo nano /etc/ssh/sshd_config
```

1. Uncomment `Line 15` and change the Port
2. Press <kbd>Ctrl</kbd>+<kbd>X</kbd> and press <kbd>Y</kbd> to close and save
3. Restart the SSH service using `sudo systemctl restart ssh.service`
4. Quit the SSH session and reconnect

## 3. Installing useful applications
```bash
sudo apt install git python3 python3-pip -y
```

## 4. Installing and Configuring Samba

```bash
sudo apt-get install samba samba-common-bin -y
```
---

```bash
sudo nano /etc/samba/smb.conf
```

1. Add the following the the bottom of the file
```txt
[jupiter]
path = /
writeable=Yes
create mask=0777
directory mask=0777
public=no
```
2. Press <kbd>Ctrl</kbd>+<kbd>X</kbd> and press <kbd>Y</kbd> to close and save
3. `sudo smbpasswd -a walkx`
   1. Choose a password for your share
4. `sudo systemctl restart smbd`

## 5. Reboot the system
```bash
sudo reboot now
```
