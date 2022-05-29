<h1 align="center">
  🐳 Installing and Configuring Docker
</h1>

<details>
<summary><b>Table of Contents</b></summary>

- [Installing Docker](#installing-docker)
- [Installing Portainer](#installing-portainer)

</details>

## Installing Docker
```bash
sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release -y
```

```bash
sudo mkdir -p /etc/apt/keyrings
```

```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```bash
sudo apt-get update
```

```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

```bash
sudo chmod 666 /var/run/docker.sock
```

## Installing Portainer
Portainer helps you easily manage your docker contains in a web UI.

```bash
docker volume create portainer_data && \
docker run -d -p 9000:9000 -p 9443:9443 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer:/data portainer/portainer-ce:latest
```

*Tip: In portainer go to environments > local, and change the Public IP to your servers IP!*
