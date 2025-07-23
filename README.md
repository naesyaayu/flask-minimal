# ## cara mer reboot secara manual di EC2 intens
saya menggunakan kode dibawah ini


```ls
cd flask-minimal
sudo nano /etc/systemd/system/flaskapp.service
```
   ```[Unit]
Description=Flask Minimal App
After=network.target

[Service]
User=ubuntu
WorkingDirectory=/home/ubuntu/flask-minimal
ExecStart=/home/ubuntu/flask-minimal/venv/bin/python app.py
Restart=always

[Install]
WantedBy=multi-user.target
   ```
 
   ```sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable flaskapp.service
sudo systemctl start flaskapp.service
   ```

   ```sudo systemctl status flaskapp.service
   ```

## setelah dicek berhasil/tidak,pastikan hasinya harus berhasil 

Cara Reboot EC2 via AWS Console (Web Interface)
Buka halaman AWS EC2 Dashboard

Klik menu Instances (di sidebar kiri)

Pilih instance yang ingin direboot (centang)

Klik tombol "Instance state" di atas

Pilih "Reboot instance"

Klik Yes, Reboot
## cek kembali web nya, jika web nya sudah tidak muncul berarti berhasil 



