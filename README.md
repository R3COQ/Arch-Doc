
# Arch Linux Kurulumları ve Sistem Ayarları Dökümantasyonu

## Paket Yöneticisi ile Kurulan Uygulamalar

### Temel Araçlar
- `sudo pacman -S wget` - İnternetten dosya indirme aracı
- `sudo pacman -S net-tools` - Ağ yönetim araçları (ifconfig, netstat gibi)
- `sudo pacman -S bind-tools` - DNS araçları (dig, nslookup gibi)
- `sudo pacman -S mtr` - Ağ diagnostik aracı
- `sudo pacman -S speedtest-cli` - İnternet hız testi aracı
- `sudo pacman -S usbutils` - USB aygıtları görüntüleme (lsusb)
- `sudo pacman -S lm_sensors` - Donanım sensörleri izleme
- `sudo pacman -S openssh` - SSH istemci ve sunucusu
- `sudo pacman -S quota` - Disk kotaları yönetimi
- `sudo pacman -S ntfs-3g exfat-utils dosfstools` - Dosya sistemi desteği

### Docker ve Container Araçları
- `sudo pacman -S docker docker-compose` - Container platformu ve orkestrasyon
- `sudo pacman -S kubectl` - Kubernetes komut satırı aracı
- `sudo pacman -S kubectx` - Kubernetes context değiştirme aracı

### Geliştirme Araçları
- `sudo pacman -S terraform` - Infrastructure as Code aracı
- `sudo pacman -S ansible` - Konfigürasyon yönetim aracı
- `sudo pacman -S pass gnupg` - Şifre yönetimi ve şifreleme

### Multimedya
- `sudo pacman -S vlc` - Video oynatıcı
- `sudo pacman -S elisa` - Müzik oynatıcı
- `sudo pacman -S obs-studio` - Ekran kayıt ve yayın yazılımı
- `sudo pacman -S cheese kamoso` - Webcam uygulamaları
- `sudo pacman -S ktorrent` - Torrent istemcisi
- `sudo pacman -S kdenlive` - Video düzenleme yazılımı
- `sudo pacman -S krita` - Dijital resim yazılımı
- `sudo pacman -S gimp` - Görsel düzenleme yazılımı

### Ofis ve Üretkenlik
- `sudo pacman -S libreoffice` - Ofis paketi
- `sudo pacman -S kcalc` - Hesap makinesi
- `sudo pacman -S okular` - PDF görüntüleyici
- `sudo pacman -S kate` - Gelişmiş metin editörü
- `sudo pacman -S digikam` - Fotoğraf yönetimi
- `sudo pacman -S kmail` - E-posta istemcisi
- `sudo pacman -S filelight` - Disk kullanım görselleştirme

### Sistem Araçları
- `sudo pacman -S timeshift` - Sistem yedekleme aracı
- `sudo pacman -S neofetch` - Sistem bilgisi gösterimi
- `sudo pacman -S partitionmanager` - Disk bölümleme aracı
- `sudo pacman -S ksystemlog` - Sistem log görüntüleyici
- `sudo pacman -S kompare` - Dosya karşılaştırma aracı
- `sudo pacman -S kgpg` - GPG arayüzü
- `sudo pacman -S isoimagewriter` - ISO yazma aracı
- `sudo pacman -S kget` - İndirme yöneticisi

### KDE Özel Araçlar
- `sudo pacman -S yakuake` - Açılır terminal
- `sudo pacman -S kdeconnect` - Telefon-PC entegrasyonu
- `sudo pacman -S kwallet kwalletmanager` - Şifre yönetimi
- `sudo pacman -S plasma-firewall` - Güvenlik duvarı arayüzü
- `sudo pacman -S power-profiles-daemon` - Güç yönetimi
- `sudo pacman -S krunner` - Uygulama başlatıcı
- `sudo pacman -S gwenview` - Resim görüntüleyici
- `sudo pacman -S kleopatra` - Sertifika yönetimi

### AUR (yay) ile Kurulan Uygulamalar
- `yay -S google-chrome opera spotify` - Web tarayıcıları ve müzik servisi
- `yay -S slack-desktop` - Mesajlaşma uygulaması
- `yay -S teams-for-linux-bin` - Video konferans
- `yay -S visual-studio-code-bin` - Kod editörü
- `yay -S postman` - API geliştirme aracı
- `yay -S docker-desktop` - Docker GUI arayüzü
- `yay -S zapzap` - WhatsApp istemcisi
- `yay -S octopi` - Grafik paket yöneticisi

## Sistem Ayarları

### Docker Konfigürasyonu
```bash
sudo systemctl enable --now docker.service
sudo usermod -aG docker $USER
newgrp docker
```

### Güç Yönetimi
```bash
sudo systemctl enable --now power-profiles-daemon
```

### Bluetooth
```bash
sudo systemctl enable bluetooth --now
```

### Ses Sistemi
```bash
sudo pacman -S pipewire pipewire-alsa pipewire-pulse wireplumber
sudo pacman -S bluez bluez-utils
```

### Güvenlik Duvarı
```bash
sudo systemctl enable --now firewalld
```

### SSH Agent
```bash
sudo systemctl enable ssh-agent
```

### GPG Konfigürasyonu
```bash
gpg --full-generate-key
pass init [GPG_KEY_ID]
```

### Zsh Eklentileri
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
git clone https://github.com/Aloxaf/fzf-tab ~/.oh-my-zsh/custom/plugins/fzf-tab
git clone https://github.com/zsh-users/zsh-completions ~/.oh-my-zsh/custom/plugins/zsh-completions
git clone https://github.com/zdharma-continuum/fast-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/fast-syntax-highlighting
git clone https://github.com/zsh-users/zsh-history-substring-search ~/.oh-my-zsh/custom/plugins/zsh-history-substring-search
autoload -U compinit && compinit
```

### Sistem Temizliği
```bash
sudo pacman -Rns $(pacman -Qdtq)
sudo pacman -Scc
sudo paccache -r
```

---

Bu dökümantasyon, sistemde yapılan kurulum ve konfigürasyon işlemlerinin tam listesini içermektedir. Her bir paket ve ayar, sistemin işlevselliğini artırmak ve kullanıcı deneyimini geliştirmek için eklenmiştir.
