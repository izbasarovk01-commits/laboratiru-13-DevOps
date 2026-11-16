sudo useradd devuser
sudo groupadd devgroup
sudo usermod -aG devgroup devuser
sudo touch /home/dev_data.txt
sudo chown :devgroup /home/dev_data.txt
sudo chmod 640 /home/dev_data.txt
ls -l /home/dev_data.txt

last -n 20
sudo grep "Failed password" /var/log/auth.log
sudo journalctl -u ssh

sudo apt update
sudo apt install fail2ban -y
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
Конфигурация:

bantime = 600
maxretry = 3
sudo systemctl enable --now fail2ban
sudo fail2ban-client status sshd

sudo ufw allow 22
sudo ufw allow 80
sudo ufw enable
sudo ufw status verbose

sudo nano /etc/ssh/sshd_config
Конфигурацияға енгізіледі:

PermitRootLogin no
sudo sshd -t
sudo systemctl restart ssh
