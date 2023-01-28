<p align="center">
    <img src="https://user-images.githubusercontent.com/102881479/215289147-dafd06d4-38bf-48f3-ad30-381d737de011.png">
</p>
<p align="center">
    <img src="https://img.shields.io/badge/OS-Linux-blue" alt="OS">
    <img src="https://img.shields.io/badge/Language-C%20%7C%20C%2B%2B-blue.svg" alt="Language">
    <img src="https://img.shields.io/badge/Grade-125%2F100-brightgreen.svg" alt="Grade">
    <img src="https://img.shields.io/badge/Status-Completed-brightgreen.svg" alt="Status">
</p>

## Introduction

This project introduces the student to the wonderful world of virtualization. It was possible to choose between `Debian` and `CentOS` to be set up in `VirtualBox`. By July 26th 2022, this project was done in `Debian` with its most recent stable release (v11.4) since it's easier for first-time travelers learning this topic and it receives a lot of updates and new features.

For the bonus implementation, [fail2ban](https://www.fail2ban.org/wiki/index.php/Main_Page) was set up. It's a service that bans IPs after malicious signs, i.e. too many password failures.

## Requirements

#### Mandatory:

- ✅ Create at least 2 encrypted partitions using LVM.
- ✅ A SSH service will be running on port 4242 only. It must not be possible to connect using SSH as root.
- ✅ Configure UFW firewall to leave only port 4242 open.
- ✅ Implement a strong password policy, that comply with the following requirements:

  - The password has to expire every 30 days.
  - The minimum number of days allowed before the modification of a password will be set to 2.
  - The user has to receive a warning message 7 days before their password expires.
  - The password must be at least 10 characters long. It must contain an uppercase letter, a lowercase letter, and a number. Also, it must not contain more than 3 consecutive identical characters.
  - The password must not include the name of the user.
  - The following rule does not apply to the root password: The password must have at least 7 characters that are not part of the former password.
  - The `root` password has to comply with this policy.

- ✅ Install and configure `sudo` following strict rules, that comply with the following requirements:
  - Authentication using `sudo` has to be limited to 3 attempts in the event of an incorrect password.
  - A custom message of your choice has to be displayed if an error due to a wrong password occurs when using `sudo`.
  - Each action using `sudo` has to be archived, both inputs and outputs. The log file has to be saved in the `/var/log/sudo/` folder.
  - The TTY mode has to be enabled for security reasons.
  - The paths that can be used by sudo must be restricted. For example: `/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin`
- ✅ In addition to `root`, a `user` has to be present and it must belong to `user42` and `sudo` groups.
- ✅ Create a script developed in `bash` that display some operating system information every 10 minutes since server startup.

#### Bonus:

- ✅ Set up `root`, `swap`, `home`, `var`, `srv`, `tmp` and `var--log` encrypted partitions using LVM.
- ✅ Set up a functional WordPress website with the following services: `lighttpd`, `MariaDB` and `PHP`.
- ✅ Set up a service of your choice that you think is useful (NGINX / Apache2 excluded!).

## References

- Books:
  - SIQUEIRA, Luciano. Certificação LPI-1 101-102. Rio de Janeiro, 2015.
  - SILBERSCHATZ, Abraham; GALVIN, Peter; GAGNE, Peter. Fundamentos de sistemas operacionais. 2015.

- About Debian bugs:
  - [Debian error message: "Unable to find LVM volume", but then boots successfully](https://unix.stackexchange.com/questions/204371/debian-error-message-unable-to-find-lvm-volume-but-then-boots-successfully) by Stack Exchange

- About important concepts necessary to do the project:
  - [Sudoer manual](https://www.sudo.ws/docs/man/1.8.14/sudoers.man/)
  - [What is LVM (Logical Volume Management), and what are its Benefits?](https://linuxhint.com/whatis_logical_volume_management/) by Karim Buzdar.
  - [A Linux user's guide to Logical Volume Management](https://opensource.com/business/16/9/linux-users-guide-lvm) by David Both
  - [What is ModRewrite?](https://www.seobility.net/en/wiki/Mod_Rewrite) by Seobility Wiki.
  - [What is SEO Friendly?](https://www.seobility.net/en/wiki/SEO-friendly_URLs) by Seobility Wiki.
  - [What is CPU load average?](https://community.tenable.com/s/article/What-is-CPU-Load-Average) by Tenable Community.
  - [How to Use SCP Command to Securely Transfer Files](https://linuxize.com/post/how-to-use-scp-command-to-securely-transfer-files/) by Linuxize.
  - [What is the real difference between apt and aptitude?](https://www.tecmint.com/difference-between-apt-and-aptitude/) by Gunjit Khera.
  - Best Brazilian resource about shell: https://aurelio.net/shell/
  - [Understanding Crontab in Linux With Examples](https://linuxhandbook.com/crontab/) by Christopher Murray.
  - [Understanding lsblk output](https://superuser.com/questions/778686/linux-lsblk-output) by Stack Overflow.
  - [Debian 10 Manual Partition for /boot, /swap, root, /home, /tmp, /srv, /var, /var/mail, /var/log](https://techencyclopedia.wordpress.com/2020/04/21/debian-10-manual-partition-for-boot-swap-root-home-tmp-srv-var-var-mail-var-log/) by Techencyclopedia.
  - [Types of Hard Drives – SATA, PATA, SCSI, and SSD](https://www.freecodecamp.org/news/types-of-hard-drives-sata-pata-scsi-and-more-2/) by Kolade Chris.
  - [About mounting points size](https://www.debian.org/releases/stable/amd64/ch06s03.en.html#di-partition) by Official Debian GNU/Linux Installation Guide.
  
- Guides from other students that really helped:
  - [Born2beroot: 42 school project](https://baigal.medium.com/born2beroot-e6e26dfb50ac) by Baigalmaa Baatar.
  - [42cursus - Born2beroot](https://githubmemory.com/repo/hanshazairi/42-born2beroot#setting-up-a-cron-job) by hanshazairi.
  - [CentOS Linux 8 Guide](https://github.com/caroldaniel/42sp-cursus-born2beroot/blob/master/guides/CentOS-en.md#Passwd) by [caroldaniel](https://github.com/caroldaniel).

- About the bonus project:
  - [Born2beroot VB VM Installation (Bonus)](https://www.youtube.com/watch?v=2w-2MX5QrQw) by hanshazairi.
  - [How to install WordPress on Lighttpd web server - Ubuntu 20.04/18.04](https://www.how2shout.com/linux/install-wordpress-on-lighttpd-web-server-ubuntu/) Heyan Maurya.
  - [How to Install WordPress with Lighttpd Web Server on Ubuntu 20.04](https://www.atlantic.net/dedicated-server-hosting/how-to-install-wordpress-with-lighttpd-web-server-on-ubuntu-20-04/) by Hitesh Jethva.
  - [How To Reset Your MySQL or MariaDB Root Password](https://www.digitalocean.com/community/tutorials/how-to-reset-your-mysql-or-mariadb-root-password) by Mateusz Papiernik.
  - [Fail2ban no Debian: instalação e configuração](https://www.vivaolinux.com.br/artigo/Fail2ban-no-Debian-Instalacao-e-Configuracao) by [Diego Mendes Rodrigues](https://www.linkedin.com/in/diegomendesrodrigues/).
