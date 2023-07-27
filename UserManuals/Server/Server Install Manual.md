
# Server Install Manual

## Table of Contents
1. [Installing Quota Package](#installing-quota-package)
2. [Installing Webmin](#installing-webmin)
3. [SSH Tunneling to Webmin(Optional)](#ssh-tunneling-to-webmin)
4. [Accessing Webmin](#accessing-webmin)
5. [Logging In](#logging-in)
6. [Setting Traditional Chinese (Optional)](#setting-traditional-chinese-optional)
7. [Setting Max Disk Usage for Each User](#setting-max-disk-usage-for-each-user)
8. [Checking Disk Access for Each User](#checking-disk-access-for-each-user)
9. [Setting Auto-Mount on Startup (Optional)](#setting-auto-mount-on-startup-optional)
10. [Locking NVIDIA Driver Version](#locking-nvidia-driver-version)

## Installing Quota Package
Quota is a package used to manage and enforce storage quotas on a filesystem. To install it, run the following commands in your terminal:

```bash
sudo apt-get update
sudo apt-get install quota
```

## Installing Webmin
Webmin is a web-based interface for system administration for Unix. You can download it from the [official website](https://webmin.com/download/). Alternatively, use the following commands to download and set up the repository:

```bash
curl -o setup-repos.sh https://raw.githubusercontent.com/webmin/webmin/master/setup-repos.sh
sh setup-repos.sh
```

## SSH Tunneling to Webmin(Optional)
If you are using SSH. To connect to Webmin remotely via SSH, run the following command, replacing "username", "remote_computer_IP", and "remote_port" with the appropriate values:

```bash
ssh -L 10000:localhost:10000 username@remote_computer_IP -p remote_port
```

## Accessing Webmin
Once the SSH tunnel is established, you can access Webmin by entering the following URL in your web browser:

```website
https://localhost:10000/
```

## Logging In
Use the username and password of your Ubuntu system to log in to Webmin.

## Setting Traditional Chinese (Optional)
You can optionally set the system language to Traditional Chinese. Follow the on-screen instructions after logging in.

## Setting Max Disk Usage for Each User
You can set the maximum disk usage for each user. This feature can help prevent a single user from consuming too much disk space.

Remember to set a limit for both the SSD and HDD:

- SSD: Not set yet
- HDD: 1TB

## Checking Disk Access for Each User
Ensure that each user can access the disk and has read/write permissions. Users must not be allowed to modify others' directories.

## Setting Auto-Mount on Startup (Optional)
You can optionally set the disk to automatically mount on system startup. Follow the on-screen instructions after logging into Webmin.

## Locking NVIDIA Driver Version
To prevent the NVIDIA driver from being automatically updated, lock the version with the following command:

```bash
sudo apt-mark hold nvidia-*
```