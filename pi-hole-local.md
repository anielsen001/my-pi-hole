## run a pi-hole on a local docker container

- Official docker-pi-hole <https://github.com/pi-hole/docker-pi-hole>
- Blog: <https://pawelurbanek.com/pihole-local-computer>
- GitHub: <https://github.com/pawurb/pi-hole-docker-compose>
- https://adamtheautomator.com/pi-hole-in-docker/

##  Run a pi-hole locally

Pull the container
```bash
docker pull pihole/pihole
```

Clone the docker-pi-hole repo 
```bash
git clone https://github.com/pi-hole/docker-pi-hole
```

Copy the example file to a local version
```bash
cp docker-pi-hole/examples/docker-compose.yml.example ./docker-compose-local.yml
```

