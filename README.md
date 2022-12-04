# Make image of old SD-Card for backup

If you wish to make a backup copy of an SD-Card before imaging for a new system, follow these:
[SD-Card backup instructions](sd-card-backup.md).


# Image with new OS for raspberry pi

```
rpi-imager
```
- select Raspbery Pi OS 32-bit for Pi 3B+
- select options and the username/password/hostname can be set along with wifi info if needed and ssh.

# Update OS 

```bash
sudo apt update
sudo apt upgrade 
```

# Install docker

Download the installation script and run:
```bash
curl -sSL https://get.docker.com -o get_docker.sh
sudo bash get_docker.sh
```

Add user pi to the docker user group
```bash
sudo usermod -aG docker pi
```

Logout and back in to make sure the group is setup.

Test docker
```bash
docker run hello-world
```

Set up docker to run on startup
```bash
sudo systemctl enable docker
```

# Install docker-compose

Basic requirements:
```bash
sudo apt install libffi-dev libssl-dev
sudo apt install python3-dev
sudo apt-get install -y python3 python3-pip
```

Install rust:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Install docker-compose, this step will take a while
```bash
pip3 install docker-compose
```



# Install pi-hole docker

```bash
git clone https://github.com/pi-hole/docker-pi-hole.git
```

Edit the `docker-compose.yml.example` in `examples`:
```bash
cd docker-pi-hole/examples
cp docker-compose.yml.example docker-compose.yml
```

- Set the password for the web interface
  

# References

0. R-Pi-Docker: https://pimylifeup.com/raspberry-pi-docker/
1. https://www.jfrog.com/connect/post/install-docker-compose-on-raspberry-pi/
2. Rust: https://www.rust-lang.org/tools/install
3. Pi-hole: https://github.com/pi-hole/docker-pi-hole
4. Docker: https://docs.docker.com/config/daemon/systemd/