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

- Devam eden uzun bir liste karşımıza çıkarsa klavyeden `yön tuşlarıyla` aşağı veya yukarı haraket ettirebiliz.
- Listeden çıkmak için klavyeden `'q'` tuşuna basılması gerekir.

 ![](pictures/TerminalList.PNG)

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

- Diğer branch üzerinde işlerimizi hallettikten sonra, kendi branch'imizde sakladığımız komutları aşağıdaki kod yardımıyla gerçekleştiririz.

```bash
        git stash pop
```
![](pictures/gitstashpop.PNG)

- Saklanan verilerin listesini görebilmek için:

```bash
        git stash list
```
![](pictures/gitstashlist.PNG)

- İstediğimiz `Stash`'i işleme almak için:

```bash
        git stash apply stash@{i}
```
Stash'i tekrar uygulamaya alsak da gerektiğinde tekrar kullanabilmek adına yine saklanmaya devam eder.
![](pictures/gitstashapply.PNG)

- Var olan saklı Stash'lerin hepsini listeden temizlemek için:

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
- Geçmiş bir `commit'e` dönüp ondan önceki bütün commit'leri kaldırmak için - commit'lerdeki değişiklikler silinmez:

```bash
        git reset donulecekCommitId
```
![](pictures/gitreset.PNG)

- Geçmiş bir `commit'e` dönüp ondan önceki bütün commit'leri ve yapılan işlemleri kaldırmak için:

```bash
        git reset --hard donulecekCommitId
```
![](pictures/gitresethard1.PNG)
![](pictures/gitresethard2.PNG)

- Geçmiş bir `commit'e` dönüp ondan önceki commit'leri silmeden yeni commit oluşturarak aynı branch üzerinden devam edebilmek için:

```bash
        git revert donulecekCommitId
```
![](pictures/gitrevert1.PNG)
![](pictures/gitrevert2.PNG)

İki dosya arasındaki değişiklikleri veya oluşan farklılıkları görebilmemiz `git diff` komutuyla sağlarız
- Son `commit` veya başka bir `commit` ile arasında ne gibi değişiklikler var bunları görebilmek için:

```bash
        git diff
```
![](pictures/gitdiff1.PNG)

```bash
        git diff commitId
```
![](pictures/gitdiff3.PNG)
![](pictures/gitdiff4.PNG)

- Üzerinde bulunduğumuz `branch` ile diğer `branch` arasında ne gibi değişiklikler var bunları görebilmek için:

```bash
        git diff BranchAdi
```
![](pictures/gitdiff2.PNG)

- İki farklı `branch` arasında ne gibi değişiklikler var bunları görebilmek için:

```bash
        git diff ilkBranchAdi ikinciBranchAdi 
```
![](pictures/gitdiff5.PNG)

- `git rebase` hem log temizlemek için hem de tarihi tekrar yazmak için kullanılabilir.
`master branch` içerisindeki değişiklikleri kendi branch'inize taşımak isterseniz de kullanabilirsiniz.
Fazladan `merge commit` işlemi yapılmamış olur ve loglar temizlenmiş ve sıralanmış olur.
!! `master branch` üzerinde başka bir ekip arkadaşınızın çalışıyor olmaması gerekir.  
!! Önemli olan `master` branch dışında başka bir branch'de bulunuyor olmaktır.
```bash
        git rebase master
```
![](pictures/gitrebase.PNG)

### GitHub
GitHub, sürüm kontrol sistemi olarak Git kullanan yazılım geliştirme projeleri için web tabanlı bir depolama servisidir. <br/>
Yaptığınız dokümantasyonları Git komutlarını kullanarak paylaşımlı bir şekilde sonradan ulaşabilmenizi sağlayarak depolanızı sağlar. <br/>
GitHub'a yüklemeden önce GitHub'da `Repositories > New` şeklinde veya arama çubuğu yanındaki `+` simgesine tıklayarak `New repository` seçeneğine tıklayarak yeni bir `Repository` oluşturmamız gerekir. Repo'nuza bir isim (Repository name*) ve isteğe bağlı olarak bir açıklama (Description (optional)) ekleyebilirsiniz. <br/>
Diğer kullanıcıların Repo'nuzu görmesini istiyorsanız `Public` seçeneği seçili olmalıdır. <br/>
Diğer kullanıcılar görmesin sadece ben görebileyim derseniz de `Private` seçeneğini seçebilirsiniz. <br/>

- GitHub'ımıza uzaktan bağlanmasını sağlamak için:
- `origin` içerisinde Repo'nun URL'ini tutar.

```bash
        git remote add origin https://github.com/UserName/GitRepoName.git
```
![](pictures/gitremote.PNG)

- Uzak Repo'muza yapılanları gönderebilmek için:
!! Üzerinde bulunduğumuz branch `main branch` (ana branch'ınız hangisiyse o branch) olmalı ve o ana branch'ımızda işlemleri gerçekleştirmeliyiz.  
!! Bu işlemleri yapmadan önce GitHub hesabımızın Git üzerinden oturum açmış olması gerekir.
`-u`, `origin` ve `main`'a push edeceğini tutar.
```bash
        git push -u origin main

        git push origin main
        git push                        -> origin -> main
```
![](pictures/gitpush1.PNG)
![](pictures/gitpush2.PNG)
![](pictures/gitpush3.PNG)

- `Remote branch`'leri görüntülemek için:

```bash
        git branch -r
```
![](pictures/gitbranchR.PNG)
![](pictures/gitbranch-.PNG)

Pull Request : GitHub bize branch'lar arasında çakışma yok ise `merge` yapmamızı sağlayabilir. 
- GitHub'daki değişiklikleri kendi `Local Repo`'muza taşımak için:

```bash
        git fetch origin BranchAdi
```

- Github'daki değişiklikleri eklemek ve ayrı bir branch oluşturmadan kendi branch'imizin üzerine değişiklikleri kaydetmek için:

        git pull = git fetch + git merge

```bash
        git pull 
```

- Başka birisinin GitHub'ındaki Repo'yu kendi Local Repo'muza ekleyebilmek için:

```bash
        git clone https://github.com/AtakanTurgut/DataStructures_Advanced
```
![](pictures/gitclone.PNG)

- Fork işlemi yaparak diğer kullanıcıların Repo'sunu kendi hesabımıza Repo olarak ekleyebiliriz.
- Ardından kendi Repo'muzdan `git clone` komutunu kullanarak kendi `Local Repo`'muzda görebiliriz.'

Private bir Repo'ya geliştirici ekleyebilmek için:

        ReporName       ->      Collaborators        ->         Add peope