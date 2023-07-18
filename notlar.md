**en iyi yöntem githubda reportisory açıp onu git clone ile almak.**


### Eğer binlerce dosya source control kısmında gözüküyorsa
- .gitignore dosyası eklenip, commit edilmesi gerekir.
- .gitignore dosyasına /node_modules eklenebilir.
- öncesinde git status ile bakılmalı

### Var olan bir projeyi github'a yüklemek için
- git remote add origin git@github.com:sammy/my-new-project.git
- bu şekilde yapman için önce githubda reportisory açman gerekiyor.

### ???reportisory ile bizim localdeki farklılıklar nasıl sıralanır
- önce **git fetch** sonra **git diff branchIsmi origin/branchIsmi**
- şablonu ise bu **git diff <mainbranch_path> <remotebranch_path>** 

### Var olan bir branch'ın ismini değiştimek için
- o branch'ta
- **git branch -m new-branch-name**


## Kodluyoruz
- **git init** initilaze başlatma
- **git add** ekliyor önce staging area'ya
- **git status** neler değişmiş.
- **git push** sunucuya gönder
- **git pull** sunucudan çek.
- **git clone** kopyasını al
- **git checkout** branchlar arası geçiş yapmak için
- **git rm** dosyaları yapıları silmek için
- **git commit** onayla
- Eğer bir proje açılıp ilk defa versiyon kontrol sistemi kullanılacaksa **git init** bu .git gizli dosyasını oluşturuyor.
- **git status** ile branch'ı, commit'i dosyaları gösteriyor. Bu gösterilen dosyalardan sadece birini seçebilirsin takip edilmesi için:
- **git add takipEdilecek.uzantısı**
- **git rm --cached takipEdilen.uzantısı** takip etmeyi bırakmak için
- **git commit -m 'ne yazmak istiyorsan'** bu şekilde yapılanı işliyorsun.
- MINGW64 aslında bir editor (git bash için) **:q** yaparak iptal edilebilir ya da çıkış yapılabilir.
- .git dosyası silinebilir.
- **M** modified
- **U** untracked
- **.gitignore** dosyası ile versiyon kontrol sisteminin takip etmemesini istediğimiz dosyaları vs belirleyebiliyoruz.
- .gitignore dosyası içine:
- **engellenecek.uzantısı** dosyayı engeller
- **engellenecekDosya/** klasörü engeller
- *.jpg dosya uzantılıları engeller
- **git add .** hepsini ekler
- **git checkout branchismi** o brancha geçiş yapar.
- **git merge branchismi** branchları birleştirir. Master'a gelip son branch'ı merge edersen o master isminde son çalışma olmuş oluyor.
- **Terminalden doğrudan reportisory oluşturamıyorsun. Önce github'dan reportisory oluşturup ona push etmelisi (git clone daha doğru bir tercih)
- commit'ten çok readme dosyasına açıklama yapmak daha doğru.
- git pull yaptığında ordaki değişiklik ne ise onu çekiyorsun. Başka biri o reportisory'de çalışıyorsa yaptığı değişiklikleri çekebiliriz.
- Alternatifler gitlab, bitbucket
- Reportisory'de kendimiz ya da başkası tarafından bir değişiklik var ise bunu **git pull origin branchismi** ile çekebiliyoruz  


## Kadir Kasım
- Yapı şu şekilde çalışma alanın var sonrasında bunu git add ile staged area'ya taşıyorsun commit ederek local reportisory'ni oluşturmuş oluyorsun. Daha sonra ise bunu uzak sunucuya publish etmen gerekiyor
- **pwd** ile hangi klasörde olduğunu görüyorsun
- **ls** ile dosya ve dizinlere ulaşıyorsun
- **ls a** gizli dosyalar
- **mkdir klasörIsmi** klasör oluşturuyor
- **touch dosyaIsmi.uzantısı** o dosyayı oluşturuyor
- **:w** write anlamında
- **rm dosyaIsmi.uzantısı** silmek için
- **rm -r klasörIsmi** klasörü içindekilerle birlikte siler
- **git rm --cached dosyaIsmi.uzatisi** untracked olmuş olur
- **git log** commitleri gösteriyor
- **git log --oneline** kısaltarak gösteriyor
- **git reset 468600 (commit id ne ise)** eğer bundan sonra **--hard** eklersen hepsini siliyor
- **soft** der ise sadece staged area'ya alıyorW
- **git reset 468600 (commit id ne ise)** işlemleri terse çeviriyor
- **git amend -m "varolan commit değişikliği"** var olan commit mesajını değiştiriyor
- **git branch branchIsmi** branch oluşturuyor
- **git branch -a** branch listesini veriyor. Yeşil hangi branch üstünde olduğunu gösteriyor
- **git checkout** hangi branch'e gitmek istiyorsan ona gidiyorsun
- **git checkout -b branchIsmi** branch'i oluşturup geçiş yapar
- **git branch -d branchIsmi** branch'ı siliyor. Bulunduğun branch'ta isen silemiyor. hata veriyorsa -D kullanmalısın.
- **git merge branchIsmi** hangi branchta isen branchIsmi yazdığındakileri ona birleştiriyor
### Ders 11 
- Alternatifleri gitlab, bitbucket
- **git push reportisoryLink branchIsmi** var olanları o projeye gönderir
- **git remote add origin reportisoryLinK(uzakbağlantılinki)** bu şekilde artık dosyaların gönderileceği yer belirli olmuş oluyor
- **git remote -v** bu şekilde remote ettiğin bağlantılar sıralanıyor
- **git push origin master** bu şekilde artık link vermeden gönderebiliyorsun

- Önce githubda reportisory oluşturup sonrasında klonlayarak onu almak daha iyi bir yöntem
- **git remote -v** diyerek uzak bağlantı noktasını görüyorsun

- fork ettiğinde diğer kullanıcıya bir müdahalede bulunmuyorsun
- Eğer diğer kullanıcının haberi olmasını istiyorsan pull request yapıyorsun (ders13) bu da ana kullanıcının reportisory'sinde pull requests kısmında gözüküyor

### Ders 14 fetch ve pull
- **git fetch origin** dosyaları getirdi ama işlem yapmadı merge edilmesi gerekiyor
- **git merge origin/branchIsmi** hangi branch yazıldıysa ona getirir.
- **git pull origin branchIsmi** doğrudan değişik olan dosyaları getiriyor.

### Ders 15
- dizin/* .gitignore dosyası içinde o dizin altındaki herşeyi saklar
- !dizin/saklanacakDosyaIsmi.uzatisi o dizin altındaki sadece o dosyayi saklar

- ???reportisory ile bizim localdeki farklılıklar nasıl sıralanır
- önce **git fetch** sonra **git diff branchIsmi origin/branchIsmi**
- şablonu ise bu **git diff <mainbranch_path> <remotebranch_path>** 

### ders16
- github'ın kendi readme'sinde preview yapmak daha kullanışlı
- markdown syntax için : [Link](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

- Tablo oluşturmak için [Link](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/organizing-information-with-tables)

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

| First Header  | Second Header |
| --- | --- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

- "---" çizgi koymak yeterli

| Left-aligned | Center-aligned | Right-aligned |
| :---         |     :---:      |          ---: |
| git status   | git status     | git status    |
| git diff     | git diff       | git diff      |


- branchta bir değişiklik var mı git status
- git checkout -- dosyaIsmi.uzantisi değişiklik varsa geri alıyor

??? Değişikliğe uğramış branch hangisi bunu nasıl bilicez

