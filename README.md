Samba
======
***

## Samba를 이용하여 윈도우(Host) / 리눅스(Guest) 공유폴더 설정하기
***

## 0. 기본
    sudo apt-get update
    sudo apt-get -y install samba
    sudo smbpasswd -a <계정명>

## 1. Samba 설정
    sudo cp /etc/samba/smb.conf /etc/samba/smb.conf_backup
    sudo vi /etc/samba/smb.conf
        [Workspace]
                path = /home/**<리눅스계정>**/**samba_workspace**
                valid users = **<리눅스계정>**
                writable = yes
                create mode = 0777
                directory mode = 0777
    sudo service smbd restart

## 2. 윈도우(Host)에서 접속
    \\**192.168.153.196**\Workspace
