## Git & GitHub : Versiyon Kontrolü
Git : Versiyon Kontrol Sistemidir.

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

###  Git Bash - Terminal Kullanımı 
Windows, Mac ve Linux için Git komutları farklılık göstermez, aynıdır.

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
        cd KlasorAdi
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
        mkdir KlasorAdi
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
        rm -rf KlasorAdi
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
 ![](pictures/gitadd..PNG)

- Git'e eklenenlerin işlenebilmesi için:
```bash
        git commit -m "commit message"
```
- İşleme alma mesajı yapılanları açıklayıcı olmalıdır.
 ![](pictures/gitcommit.PNG)

 - İşlemleri görebilmek için:
 ```bash
        git log
```
Her commit'in kendine ait bir işlem numarası olur. <br/>
İşlem numarasına dönmek istersek o amaçla kullanılır.

        HEAD -> master

Üzerinde bulunduğumun branch'ı gösterir
![](pictures/gitlog.PNG)

- Yapılan değişiklikleri tekrardan Git'e eklemek ve kontrolleri tekrardan sağlamak için kısaca:
```bash
        git add .
        git commit -m "commit message"
        git status
        git log
```
![](pictures/gitbref.PNG)

Gizli kalmasını istediğimiz dosyaları `Local Repo`'ya kaydetmek istemeyiz.
- `git add` yapılmaması gerekir.
- Öncelikle `.gitignore` isimli bir dosya oluşturmalıyız.
```bash
        touch .gitignore
```
gitignore dosyası içerisine gizli kalmasını istediğimiz dosyayı uzantısıyla birlikte yazmalıyız.
Gizli kalmasını istediğimiz dosya artık Git sorumluluğuna girmez.
```cs
        gitignore  ==>  dosya.uzantısı
```
![](pictures/gitignore2.PNG)
![](pictures/gitignore1.PNG)

### Branch İşlemleri

        HEAD -> master

MASTER : Genellikle ana branch olarak kullanılır. Bir projenin bitmiş son halini temsil eder.
HEAD -> branch : Bizim git içerisinde hangi konumda (branch) olduğumuzu gösterir. Genellikle son commit'i gösterir.
- Var olan branch'leri görüntülemek için:
```bash
        git branch 
```
![](pictures/gitbranch.PNG)

- Başka bir branch oluşturmak için:
```bash
        git branch BranchAdi 
```
![](pictures/gitbranchN.PNG)

- Başka bir branch'a geçiş yapmak için:
```bash
        git switch BranchAdi 
```
![](pictures/gitswitch.PNG)

- İki branch'ı birleştirmek için:
Hangi branch'a merge'leyeceksek o branch üzerinde olmalıyız.
```bash
        git branch master
        git merge BirlesirilecekBranch
```
```cs
        master  <--  BirlesirilecekBranch
        master branchine BirlesirilecekBranch eklenmiş olur.
```
![](pictures/gitmerge.PNG)

### Fast Forwarding 
 Master branch üzerinde hiçbir değişiklik yapmadan başka bir branch ile ilerleyerek en son Master branch ile birleştirme (merge) işlemidir.

![](pictures/gitfastforward.PNG)

###  Merge Conflict  
Master branc içerisinde commit oluşturarak Merge Conflict işlemini çözebiliriz.
![](pictures/gitconflict1.PNG)
![](pictures/gitconflict2.PNG)
![](pictures/gitconflict3.PNG)
![](pictures/gitconflict4.PNG)

### Stash
Başka bir branch'da oluşturulan bir dosya commit işlemi yapılmadan git'e eklendiyse (git add <>) ve ardından tekrar başka bir branch'e geçildiyse diğer branch'de oluşturulan dosya da geçilen branch'e taşınır.  <br/>
Bu durumu önlemek için kendi branch'imiz üzerindeki değişiklikleri saklayıp tutmamız gerekir. Bunun aşağıdaki kodu kullanırız:
```bash
        git stash 
```
![](pictures/gitstash.PNG)

Diğer branch üzerinde işlerimizi hallettikten sonra, kendi branch'imizde sakladığımız komutları aşağıdaki kod yardımıyla gerçekleştiririz.
```bash
        git stash pop
```
![](pictures/gitstashpop.PNG)

Saklanan verilerin listesini görebilmek için:
```bash
        git stash list
```
![](pictures/gitstashlist.PNG)

İstediğimiz `Stash'i` işleme almak için:
```bash
        git stash apply stash@{i}
```
Stash'i tekrar uygulamaya alsak da gerektiğinde tekrar kullanabilmek adına yine saklanmaya devam eder.
![](pictures/gitstashapply.PNG)

Var olan saklı Stash'lerin hepsini listeden temizlemek için:
```bash
        git stash clear
```
![](pictures/gitstashclear.PNG)

- Çalışma yaptığımız dosya commit attıktan sonra bir şekilde bozulur veya sıkkıntı çıkartırsa ise eski commit'li haline döndürmek için aşağıdaki komutu kullanarak düzeltmemizi yapabiliriz:
```bash
        git restore dosya.uzantıs
```
![](pictures/gitrestore.PNG)

### Checkout
- Commitlerimiz arasında gezinebilmek için:
```bash
        git checkout commitId
```
Detached HEAD : 
![](pictures/gitcheckout0.PNG)
![](pictures/gitcheckout1.PNG)
![](pictures/gitcheckout3.PNG)
![](pictures/gitcheckout2.PNG)

- Yapılacak işlemler yapıldıktan sonra ayrı bir branch oluşturulup devam edilebilir veya alınacak notlar vesayre alındıktan sonra  yapılabilecek en kolay haliyle çalışılan branch'a geri dönülebilir:
```bash
        git switch master
```
![](pictures/gitswitchmaster.PNG)

### Reset vs Revert
- Geçmiş bir `commit'e` dönüm ondan önceki bütün komiyleri kaldırmak için:
```bash
        git switch master
```
![](pictures/gitswitchmaster.PNG)
