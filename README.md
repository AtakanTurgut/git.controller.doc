## Git & GitHub : Versiyon Kontrolü
- Git : Versiyon Kontrol Sistemidir.

### Windows Git Kurulum
Windows'a Git'i kurmak için [[kaynak]](https://git-scm.com/download/win).       <br/>
Hazır ayarlar kullanılarak `Next` butonuna tıklayıp geçiyoruz. En son `Install` seçeneğine tıklayarak yüklemeyi başlatıp yüklendikten sonra da `Finish` butonuna tıklayarak kapatıyoruz.
```bash
        git --version
```
Yükleme işlemi başarıyla sona erdikten sonra yukarıdaki komutu kullanarak Git versiyonunun kontrol edebiliriz.  <br/>
Komutları yükleme sonrası `Git Bash` komut iştemcisine yazıyoruz.
![](pictures/gitIm1.PNG)

### Mac ve Linux Kurulumu
Mac ve Linux sistemlerde hali hazırda Git kurulu olur.  <br/>
Eğer sistemde yüklü değilse ve yüklememiz gerekirse [[kaynak]](https://git-scm.com/download).   <br/>
Binary installer'ı kullanarak Git yüklenebilir.
```bash
        git --version
```

Yukarıdaki komutu kullanarak Git'in çalışıp çalışmadığını görebiliriz.
```bash
        git
```
Git yüklüyse yukarıdaki komutu girerek Git Dokümantasyonuna ulaşabiliriz.

###  Git Bash Terminal Kullanımı 
- İçerisinde bulunduğumuz dizinde diğer klasörleri ve dokümanları gösterir.
```bash
        ls      
```
![](pictures/ls.PNG)

- Klasör içerisindeki gizli dosyaları da görmek istersek:
```bash
        ls -la      
```
![](pictures/ls-la.PNG)

- Üzerinde bulunduğumuz dizini bulmak için:
```bash
        pwd
```
![](pictures/pwd.PNG)

- Dizindeki diğer klasörlere ulaşabilmek için:
```bash
        cd KlasorAdı
```
![](pictures/cd.PNG)

- Bir önceki dizine geri dönebilmek için:
```bash
        cd ..
```
![](pictures/cd...PNG)

- Terminal çıktılarını temizlemek için:
```bash
        clear
```

- Dizin üzerinde klasör oluşturmak için:
```bash
        mkdir KlasorAdı
```
![](pictures/mkdir.PNG)

- Dizinde dosya oluşturmak için:
 ```bash
        touch dosya.uzantısı
 ```
 ![](pictures/touch.PNG)

 - Dizinden dosya kaldırmak için:
```bash
        rm dosya.uzantısı
 ```
 ![](pictures/rm.PNG)

- Dizinden klasör kaldırmak için:
```bash
        rm -rf KlasorAdı
```
 ![](pictures/rm-rf.PNG)

### Kullanıcı Adı ve Email Girmek
- Git sistemine kullanıcı adımızı ve email bilgilerimizi kaydetmek için:
```bash
        git config --global user.name "UserName Surname"

        git config user.name
```
 ![](pictures/configUserName1.PNG)
 ![](pictures/configUserName2.PNG)

- Git sistemine email bilgisini kaydetmek için:
```bash
        git config --global user.email user@email.com

        git config user.email
```
 ![](pictures/configUserEmail.PNG)

### Git Temel Komutları
```cs
        Çalşıma Klasörü      =>      Index - Staging       =>       Local Repository
                          git add                      git commit
```

- Git güncel durumunu göstermek için:
```bash
        git status
```
Herhangi bir yerde `git init` komutunu çalıştırmadan önce git durumunu kontrol etmek her zaman için doğru olacaktır. <br/>
Aksi halde git'i birkaç farklı aktif etme durumu çakışmalara sebep olabilir.
 ![](pictures/gitstatus.PNG)

 - Git'i klasörde aktif etmek için:     master veya main branch olarak çalıştırır.
 ```bash
        git init
```
 ![](pictures/gitinit.PNG)

 - Git'e dosya veya klasör eklemek için:
```bash
        git add dosya.uzantısı
```
 ![](pictures/gitadd.PNG)

- Git'e yapılanların tümünü eklemek için:
```bash
        git add .
```