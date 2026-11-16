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
