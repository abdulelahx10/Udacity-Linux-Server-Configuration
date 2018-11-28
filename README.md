# Udacity Linux Server Configuration

In this project I installed a Linux server and prepared it to host my web applications in AWS lightsail.

## Server Info
IP address: 3.121.241.119

SSH port: 2200

Application URL: <http://ec2-3-121-241-119.eu-central-1.compute.amazonaws.com/>.

## configuration changes

- Updated all installed packages with:
```
sudo apt-get update
sudo apt-get upgrade
```

- Configured sshd_config to change PORT SSH from 22 to 2200 and disable root with:
```
sudo nano /etc/ssh/sshd_config
```

- Only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123) with:

```
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 2200/tcp
sudo ufw allow 80/tcp
sudo ufw allow 123/udp
sudo ufw enable
```

- created grager user and giving him sudo with:
```
sudo adduser grader
sudo nano /etc/sudoers.d/grader
```
then add to it:
```
grader ALL=(ALL:ALL) ALL
```

## third-party resources used

many library like Flask, sqlalchemy...

to install:

```
pip3 install flask
pip3 install sqlalchemy
pip3 install oauth2client
pip3 install httplib2
```


## Authors

* **Abdulelah Alshalhoub** - *Initial work* - [abdulelahx10](https://github.com/abdulelahx10)
