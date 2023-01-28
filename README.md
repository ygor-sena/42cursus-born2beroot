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

This project introduces the student to the wonderful world of virtualization. It was possible to chose between `Debian` and `CentOS` to be set up in `VirtualBox`. By July 26th 2022, this project was done in `Debian` with its most recent stable release (v11.4) since it's easier for first-time travelers learning this topic and it receives a lot of updates and new features.

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

- About Debian bugs:
  - https://unix.stackexchange.com/questions/204371/debian-error-message-unable-to-find-lvm-volume-but-then-boots-successfully

- About important concepts necessary to do the project:
  - sudoer manual: https://www.sudo.ws/docs/man/1.8.14/sudoers.man/
  - https://linuxhint.com/whatis_logical_volume_management/ e https://opensource.com/business/16/9/linux-users-guide-lvm
  - O que é ModRewrite: https://www.seobility.net/en/wiki/Mod_Rewrite
  - O que é SEO friendly? https://www.seobility.net/en/wiki/SEO-friendly_URLs
  - O que é CPU Load average? https://community.tenable.com/s/article/What-is-CPU-Load-Average
  - Como usar SCP: https://linuxize.com/post/how-to-use-scp-command-to-securely-transfer-files/
  - Diferença entre apt e aptitude? https://www.tecmint.com/difference-between-apt-and-aptitude/
  - https://www.sudo.ws/docs/man/1.8.14/sudoers.man/
  - Como verificar autenticidade de uma uma imagem Debian: https://www.debian.org/CD/verify
Sobre pontos de montagem: https://www.debian.org/releases/stable/amd64/ch06s03.en.html#di-partition e https://www.debian.org/releases/stable/amd64/apcs01.en.html
  - Melhor site sobre Shell em português: https://aurelio.net/shell/
  - Como usar crontab: https://linuxhandbook.com/crontab/
  - Sobre lsblk, MAJ:MIN e dispositivos https://superuser.com/questions/778686/linux-lsblk-output
  - Para que serve cada pasta e sistema de montagem: https://techencyclopedia.wordpress.com/2020/04/21/debian-10-manual-partition-for-boot-swap-root-home-tmp-srv-var-var-mail-var-log/ e https://tldp.org/HOWTO/Multi-Disk-HOWTO.html
  - https://www.freecodecamp.org/news/types-of-hard-drives-sata-pata-scsi-and-more-2/
  - Como verificar autenticidade de uma uma imagem Debian: https://www.debian.org/CD/verify
  - Sobre pontos de montagem: https://www.debian.org/releases/stable/amd64/ch06s03.en.html#di-partition e https://www.debian.org/releases/stable/amd64/apcs01.en.html
  
- Guides from other students that really helped:
  - https://baigal.medium.com/born2beroot-e6e26dfb50ac
  - https://githubmemory.com/repo/hanshazairi/42-born2beroot#setting-up-a-cron-job
  - https://github.com/caroldaniel/42sp-cursus-born2beroot/blob/master/guides/CentOS-en.md#Passwd

- About the bonus project:
  - Como instalar as partições do bônus: https://www.youtube.com/watch?v=2w-2MX5QrQw
  - Como instalar WordPress com Lighttpd Ubuntu 20.04: https://www.how2shout.com/linux/install-wordpress-on-lighttpd-web-server-ubuntu/ e https://www.atlantic.net/dedicated-server-hosting/how-to-install-wordpress-with-lighttpd-web-server-on-ubuntu-20-04/ e 
  - Como resetar a senha do Maria DB: https://www.digitalocean.com/community/tutorials/how-to-reset-your-mysql-or-mariadb-root-password
  - https://www.vivaolinux.com.br/artigo/Fail2ban-no-Debian-Instalacao-e-Configuracao
