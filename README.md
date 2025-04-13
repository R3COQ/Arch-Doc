# Arch Linux Sistem Kurulum ve Yapılandırma Dökümanı

Bu döküman, bir Arch Linux sisteminde gerçekleştirilen çeşitli kurulum ve yapılandırma işlemlerini detaylandırmaktadır. İşlemler, Zsh kabuk yapılandırması, temel sistem araçlarının kurulumu, masaüstü uygulamalarının kurulumu, geliştirme araçlarının kurulumu ve diğer sistem ayarlarını kapsamaktadır.

## 1. Zsh Kabuk Yapılandırması ve Eklentileri

Zsh kabuğunu özelleştirmek ve kullanımını kolaylaştırmak için çeşitli eklentiler kurulmuş ve yapılandırılmıştır.

* **Otomatik Öneri Eklentisi:**
    ```bash
    git clone [https://github.com/zsh-users/zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions) ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
    ```
    Bu komut, Zsh için otomatik komut önerileri sunan `zsh-autosuggestions` eklentisini Oh My Zsh özel eklentiler dizinine klonlar.

* **Sözdizimi Vurgulama Eklentisi:**
    ```bash
    git clone [https://github.com/zsh-users/zsh-syntax-highlighting.git](https://github.com/zsh-users/zsh-syntax-highlighting.git) ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
    ```
    Bu komut, Zsh komut satırında sözdizimi vurgulaması sağlayan `zsh-syntax-highlighting` eklentisini klonlar.

* **`.zshrc` Dosyası Düzenleme:**
    ```bash
    nano .zshrc
    ```
    Bu komut, Zsh yapılandırma dosyasını Nano metin düzenleyici ile açar. Bu işlem birden çok kez tekrarlanmıştır, muhtemelen kurulan eklentileri etkinleştirmek ve diğer Zsh ayarlarını yapılandırmak için kullanılmıştır.

* **fzf Tab Tamamlama Eklentisi:**
    ```bash
    git clone [https://github.com/Aloxaf/fzf-tab](https://github.com/Aloxaf/fzf-tab) ~/.oh-my-zsh/custom/plugins/fzf-tab
    ```
    Bu komut, fzf (bulanık bulucu) ile entegre olarak gelişmiş tab tamamlama özellikleri sunan `fzf-tab` eklentisini klonlar.

* **Gelişmiş Tamamlama Eklentileri:**
    ```bash
    git clone [https://github.com/zsh-users/zsh-completions](https://github.com/zsh-users/zsh-completions) ~/.oh-my-zsh/custom/plugins/zsh-completions
    ```
    Bu komut, Zsh için daha kapsamlı ve özelleştirilmiş tamamlama tanımları içeren `zsh-completions` eklentisini klonlar.

* **Tamamlama Sistemini Başlatma:**
    ```bash
    autoload -U compinit && compinit
    ```
    Bu komut, Zsh tamamlama sistemini başlatır.

* **Hızlı Sözdizimi Vurgulama Eklentisi:**
    ```bash
    git clone [https://github.com/zdharma-continuum/fast-syntax-highlighting.git](https://github.com/zdharma-continuum/fast-syntax-highlighting.git) ~/.oh-my-zsh/custom/plugins/fast-syntax-highlighting
    ```
    Bu komut, daha hızlı performans sunan alternatif bir sözdizimi vurgulama eklentisi olan `fast-syntax-highlighting`i klonlar.

* **Geçmişte Alt Dize Arama Eklentisi:**
    ```bash
    git clone [https://github.com/zsh-users/zsh-history-substring-search](https://github.com/zsh-users/zsh-history-substring-search) ~/.oh-my-zsh/custom/plugins/zsh-history-substring-search
    ```
    Bu komut, komut geçmişinde alt dizelere göre arama yapmayı sağlayan `zsh-history-substring-search` eklentisini klonlar.

## 2. Temel Sistem Araçlarının Kurulumu

Sistem yönetimi ve temel işlevler için çeşitli araçlar Pacman paket yöneticisi kullanılarak kurulmuştur.

* **Sistem Geri Yükleme Aracı:**
    ```bash
    sudo pacman -S timeshift
    ```
    Timeshift, sistem anlık görüntüleri alarak geri yükleme noktaları oluşturmayı sağlar.

* **Web Üzerinden Dosya İndirme Aracı:**
    ```bash
    sudo pacman -S wget
    ```
    Wget, komut satırından web üzerinden dosya indirmek için kullanılır.

* **Ağ Bağlantısını Test Etme Aracı:**
    ```bash
    sudo pacman -S ping
    ```
    Ping, ağdaki bir sunucuya ulaşılabilirliği test etmek için kullanılır.

* **Temel Ağ Araçları:**
    ```bash
    sudo pacman -S net-tools
    ```
    `net-tools` paketi, `ifconfig`, `netstat` gibi temel ağ yapılandırma ve izleme araçlarını içerir.

* **Bulanık Arama Aracı:**
    ```bash
    sudo pacman -S fzf
    ```
    fzf, komut satırında dosyaları, geçmişi ve diğer öğeleri bulanık eşleştirme ile hızlı bir şekilde bulmayı sağlar.

## 3. AUR Yardımcısı Yay Kurulumu

Arch User Repository (AUR), topluluk tarafından sağlanan paketleri içerir. Bu paketleri kolayca kurmak için `yay` yardımcı programı kurulmuştur.

* **Yay Kaynak Kodlarını İndirme:**
    ```bash
    cd Workdir
    git clone [https://aur.archlinux.org/yay.git](https://aur.archlinux.org/yay.git)
    ```

* **Yay Paketini Derleme ve Kurma:**
    ```bash
    cd yay
    makepkg -si
    ```
    `makepkg -si` komutu, paketi derler (`-s`) ve bağımlılıklarını kurduktan sonra (`-i`) yükler.

## 4. Uygulama Kurulumları (Yay ve Pacman ile)

Çeşitli masaüstü uygulamaları ve geliştirme araçları hem Pacman (resmi depolar) hem de Yay (AUR) kullanılarak kurulmuştur.

* **Web Tarayıcıları ve Müzik Uygulaması:**
    ```bash
    yay -S google-chrome opera spotify
    ```
    Google Chrome, Opera web tarayıcıları ve Spotify müzik uygulaması AUR üzerinden kurulmuştur.

* **Konteyner Platformu Docker:**
    ```bash
    sudo pacman -S docker
    sudo pacman -S docker-compose
    sudo systemctl enable --now docker.service
    sudo usermod -aG docker $USER
    ```
    Docker ve Docker Compose, konteynerleştirilmiş uygulamaları yönetmek için kurulmuş ve Docker servisi başlatılmıştır. Kullanıcı, Docker komutlarını `sudo` olmadan çalıştırabilmek için `docker` grubuna eklenmiştir (genellikle yeniden oturum açmak gerekir).

* **Kubernetes Yönetim Araçları:**
    ```bash
    sudo pacman -S kubectl
    sudo pacman -S kubectx
    ```
    Kubectl, Kubernetes kümelerini yönetmek için kullanılan komut satırı aracıdır. Kubectx ise farklı Kubernetes kümeleri arasında kolayca geçiş yapmayı sağlar.

* **Masaüstü Uygulamaları (Metin Düzenleyici, Belge Görüntüleyici, vb.):**
    ```bash
    sudo pacman -S kate okular kdeconnect power-profiles-daemon pipewire pipewire-alsa pipewire-pulse wireplumber bluez bluez-utils kcalc gwenview vlc neofetch flatpak plasma-firewall firewalld digikam kmail filelight kleopatra gimp krunner libreoffice
    sudo systemctl enable --now power-profiles-daemon
    sudo systemctl enable bluetooth --now
    sudo systemctl enable --now firewalld
    ```
    Bu komutlar, Kate (gelişmiş metin düzenleyici), Okular (belge görüntüleyici), KDE Connect (telefon-bilgisayar entegrasyonu), güç profili yönetimi, ses ve video sunucusu PipeWire, Bluetooth desteği, temel masaüstü uygulamaları, Flatpak paket yöneticisi, güvenlik duvarı araçları, fotoğraf yönetimi, e-posta istemcisi, disk kullanım analiz aracı, sertifika yönetimi, resim düzenleme, uygulama başlatıcı ve ofis paketi gibi çeşitli masaüstü uygulamalarını kurar ve ilgili servisleri başlatır.

* **Diğer Uygulamalar (Slack, Teams, VS Code):**
    ```bash
    yay -S slack-desktop
    yay -S teams-for-linux-bin
    yay -S visual-studio-code-bin
    ```
    Slack, Microsoft Teams ve Visual Studio Code gibi popüler uygulamalar AUR üzerinden kurulmuştur.

* **Paket Kaldırma ve Önbellek Temizleme:**
    ```bash
    sudo pacman -Rns $(pacman -Qdtq)
    sudo pacman -Scc
    sudo paccache -r
    sudo pacman -S paccache
    ```
    Bu komutlar, artık gerekmeyen (orphaned) paketleri kaldırır ve Pacman önbelleğini temizler. `paccache` aracı da kurulmuştur.

* **Diğer Araçlar (Postman, Octopi, Parola Yöneticisi, Ağ Araçları vb.):**
    ```bash
    yay -S postman
    yay -S octopi
    sudo pacman -S pass gnupg mtr quota ntfs-3g exfat-utils dosfstools usbutils partitionmanager lm_sensors network-tools bind-tools speedtest-cli discord kwallet kwalletmanager gnupg pinentry openssh
    ```
    API geliştirme aracı Postman, Pacman için grafiksel arayüz Octopi, parola yöneticisi Pass, şifreleme aracı GnuPG, ağ teşhis araçları, disk kota yönetimi, dosya sistemi destek araçları, USB bilgi aracı, bölümleme yöneticisi, donanım sensör izleme, gelişmiş ağ araçları, DNS sorgulama araçları, internet hız testi, iletişim uygulaması Discord, KDE cüzdan yönetimi ve SSH araçları gibi çeşitli yardımcı programlar kurulmuştur.

* **Grafik ve Multimedya Uygulamaları:**
    ```bash
    sudo pacman -S kolourpaint yakuake ksystemlog kompare kgpg isoimagewriter ktorrent elisa obs-studio cheese kamoso kget krita kdenlive
    sudo pacman -Rns kolourpaint
    ```
    Basit resim düzenleme, açılır terminal, sistem günlük görüntüleyici, dosya karşılaştırma, GPG ön yüzü, ISO yazma aracı, BitTorrent istemcisi, müzik çalar, yayın ve kayıt yazılımı, web kamerası uygulamaları, indirme yöneticisi, dijital boyama ve video düzenleme yazılımları gibi çeşitli grafik ve multimedya uygulamaları kurulmuştur. Kolourpaint daha sonra kaldırılmıştır.

## 5. Docker Yapılandırması

Docker kullanımı için ek yapılandırmalar yapılmıştır.

* **Docker Desktop Kurulumu:**
    ```bash
    yay -S docker-desktop
    ```
    Docker Desktop, Docker'ı grafiksel bir arayüz üzerinden yönetmeyi sağlar.

* **GPG ve Pass ile Docker Kimlik Bilgilerini Yönetme:**
    ```bash
    sudo pacman -S pass gnupg
    gpg --full-generate-key
    nano ~/.docker/config.json
    pass init <GPG_ANAHTAR_ID>
    nano ~/.docker/config.json
    ```
    Bu adımlar, Docker kimlik bilgilerini güvenli bir şekilde saklamak için Pass parola yöneticisinin GPG ile birlikte kullanımını yapılandırmayı amaçlamaktadır. `<GPG_ANAHTAR_ID>` yerine gerçek GPG anahtar kimliği girilmelidir.

## 6. Diğer Sistem Ayarları ve Araçları

Çeşitli diğer sistem ayarları ve yardımcı araçlar da kurulmuştur.

* **Ağ İzleme Aracı:**
    ```bash
    sudo pacman -S mtr
    mtr 213.14.134.174
    ```
    MTR (My Traceroute), ağ yolu üzerindeki yönlendiricileri ve gecikmeleri izlemek için kullanılır.

* **Disk Kotası Yönetimi:**
    ```bash
    sudo pacman -S quota
    ```
    Disk kotalarını yönetmek için gerekli araçlar kurulmuştur.

* **Dosya Sistemi Desteği:**
    ```bash
    sudo pacman -S ntfs-3g exfat-utils dosfstools
    ```
    NTFS, exFAT ve FAT dosya sistemlerine okuma/yazma desteği eklenmiştir.

* **USB Cihazlarını Listeleme:**
    ```bash
    lsusb
    sudo pacman -S usbutils
    lsusb
    ```
    `lsusb` komutu, bağlı USB cihazlarını listeler. `usbutils` paketi bu komutu içerir.

* **Disk Bölümleme Aracı:**
    ```bash
    sudo pacman -S partitionmanager
    ```
    Partition Manager, disk bölümlerini grafiksel olarak yönetmek için kullanılır.

* **Donanım Sensörlerini İzleme:**
    ```bash
    sudo pacman -S lm_sensors
    ```
    `lm_sensors`, sıcaklık, fan hızı gibi donanım sensörlerinden bilgi almayı sağlar.

* **Gelişmiş Ağ Araçları ve DNS Sorgulama:**
    ```bash
    sudo pacman -S network-tools
    sudo pacman -S bind-tools
    ```
    `network-tools` ve `bind-tools` paketleri, gelişmiş ağ yapılandırma ve DNS sorgulama araçlarını içerir.

* **İnternet Hız Testi:**
    ```bash
    sudo pacman -S speedtest-cli
    ```
    `speedtest-cli`, komut satırından internet hızını test etmek için kullanılır.

* **İletişim Uygulaması Discord:**
    ```bash
    sudo pacman -S discord
    ```
    Discord, sesli ve yazılı iletişim için popüler bir uygulamadır.

* **KDE Cüzdan Yönetimi:**
    ```bash
    sudo pacman -S kwallet kwalletmanager
    ```
    KDE Wallet, parolaları ve diğer hassas bilgileri güvenli bir şekilde saklamak için kullanılır.

* **GPG ve PIN Giriş Araçları:**
    ```bash
    sudo pacman -S gnupg pinentry
    ```
    GnuPG ve PIN giriş diyalogları, şifreleme ve kimlik doğrulama işlemleri için gereklidir.

* **SSH (Güvenli Kabuk):**
    ```bash
    sudo pacman -S openssh
    systemctl status ssh-agent.service
    which ssh-agent
    sudo systemctl status ssh-agent
    sudo systemctl enable ssh-agent
    ```
    OpenSSH, güvenli uzaktan erişim için kullanılır. `ssh-agent` servisi de etkinleştirilmiştir.

* **Sistem Güncellemesi:**
    ```bash
    sudo pacman -Syu
    ```
    Bu komut, sistemdeki tüm paketleri ve paket listelerini günceller.

* **Yeniden Başlatma:**
    ```bash
    reboot
    ```
    Sistemdeki değişikliklerin etkinleşmesi için birkaç kez yeniden başlatma işlemi yapılmıştır.

Bu döküman, gerçekleştirilen işlemlerin kapsamlı bir özetini sunmaktadır. Her bir komutun amacı ve sistem üzerindeki etkisi açıklanmıştır. Bu bilgiler, sistemin mevcut durumu ve yapılan yapılandırmalar hakkında genel bir bakış sağlar.
