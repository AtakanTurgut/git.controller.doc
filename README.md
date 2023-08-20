# Git & GitHub : [Version Control](README.md)
Git : It is a Version Control System.

### [Git Installation for Windows](#)
[[Source]](https://git-scm.com/download/win) for installing Git on Windows..       <br/>
Using the presets, we click the `Next` button and pass. Lastly, we start the installation by clicking on the 'Install' option, and after installing it, we close it by clicking the 'Finish' button.
```bash
        git --version
```
After successfully completing the installation, we can check the Git version using the code above.  <br/>
We write the commands in the `Git Bash` command processor after installation.
![](pictures/gitIm1.PNG)

### [Git Installation for Mac and Linux](#)
Mac and Linux systems already have Git installed. <br/>
If it is not installed on the system and we need to install it [[source]](https://git-scm.com/download).   <br/>
Git can be installed using the Binary Installer.
```bash
        git --version 
```     

Using the above command we can see if Git is running or not.
```bash
        git
```
If Git is installed, we can access Git Documentation by entering the above command.

### [Git Bash - Terminal Usage](#)
Git commands for Windows, Mac and Linux are no different, they are the same.

- Shows other folders and documents in the current directory.

```bash
        ls      
```
![](pictures/ls.PNG)

- If we want to see the hidden files in the folder:

```bash
        ls -la      
```
![](pictures/ls-la.PNG)

- Bulunduğumuz dizini bulmak için:

```bash
        pwd
```
![](pictures/pwd.PNG)

- To access other folders in the directory:

```bash
        cd KlasorAdi
```
![](pictures/cd.PNG)

- To go to the previous directory:

```bash
        cd ..
```
![](pictures/cd...PNG)

- To clear terminal outputs:

```bash
        clear
```

- To create a folder in a directory:

```bash
        mkdir KlasorAdi
```
![](pictures/mkdir.PNG)

- To create a file in the directory:

 ```bash
        touch dosya.uzantısı
 ```
 ![](pictures/touch.PNG)

 - To remove files from the directory:

```bash
        rm dosya.uzantısı
 ```
 ![](pictures/rm.PNG)

- To remove a folder from the directory:

```bash
        rm -rf KlasorAdi
```
 ![](pictures/rm-rf.PNG)

- If we come across a long list that continues, we can move it up or down with the 'arrow keys' from the keyboard.
- To exit the list, `'q'' keys must be pressed on the keyboard.

 ![](pictures/TerminalList.PNG)

### [Entering Username and Email](#)
- To save your Git username and email information:

```bash
        git config --global user.name "UserName Surname"

        git config user.name
```
 ![](pictures/configUserName1.PNG)
 ![](pictures/configUserName2.PNG)

- To save email information to the Git system:

```bash
        git config --global user.email user@email.com

        git config user.email
```
 ![](pictures/configUserEmail.PNG)

### [Git Basic Commands](#)
```cs
        Work Folder      =>      Index - Staging       =>       Local Repository
                          git add                      git commit
```

- To show the current state of Git:

```bash
        git status
```
It's always correct to check git status before running "git init" anywhere. <br/>
Otherwise, several different activations of git may cause conflicts.
 ![](pictures/gitstatus.PNG)

 - To enable Git in the folder:     runs as master or master branch.

 ```bash
        git init
```
 ![](pictures/gitinit.PNG)

 - To add files or folders to Git:

```bash
        git add dosya.uzantısı
```
 ![](pictures/gitadd.PNG)

- To add it to Git:

```bash
        git add .
```
 ![](pictures/gitadd..PNG)

- To add commits to Git:

```bash
        git commit -m "commit message"
```
- The processing message should be descriptive of what has been done.

 ![](pictures/gitcommit.PNG)

 - To view transactions:

 ```bash
        git log
```
Each commit has its own transaction number. <br/>
It is used for this purpose when it is desired to go to the processing center.

        HEAD -> master

Shows the current branch.
![](pictures/gitlog.PNG)

- To re-introduce what's been done in Git and re-enable the controls, briefly:

```bash
        git add .
        git commit -m "commit message"
        git status
        git log
```
![](pictures/gitbref.PNG)

We don't want to save the files we don't want to share in `Local Repo`.
- `git add` needs to be done..
- First we need to create a file named `.gitignore`.

```bash
        touch .gitignore
```
gitignore file, we must write the file that we want to be hidden with its extension.
Incognito file is no longer protected by Git.
```cs
        gitignore  ==>  file.extention
```
![](pictures/gitignore2.PNG)
![](pictures/gitignore1.PNG)

### [Branch İşlemleri](#)

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

### [Fast Forwarding](#)
 Master branch üzerinde hiçbir değişiklik yapmadan başka bir branch ile ilerleyerek en son Master branch ile birleştirme (merge) işlemidir.

![](pictures/gitfastforward.PNG)

### [Merge Conflict](#)
Master branc içerisinde commit oluşturarak Merge Conflict işlemini çözebiliriz.
![](pictures/gitconflict1.PNG)
![](pictures/gitconflict2.PNG)
![](pictures/gitconflict3.PNG)
![](pictures/gitconflict4.PNG)

### [Stash](#)
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

### [Checkout](#)
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

### [Reset vs Revert](#)
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

### [GitHub](#)
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

        RepoName       ->      Collaborators        ->         Add peope