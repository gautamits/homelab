sudo apt install samba -y
sudo cp /etc/samba/smb.conf /etc/samba/smb.conf
sudo nano /etc/samba/smb.conf
# edit

[Share]
comment = Shared
path = /media/amit/backup/shared
browsable = yes
writable = yes
guest ok = yes
read only = no
force user = amit

sudo adduser --home /home/samba --shell /usr/sbin/nologin samba

sudo smbpasswd -a samba
sudo ufw allow samba
sudo systemctl restart smbd
sudo systemctl enable smbd