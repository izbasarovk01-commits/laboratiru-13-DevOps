Зертханалық жұмыс №13
Тақырыбы: Операциялық жүйелердің қауіпсіздігі мен қолжетімділігін қамтамасыз ету
Жұмыстың мақсаты
Операциялық жүйе қауіпсіздігін қамтамасыз ету.
Қолданушы құқықтарын басқару.
Жүйелік журналдарды талдау.
Желілік шабуылдардан қорғау.
Бұлтты сервер қауіпсіздігін үйрену.
1-тапсырма. Қолданушы рұқсаттарын басқару
sudo useradd devuser
sudo groupadd devgroup
sudo usermod -aG devgroup devuser
sudo touch /home/dev_data.txt
sudo chown :devgroup /home/dev_data.txt
sudo chmod 640 /home/dev_data.txt
ls -l /home/dev_data.txt
Нәтиже: Қолданушы және топ құрылды. Файлға рұқсаттар берілді.

2-тапсырма. Жүйелік журналдарды талдау
last -n 20
sudo grep "Failed password" /var/log/auth.log
sudo journalctl -u ssh
Нәтиже: Жүйеге кіру әрекеттері мен қателер журналдары тексерілді.

3-тапсырма. Fail2Ban орнату
sudo apt update
sudo apt install fail2ban -y
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
Конфигурация:

bantime = 600
maxretry = 3
sudo systemctl enable --now fail2ban
sudo fail2ban-client status sshd
Нәтиже: Fail2Ban орнатылып, SSH қауіпсіздігі бапталды.

4-тапсырма. UFW Firewall
sudo ufw allow 22
sudo ufw allow 80
sudo ufw enable
sudo ufw status verbose
Нәтиже: 22 және 80 порттарына рұқсат берілді.

5-тапсырма. SSH қауіпсіздігі
sudo nano /etc/ssh/sshd_config
Конфигурацияға енгізіледі:

PermitRootLogin no
sudo sshd -t
sudo systemctl restart ssh
Нәтиже: Root арқылы SSH-ке кіруге тыйым салынды.

Қорытынды
Зертханалық жұмыс барысында Linux операциялық жүйесінің қауіпсіздігін қамтамасыз ету, қолданушыларды басқару, журналдарды талдау, Fail2Ban және UFW құралдарын пайдалану үйренілді.


Акбала Джумадилова <dzumadilovaakbala@gmail.com>
08:28 (1 час назад)
кому: izbasarovk01


ЗЕРТХАНАЛЫҚ ЖҰМЫС №13
Тақырыбы: Операциялық жүйелердің қауіпсіздігі мен қолжетімділігін қамтамасыз ету.

Мақсаты: Linux операциялық жүйесінде қауіпсіздікті қамтамасыз ету және қолданушы құқықтарын басқару.

1-тапсырма. Қолданушы рұқсаттарын басқару
Орындалатын командалар:

sudo useradd devuser
sudo groupadd devgroup
sudo usermod -aG devgroup devuser
sudo touch /home/dev_data.txt
sudo chown :devgroup /home/dev_data.txt
sudo chmod 640 /home/dev_data.txt
Нәтиже: Қолданушы мен топ құрылды.

2-тапсырма. Жүйелік журналдарды талдау
last -n 20
sudo grep "Failed password" /var/log/auth.log
sudo journalctl -u ssh
Нәтиже: Жүйелік журналдар тексерілді.

3-тапсырма. Fail2Ban орнату
sudo apt install fail2ban -y
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
sudo systemctl enable --now fail2ban
sudo fail2ban-client status sshd
Конфигурация: bantime = 600, maxretry = 3.

Нәтиже: Fail2Ban конфигурациясы дайындалды.

4-тапсырма. UFW Firewall
sudo ufw allow 22
sudo ufw allow 80
sudo ufw enable
sudo ufw status verbose
Нәтиже: Қажетті порттарға рұқсат берілді.

5-тапсырма. SSH қауіпсіздігі
SSH конфигурациясында PermitRootLogin no параметрі орнатылады.

sudo sshd -t
sudo systemctl restart ssh
Нәтиже: Root арқылы SSH-ке кіру шектеледі.
