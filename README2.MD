
# 📘 Arch Linux Kurulum ve Yapılandırma Dökümantasyonu


#🐚 Zsh Yapılandırması

## 1. **Zsh Kurulumu**

Zsh, sisteminizde yüklü değilse, aşağıdaki komutla kurabilirsiniz:

```bash
sudo pacman -S zsh        # Zsh yükleme
```

## 2. Oh-My-Zsh Kurulumu

Oh My Zsh, Zsh için popüler bir yapılandırma yönetim aracıdır. Aşağıdaki komutla kurabilirsiniz:

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"  # Oh-My-Zsh yükleme
```

Kurulumdan sonra, ~/.zshrc dosyasına otomatik olarak Oh-My-Zsh yapılandırması eklenecektir.

### ⚙️ Oh-My-Zsh ve Eklenti Kurulumu

```bash
nano .zshrc
```

### 🔌 Eklentiler

1. **🔄 Autosuggestions**
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
- **Açıklama**: Bu eklenti, komutları yazarken geçmiş komutlardan otomatik öneriler sunar.

2. **🎨 Syntax Highlighting**
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
- **Açıklama**: Komut satırındaki sözdizimi hatalarını renkli olarak vurgular.

3. **🔍 History Substring Search**
```bash
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
```
- **Açıklama**: Geçmişteki komutları, sadece komutun bir kısmıyla aramanıza olanak tanır.

4. **🔲 fzf-tab**
```bash
sudo pacman -S fzf          # fzf komut satırı aracı kurulur
git clone https://github.com/Aloxaf/fzf-tab ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/fzf-tab
```
- **Açıklama**: Bu eklenti, sekme tamamlama için `fzf` arayüzünü entegre eder ve daha hızlı dosya aramaları sağlar.

#### 🔄 Zsh Konfigürasyonunun Yüklenmesi
```bash
source ~/.zshrc
```
- **Açıklama**: Yapılandırma dosyanızı yeniden yükler ve yapılan değişikliklerin aktif olmasını sağlar.


---

# 🛠️ Sistem Sürücü Kurulumları

#### 🔋 Güç Yönetimi
```bash
sudo pacman -S power-profiles-daemon     # Güç yönetimi aracı
sudo systemctl enable --now power-profiles-daemon  # Güç yönetimi servisini etkinleştir ve başlat
```

#### 🔵 Bluetooth Yönetimi
```bash
sudo pacman -S bluez bluez-utils     # Bluetooth desteği sağlayan paketler
sudo systemctl enable bluetooth --now  # Bluetooth servisini etkinleştir ve başlat

```

# 🧰 KDE Applications

#### 📊 Hesaplama ve Ofis Araçları
```bash
sudo pacman -S kcalc            # Hesap makinesi
sudo pacman -S libreoffice      # Ofis paketi
sudo pacman -S okular           # PDF görüntüleyici
sudo pacman -S kate             # Gelişmiş metin editörü
```
#### 🖼️ Resim ve Fotoğraf Yönetimi
```bash
sudo pacman -S gwenview         # Resim görüntüleyici
sudo pacman -S digikam          # Fotoğraf yönetimi
sudo pacman -S krita            # Dijital resim yazılımı
sudo pacman -S gimp             # Görsel düzenleme yazılımı
```

#### 🎥 Video ve Multimedya
```bash
sudo pacman -S vlc              # Video oynatıcı
sudo pacman -S elisa            # Müzik oynatıcı
sudo pacman -S obs-studio       # Ekran kayıt ve yayın yazılımı
sudo pacman -S cheese kamoso    # Webcam uygulamaları
sudo pacman -S ktorrent         # Torrent istemcisi
sudo pacman -S kdenlive         # Video düzenleme yazılımı
```

#### 📧 İletişim ve Şifre Yönetimi
```bash
sudo pacman -S kmail            # E-posta istemcisi
sudo pacman -S kwallet kwalletmanager # Şifre yönetimi
```

#### 🛠️ Sistem Araçları ve Yönetimi
```bash
sudo pacman -S timeshift        # Sistem yedekleme aracı
sudo pacman -S partitionmanager # Disk bölümleme aracı
sudo pacman -S ksystemlog       # Sistem log görüntüleyici
sudo pacman -S kompare          # Dosya karşılaştırma aracı
sudo pacman -S kgpg             # GPG arayüzü
sudo pacman -S isoimagewriter   # ISO yazma aracı
sudo pacman -S kget             # İndirme yöneticisi
sudo pacman -S filelight        # Disk kullanım görselleştirme
```

#### ⚙️ Uygulama Başlatıcı ve Diğer Araçlar
```bash
sudo pacman -S krunner          # Uygulama başlatıcı
sudo pacman -S kdeconnect       # Telefon-PC entegrasyonu
sudo pacman -S plasma-firewall  # Güvenlik duvarı arayüzü
sudo pacman -S power-profiles-daemon # Güç yönetimi
sudo pacman -S kleopatra        # Sertifika yönetimi
sudo pacman -S yakuake          # Açılır terminal
```

# 🧰 Sistem Uygulama Kurulumları

#### 🌐 Ağ Araçları
```bash
sudo pacman -S wget            # İnternetten dosya indirme
sudo pacman -S net-tools       # Ağ araçları (ifconfig, netstat)
sudo pacman -S bind-tools      # DNS sorguları (dig, nslookup)
sudo pacman -S mtr             # Ağ bağlantı testi ve takibi
sudo pacman -S speedtest-cli   # İnternet hız testi
```

#### 🔌 USB ve Donanım Araçları
```bash
sudo pacman -S usbutils        # USB cihazlarını gör (lsusb)
sudo pacman -S lm_sensors      # Donanım sıcaklık sensörleri - Bilgisayarın sıcaklık, voltaj ve fan hızını izlemek için kullanılır.
```

#### 🔐 Güvenlik ve Bağlantı Araçları
```bash
sudo pacman -S quota           # Disk kotası yönetimi
```

#### 🖥️ Dosya Sistemi ve Depolama Araçları
```bash
sudo pacman -S ntfs-3g exfat-utils dosfstools # Dosya sistemi desteği (NTFS, exFAT, FAT32)
```

#### 📊 Sistem Bilgisi ve İzleme Araçları
```bash
sudo pacman -S neofetch        # Sistem bilgisi gösterimi
sudo pacman -S htop            # Sistem kaynakları izleme
sudo pacman -S btop            # Sistem kaynakları izleme
```

# 🧑‍💻 Geliştirici Araçları

#### 🐳 Kubernetes Eklentileri Kurulumu
```bash
sudo pacman -S kubectl kubectx
```

#### 🌐 Terraform & Ansible Kurulumu
```bash
sudo pacman -S terraform    # Infrastructure as Code
sudo pacman -S ansible      # Otomasyon ve konfigürasyon yönetimi
```

#### 🐳 Docker Kurulumu
```bash
sudo pacman -S docker docker-compose
sudo systemctl enable --now docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world
```

#### 🐳 Docker Desktop (İsteğe bağlı)
```bash
yay -S docker-desktop
systemctl --user enable --now docker-desktop
```

# 🌐 Uygulamalar (AUR Üzerinden)

#### 🌐 Arch Yay(AUR) Kurulumu
```bash
mkdir Workdir && cd Workdir
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

#### 🌐 AUR'dan uygulama kurulumları:
```bash
yay -S visual-studio-code-bin
yay -S lens-bin
yay -S docker-desktop
yay -S google-chrome 
yay -S opera
yay -S spotify
yay -S slack-desktop 
yay -S zapzap 
yay -S teams-for-linux-bin 
yay -S postman-bin
yay -S octopi
```

---

# 🔒 Güvenlik

#### 🛡️ UFW (Firewall)
```bash
sudo pacman -S ufw
sudo systemctl enable --now ufw
```

#### 🔑 GPG ve Pass (şifre yönetimi)
```bash
sudo pacman -S pass gnupg
gpg --full-generate-key
gpg --list-keys
pass init YOUR_GPG_KEY_ID
```

---

#### 🐳 Docker Compose Projesi Örneği

```bash
cd ~/Workdir
git clone https://github.com/bariiss/SpoofDPI.git
cd SpoofDPI
docker compose up -d
```

---

# 📊 Sistem Araçları ve Bilgileri

```bash
mtr <ip_adresi>
lsblk
lsusb
htop
```

---

# 🛡️ VPN

#### 🛜 Globalprotect Kurulum
```bash
globalprotect connect -p remote.mokaunited.com -u <kullanıcı_adı>
```
