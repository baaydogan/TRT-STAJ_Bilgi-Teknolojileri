# TRT STAJI: Bilgi Teknolojileri
Bu repository içerisinde TRT Genel Müdürlüğü Bilgi Teknolojilerinde yapılan staj günlerinin günlük açıklamaları bulunmaktadır. Umarım faydalı olur.

| # Günler | Başlıklar |
| :---: |     :---:      |
| 1   | Ubuntu ve Docker Kurulumu| 
| 2     | 2. GÜN| 

# 1.GÜN
## UBUNTU
## Ubuntu nedir?
Ubuntu, Debian tabanlı bir Linux dağıtımıdır. Hem masaüstü hem de sunucu ortamlarında kullanılabilir. Açık kaynak kodlu olması, geniş bir kullanıcı ve geliştirici topluluğuna sahip olması, güvenlik ve güncelleme desteği sağlaması Ubuntu'yu popüler kılar.

## Neden Sunucu Olarak Tercih Edilir?
Ubuntu, sunucu ortamlarında yaygın olarak tercih edilir çünkü:
- Stabilite ve Güvenilirlik: Ubuntu Server, kararlı ve güvenilir bir performans sunar.
- Geniş Yazılım Desteği: Çeşitli yazılım ve hizmetlerin Ubuntu üzerinde kolayca çalıştırılabilir olması.
- Güvenlik: Düzenli güvenlik güncellemeleri ve açık kaynak kodlu olması nedeniyle güvenlik açısından avantajlıdır.
- Topluluk Desteği: Ubuntu'nun geniş bir topluluğu ve kapsamlı dökümantasyonu vardır, bu da sorun çözmeyi kolaylaştırır.

---
---

## ORTAM KURULUMU
### VirtualBox Kurulumu
Ubuntu Server'ı kuracağımız Sanal Sunucu ortamı olarak VirtualBox kurulumu gerçekleştirmemiz gerekmektedir.
[Kurulum Linki](https://www.virtualbox.org/wiki/Downloads)

![image](https://github.com/user-attachments/assets/c8ab1486-4ed9-437c-a6b9-40710646a265)

### Ubuntu Server Yüklemesi
Staj süreci boyunca stabillik ve ihtiyaç fazlası eklentilerle uğraşmamak amacıyla 22.04.04 sürümü kullanılmıştır.

Ubuntu Server kurulum ISO dosyasını [Ubuntu 22.04.04](https://releases.ubuntu.com/jammy/) adresi üzerinden indirebilirsiniz. İndirmeniz gereken dosya adı ***"ubuntu-22.04.4-live-server-amd64.iso"***

![image](https://github.com/user-attachments/assets/4db03415-70c3-493c-8b2d-133a7ee4d162)

İndirmiş olduğumuz ISO dosyasının kurulumu için VirtualBox uygulmasını açıp `Yeni` yazan butona tıklıyoruz.

![Ekran görüntüsü 2024-08-06 110652](https://github.com/user-attachments/assets/6ddb082a-940c-4ff6-8690-7c59fb07a96d)

Sunucumuza bir **AD** girip `ISO Kalıbı` adlı yere indirdiğimiz ISO dosyasını ekliyoruz. Ardından ileri diyerek devam ediyoruz.

![image](https://github.com/user-attachments/assets/040fa7ed-ab40-4dee-880c-86a5875f93fc)

`Kullanıcı adı` ve `parola` bilgilerini giriyoruz. Ardından ileri diyerek devam ediyoruz.

![image](https://github.com/user-attachments/assets/972b50e8-aea2-467f-9f4a-f9d0e38f7a03)

Cihazınızın mevcut **Ram** ve **İşlemci** özelliklerine göre dilediğiniz özelliklendirmeyi sanal makineniz için yapabilirsiniz. 
Kurulumda kullanılan cihazın Teknik özellikleri:
- 16GB Ram
- i7 11800H

Sanal makinemiz için bu teknik özelliklere sahip bilgisayarda `4096MB` Ana bellek ve `2` Çekirdek fazlasıyla yeterli olacaktır.

![image](https://github.com/user-attachments/assets/d2e3d7c2-33a4-4d4b-987b-bddfc65784a6)

Depolama olarak da mevcut sistemde 25GB alan yeterli olacaktır.

![image](https://github.com/user-attachments/assets/ac81ade2-dbaa-4ec6-acfc-3fe106e9b066)

Yapmış olduğunuz yapılandırmaları kontrol ederek **"BİTİR"** demeniz kurulumu başarıyla sonlandıracaktır.

![image](https://github.com/user-attachments/assets/892494a4-826d-4a24-b61d-ea812c275685)

Kurmuş olduğunuz Sanal Makinenin ayarlarından `AĞ` kısmına giderek sunucumuzun bağlantısını `"Yalnızca-Anamakine Bağdaştırıcısı"` olarak ayarlayın.

![image](https://github.com/user-attachments/assets/53120797-9d6d-460d-a5f2-4eac5184ba6f)

---
Arık Ubuntu Serverimizi açabiliriz. Bizi karşılayacak ilk ekran Serverimizin dilini belirleyeceği ekrandır. Burada yapmamız gereken `ENGLISH` seçeneğini seçmek ve `Enter`a basmaktır.

![image](https://github.com/user-attachments/assets/a81e4001-ea75-4998-b1d5-c77bfab7f4a9)

Gelen ekranda klavyemizin dilini seçmemiz gerekmektedir. Burada `Layout` yazan yerin üstüne gelip `Enter` tuşuna basıyoruz.
![image](https://github.com/user-attachments/assets/50b77bdb-95ad-40c6-b928-bae9f249fcae)
![image](https://github.com/user-attachments/assets/8114e69b-37f4-4f99-803b-fa2b91fd0fac)

Şimdi karşımıza Network ayarlarını yapılandıracağımız bölüm geldi. Ethernet kartımızı görüyoruz, ağ ayarlarını otomatik ve ya statik olarak yapılandırmamızı istiyor. Bu kısımda `Done` diyerek otomatik yapılandırma yapmasınına izin veriyoruz.
![image](https://github.com/user-attachments/assets/3e80ec7c-e09f-4909-8ac1-37bbac483517)

Ubuntu güncellemelerini çekeceği Mirror adresini buradan ayarlayabilirsiniz. Olduğu gibi bırakarak ilerliyoruz.
![image](https://github.com/user-attachments/assets/0d6cf401-370f-45ef-8ec5-f7245a2746cf)

Sunucumuz için ayarladığımız 25 GB disk bölümünü gördü. Farklı bir disk ayarladıysanız seçebilirsiniz. Varsayılan olarak bırakıp `Done` ile devam ediyoruz.

![image](https://github.com/user-attachments/assets/1eb3aacf-9a10-45a7-a9d3-c07673d0c5a7)

Otomatik olarak yapılandırılan dosya sistemimizi Done ile kabul ediyoruz.

![image](https://github.com/user-attachments/assets/a11cab44-4e39-4b0f-9209-483f23dd4c50)

Gelen ekranda disk üzerindeki her şeyin silineceğini söyleyen uyarı ekranı geliyor. Continue ile devam ediyoruz.

![image](https://github.com/user-attachments/assets/12728055-0982-4a15-8e8f-e235bcb3bcb0)

Kullanıcı ekleme bölümü karşımıza gelecektir. Bu bölümde gerekli alanları doldurarak Ubuntu’da kurulum sonrası login olacağımız bir hesap oluşturuyoruz.

![image](https://github.com/user-attachments/assets/b8f89a15-fb01-4900-98f5-27e0a4d3831c)

Windows Powershell veya Putty vb. araçlar ile uzaktan oturum açmak için `Install OpenSSH server` işaretleyip `Done` ile devam ediyoruz. SSH yüklemek istemiyorsak seçmeden devam edebiliriz ve sonrasında da SSH yükleyebiliriz.

![image](https://github.com/user-attachments/assets/3dd19389-29e6-40db-9428-8acafde1b2d4)

Kurmak istediğimiz servislerin listesinin olduğu bir ekran karşımıza gelecektir. Bu bölümden kurmak istediğimiz servisleri seçip devam edebiliriz. Bu servisleri istediğimiz zaman da kurabiliriz. Burada `Docker` ve `Powershell` servislerini seçerek `Done` diyerek devam ediyoruz. 

![image](https://github.com/user-attachments/assets/46363b11-f8b9-4c95-b5ce-9630eea45b55)

Ubuntu Server ve gerekli servislerin kurulumları başlayacaktır. Bütün kurulumlar bittikten sonra `Reboot Now` aktif olacaktır. Bu bölümün üstüne gelip Enter yaptığımızda sistemimiz yeniden başlayacaktır ve işletim sistemi kurulu olarak karşımıza gelecektir.

![image](https://github.com/user-attachments/assets/80af0ad4-2b0c-4cdf-94f7-976692b8a8f3)

---
---

## UBUNTU SERVER'A GİRİŞ

🎉🎉🎉 Artık nur topu gibi bir sunucumuz oldu! 🎉🎉🎉

Server açıldığında bizi ilk olarak kullanıcı bilgilerini girmemiz istenen ekran karşılıyor. Buraya gerekli bilgileri girdikten sonra bizi asıl çalışmlarımızı yürüteceğimiz terminal ekranı karşılıyor.

> [!TIP]
> Ubuntu Server açıldığında varsayılan olarak Num lock `OFF` modunda ayarlı oluyor.


![image](https://github.com/user-attachments/assets/44d8e457-ea4a-4427-b186-ce99dcfc4713)

![Ekran görüntüsü 2024-08-06 121734](https://github.com/user-attachments/assets/de0f9711-f2aa-4319-a679-127f84c69af7)

---

### Terminal Temel Komutları

Terminal üzerinde çalışırken bize sıkça lazım olacak komutlar aşağıda listeler halinde belirtilmiştir. Bu komutları iyi öğrenmeniz terminalde çalışabilmeniz için oldukça önemli.


#### Dosya ve Dizin İşlemleri

**ls**
   ```sh
   ls       # Dizin içeriğini listelemek için
   ls -la   # Alt dizinlerle birlikte detaylı listeleme için
   ```

**cd**
   ```sh
   cd /path/to/directory   # Dizin değiştirmek
   cd ~                    # Ana dizine dönmek için
   cd ..                   # Bir üst dizine geçmek için 
   ```
   
**pwd**
   ```sh
   pwd    # Bulunduğunuz dizinin yolunu öğrenmek
   ```

**mkdir**
   ```sh
   mkdir yeni_dizin    # Yeni bir dizin oluşturmak
   ```

**rmdir** 
   ```sh
   rmdir boş_dizin   # Boş bir dizini silmek
   ```

**rm**
   ```sh
   rm dosya.txt        # Tek bir dosya silmek için
   rm -r dizin_adi     # Dizin(klasör) ve içeriğini silmek için
   ```

**cp**
   ```sh
   cp kaynak_dosya hedef_dosya        # Tek bir dosya kopyalamak için
   cp -r kaynak_dizin hedef_dizin     # Dizin ve içeriğini kopyalamak için
   ```

**mv**
   ```sh
   mv kaynak hedef              # Dizin/Dosya Taşımak için
   mv eski_isim yeni_isim       # Dizin/Dosya Yeniden adlandırmak için
   ```

---

#### Dosya Görüntüleme ve Düzenleme

**cat**
   ```sh
   cat dosya.txt     # Dosya içeriğini görüntülemek
   ```

**less**
   ```sh
   less dosya.txt    # Dosya içeriğini sayfa sayfa görüntülemek
   ```

**head**
   ```sh
   head dosya.txt     # Dosyanın ilk satırlarını görüntülemek
   ```

**nano** || **vim**
   ```sh
   nano dosya.txt
   ```
   ```sh
   vim dosya.txt
   ```

---

#### Sistem Yönetimi

**sudo**
   ```sh
   sudo komut   # Yönetici (root) yetkisi ile komut çalıştırmak için
   ```

**apt-get** || **apt**
   ```sh
   sudo apt-get update    # Paket listelerini güncellemek için
   ```
   ```sh
   sudo apt-get install paket_adi    # Paket kurmak için 
   ```
   ```sh
   sudo apt-get remove paket_adi     # Paket kaldırmak için
   ```

**ps**
   ```sh
   ps aux    # Çalışan süreçleri görüntülemek için
   ```

**top**
   ```sh
   top    # Canlı süreç izlemek için
   ```

**kill**
   ```sh
   kill PID   # Süreç sonlandırmak için
   ```
   > [!NOTE]
   > PID (Process ID) süreç kimliğidir.

---

#### Ağ Komutları

**ping**
   ```sh
   ping hedef_ip_adresi    # Ağ bağlantısını test etmek için
   ```

**ifconfig**
   ```sh
   ifconfig    # Ağ arayüzlerini ve IP adreslerini görüntülemek için
   ```

**ssh**
   ```sh
   ssh kullanıcı_adi@hedef_ip_adresi    # SSH ile uzak sunucuya bağlanmak için
   ```

---

#### Yardım ve Bilgi

**man**
   ```sh
   man komut_adi    # Komutların kullanım kılavuzunu görüntülemek için
   ```

**--help**
   ```sh
   komut_adi --help   # Komut hakkında yardım almak için
   ```

Terminal komutlarını da öğrendiğimize göre artık SSH bağlantısı yapabilmeyi ve detaylarını öğrenebiliriz.

---
---

## SSH BAĞLANTISI

### SSH Nedir?
SSH (Secure Shell), ağ üzerinden güvenli bir şekilde veri iletimi ve uzaktan yönetim sağlamak için kullanılan bir protokoldür. SSH, kullanıcıların başka bir bilgisayarda komutları çalıştırmasına, dosya transferi yapmasına ve ağ servislerini güvenli bir şekilde kullanmasına olanak tanır. SSH, özellikle güvenlik gerektiren işlemler için tercih edilir.

### SSH Neden Kullanılır?

1. **Güvenlik:**
   - SSH, veri iletimi sırasında tüm trafiği şifreler. Bu, ağ üzerindeki potansiyel saldırganların veri paketlerini okuyamamasını sağlar.
   - Kimlik doğrulama mekanizmaları, kullanıcıların kimliklerini doğrulamak için güvenli yöntemler sunar.

2. **Uzak Yönetim:**
   - SSH, uzaktaki bir bilgisayara erişip komut çalıştırma imkanı verir. Bu, sistem yöneticileri ve geliştiriciler için vazgeçilmez bir araçtır.
   - Uzak sunucuların bakımını ve yönetimini kolaylaştırır.

3. **Dosya Transferi:**
   - SSH, SCP (Secure Copy) ve SFTP (SSH File Transfer Protocol) gibi protokoller aracılığıyla güvenli dosya transferi yapmayı sağlar.
   - Büyük dosyaların veya hassas verilerin güvenli bir şekilde taşınmasını sağlar.

4. **Tünelleme ve Port Yönlendirme:**
   - SSH tünelleme, güvenli bir bağlantı üzerinden başka bir ağ servisine erişim sağlar. Örneğin, uzaktaki bir veritabanına güvenli bir şekilde bağlanmak için kullanılabilir.
   - Port yönlendirme, belirli portların güvenli bir şekilde yeniden yönlendirilmesini sağlar.

5. **Çapraz Platform Desteği:**
   - SSH, Linux, macOS ve Windows dahil olmak üzere çeşitli işletim sistemlerinde kullanılabilir.
   - Bu, farklı platformlar arasında uyumluluk ve esneklik sağlar.

### Bağlantı Kurma

SSH bağlantısı kurmak için, SSH istemcisi olan bir bilgisayardan SSH sunucusu çalıştıran bir bilgisayara bağlanılır. Aşağıdaki komut, bir SSH bağlantısı kurmak için kullanılır:

```sh
ssh kullanıcı_adi@hedef_ip_adresi
```

Bağlantı kurulduğunda, uzaktaki bilgisayarın terminaline erişim sağlanır ve komutlar sanki yerel bir terminalde çalışıyormuş gibi çalıştırılabilir.

> [!IMPORTANT]
> Eğer uzak cihazınızdan SSH bağlantısı yapamıyor iseniz, PowerShell kullanarak OpenSSH servisini yükleleyelim.
> Öncelikle PowerShell'i `YÖNETİCİ olarak çalıştırın`. ardından OpenSSH servisinin sizde yüklü olmadığına emin olmak için aşağıda belirtilen kodu yazarak kontrol yapın.
> ```sh
>Get-WindowsCapability -Online | Where-Object Name -like 'OpenSSH*'
> ```
> eğer size aşağıdaki gibi bir geri dönüş geliyorsa OpenSSH sizde yüklü demektir.
> ```sh
>Name  : OpenSSH.Client~~~~0.0.1.0
>State : NotPresent
>
>Name  : OpenSSH.Server~~~~0.0.1.0
>State : NotPresent
> ```
> Eğer ki gelmiyorsa şimdi OpenSSH servisini yüklemeye geçebiliriz. Yüklemek için aşağıdaki kodu yazalım.
>  ```sh
>Add-WindowsCapability -Online -Name OpenSSH.Client~~~~0.0.1.0
>Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
> ```
> Her iki komut da aşağıdaki çıktıyı döndürmelidir:
>```sh
>Path          :
>Online        : True
>RestartNeeded : False
>```
>OpenSSH Sunucusunu ilk kullanım için başlatmak ve yapılandırmak için PowerShell'i yönetici olarak çalıştırın. Ardından sshd hizmetini başlatmak için aşağıdaki komutları çalıştırın:
> ```sh
># SSHD servisini başlat
>Start-Service sshd
>
># İsteğe bağlı ancak yapmanız tavsiye edilir.
>Set-Service -Name sshd -StartupType 'Automatic'
>
># Güvenlik Duvarı kuralının yapılandırıldığını onaylayın. Kurulum tarafından otomatik olarak oluşturulması gerekir. Doğrulamak için aşağıdakileri yapın.
>if (!(Get-NetFirewallRule -Name "OpenSSH-Server-In-TCP" -ErrorAction SilentlyContinue | Select-Object Name, Enabled)) {
>    Write-Output "Firewall Rule 'OpenSSH-Server-In-TCP' does not exist, creating it..."
>    New-NetFirewallRule -Name 'OpenSSH-Server-In-TCP' -DisplayName 'OpenSSH Server (sshd)' -Enabled True -Direction Inbound -Protocol TCP -Action Allow -LocalPort 22
>} else {
>    Write-Output "Firewall rule 'OpenSSH-Server-In-TCP' has been created and exists."
>}
> ```
> Artık rahatlıkla SSH bağlantısı yapmaya başlayabilirsin!

Powershell üzerinden `OpenSSH` servisini kullanarak `Ubuntu Serverimize` bağlanmaya kaldığımız yerden devam edebiliriz. Bağlantı yapabilmek için öncelikle Sanal Makinemizin IP Adresine ihtiyacımız var. Bunu öğrenebilmek için sanal makinemizin terminaline aşağıdaki komutu girelim:
```sh
ip addr
```

ardından bizi karşılayan ekranda `enp0s3` ip adresini kopyalayım. Çünkü artık bu bizim SSH bağlantısı yapacağımız ip adresimiz olacak.

![Ekran görüntüsü 2024-08-06 160804](https://github.com/user-attachments/assets/645ada94-ebd1-4e1b-aa12-d6733eb979c8)

İp adresimizi de öğrendiğimize göre artık SSH bağlantısını yapabiliriz. SSH bağlantısını yapabilmek için aşağıdaki kodu PowerShell içierisine yazalım.

```sh
ssh kullanıcı_adi@hedef_ip_adresi
```

gerekli komutu çalıştırdıktan sonra bizden parola isteyecek. Bu parolaya, Serverimizi kurarken belirlediğimiz şifreyi yazmak yeterli olacaktır.

![Ekran görüntüsü 2024-08-06 161851](https://github.com/user-attachments/assets/24f10320-5f43-4745-8e4c-c97dafaaf659)

TEBRİKLER 🎉🎉
Artık SSH bağlantımızı başarılı şekilde yapabiliyoruz.

> [!NOTE]
> Görselde SSH bağlantısını yaparken hem `ip adresi` kullanmadık hem de `parola` girmeden giriş yapabildik. Şimdi sıra bunun nasıl yapıldığına geldi!

---

### SSH-Keygen

`SSH-Keygen`; farklı şifreler girmek ve bu farklı şifreleri hatırlamak zorunda kalmamak için oluşturulan bir anahtarlama sistemidir. Kısaca kullanıcılara ait parmak izi niteliğindedir.

SSH bağlantımızı şifre kullanmadan yapabilmek için en güvenli işlem `SSH Public key` kullanmak olacaktır. SSH Public key kullanımı sayesinde özellikle ağ yöneticileri, birbirinden farklı uzak bilgisayar erişimlerini tek bir şifre ile gerçekleştirebilmektedir.



#### Public Key ve Private Key oluşturma

> [!NOTE]
> SSH Public Key (Açık Anahtar) erişim sağlayacağınız sunucuya,
> SSH Private Key (Gizli Anahtar) ise kendi bilgisayarınıza tanımlamanız yeterli olacaktır.
>
> `id_rsa` : Private Key
> `id_rsa.pub` : Public Key

Anahtarları oluşturmak için öncelikle aşağıdaki komutu kullanmamız gerekmektedir. 
```sh
ssh-keygen
```

Bizden key dosyalarını oluşturacak dizin isteniyor, boş bırakarak Enter tuşuna basmanız yeterli olacaktır.
![image](https://github.com/user-attachments/assets/ede627d2-5ee9-4c45-ae2f-21a31f48cce5)

Eğer daha önce bir key oluşturduysanız, sizden yeni keyi mevcut dosyanın üzerine yazmak için izin isteyecektir. Ona 'Y' diyip Enter demeniz yeterli olacaktır.

Sonrasında sizden şifre girmeniz istenecek. Biz her seferinde şifre girmek istemediğimiz için şifre yerini boş bırakıp enter dememiz yeterli olur.

Bütün işlemleri tamamladıktan sonra karşımıza aşağıdaki gibi bir ekran çıkacak.

![image](https://github.com/user-attachments/assets/00bb5193-c556-4808-8b4b-f0d33b8551e6)


> [!IMPORTANT]
> `ssh-keygen` komutunu hem Windows terminalinde hem de Ubuntu serverinin terminalinde yazalım.
> Bizim kopyalama işlemini yapacağımız Anahtar Windows içerisinde oluşturduğumuz `id_rsa.pub` dosyası olacaktır.
> Windows `~/.ssh` dizininde bulunan `id_rsa.pub` dosyasının içerisindeki anahtarı, Ubuntu sunucusunun `/root/.ssh` dizinindeki `authorized_keys` dosyası içerisine yapıştırmamız gerekmektedir.

> [!IMPORTANT]
> Bütün işlemleri yaptıktan sonra Ubuntu Serverini `Reboot` etmeyi unutmayın!

Artık şifre kullanmadan SSH bağlantımızı gerçekleştirebiliriz.

---

### SSH Config







