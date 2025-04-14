
# 📘 Arch Linux Kurulum ve Yapılandırma Dökümantasyonu

## 🐚 Zsh Yapılandırması

### Oh-My-Zsh ve Eklenti Kurulumu

```bash
nano .zshrc
```

#### Eklentiler

1. **Autosuggestions**
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

2. **Syntax Highlighting**
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

3. **History Substring Search**
```bash
git clone https://github.com/zsh-users/zsh-history-substring-search ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-history-substring-search
```

4. **fzf-tab**
```bash
sudo pacman -S fzf
git clone https://github.com/Aloxaf/fzf-tab ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/fzf-tab
```

#### Zsh Konfigürasyonunun Yüklenmesi
```bash
source ~/.zshrc
```

---

## 🧰 Genel Uygulama Kurulumları

```bash
sudo pacman -S kdeconnect 
sudo pacman -S power-profiles-daemon
sudo systemctl enable --now power-profiles-daemon
```

```bash
sudo pacman -S bluez bluez-utils
sudo systemctl enable bluetooth --now
```

```bash
sudo pacman -S kcalc 
sudo pacman -S gwenview
sudo pacman -S vlc
sudo pacman -S neofetch
sudo pacman -S digikam
sudo pacman -S kmail 
sudo pacman -S filelight 
sudo pacman -S krunner 
sudo pacman -S libreoffice 
sudo pacman -S kleopatra 
sudo pacman -S timeshift
sudo pacman -S gimp
```

---

## 🧑‍💻 Geliştirici Araçları

### Visual Studio Code
```bash
yay -S visual-studio-code-bin
```

### Docker
```bash
sudo pacman -S docker
sudo systemctl enable --now docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world
```

### Docker Desktop (İsteğe bağlı)
```bash
yay -S docker-desktop
systemctl --user enable --now docker-desktop
```

### Kubernetes
```bash
sudo pacman -S kubectl kubectx
```

### Lens
```bash
yay -S lens
```

---

## 🔒 Güvenlik

### UFW (Firewall)
```bash
sudo pacman -S ufw
sudo systemctl enable --now ufw
```

### GPG ve Pass (şifre yönetimi)
```bash
sudo pacman -S pass gnupg
gpg --full-generate-key
gpg --list-keys
pass init YOUR_GPG_KEY_ID
```

---

## 🌐 Uygulamalar (AUR Üzerinden)

```bash
mkdir Workdir && cd Workdir
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

### AUR'dan uygulama kurulumları:
```bash
yay -S google-chrome opera spotify slack-desktop zapzap teams-for-linux postman octopi
```

---

## 🐳 Docker Compose Projesi Örneği

```bash
cd ~/Workdir
git clone https://github.com/bariiss/SpoofDPI.git
cd SpoofDPI
docker compose up -d
```

---

## 📊 Sistem Araçları ve Bilgileri

```bash
sudo pacman -S mtr quota quota-tools ntfs-3g exfat-utils dosfstools usbutils lm_sensors partitionmanager
mtr <ip_adresi>
lsblk
lsusb
htop
```

---

## 🛡️ VPN

```bash
globalprotect connect -p remote.mokaunited.com -u <kullanıcı_adı>
```
