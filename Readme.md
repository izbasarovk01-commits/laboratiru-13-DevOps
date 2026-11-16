# ЗЕРТХАНАЛЫҚ ЖҰМЫС №13

## Тақырыбы: Операциялық жүйелердің қауіпсіздігі мен қолжетімділігін қамтамасыз ету

### Жұмыстың мақсаты
- Операциялық жүйе қауіпсіздігін қамтамасыз ету.
- Қолданушы құқықтарын басқару.
- Жүйелік журналдарды талдау.
- Желідегі шабуылдардан қорғау.
- Бұлтты сервер қауіпсіздігін үйрену.

---

## 1-тапсырма. Қолданушы рұқсаттарын басқару

```bash
sudo useradd devuser
sudo groupadd devgroup
sudo usermod -aG devgroup devuser
sudo touch /home/dev_data.txt
sudo chown :devgroup /home/dev_data.txt
sudo chmod 640 /home/dev_data.txt
ls -l /home/dev_data.txt

## 2 - тапсырма
last -n 20
sudo grep "Failed password" /var/log/auth.log
sudo journalctl -u ssh

## 3 - тапсырма
sudo apt update
sudo apt install fail2ban -y
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
sudo systemctl enable --now fail2ban
sudo fail2ban-client status sshd

## 4 - тапсырма
sudo ufw allow 22
sudo ufw allow 80
sudo ufw enable
sudo ufw status verbose

## 5 - тапсырма
sudo nano /etc/ssh/sshd_config
Конфигурацияға енгізіледі:

PermitRootLogin no
sudo sshd -t
sudo systemctl restart ssh
