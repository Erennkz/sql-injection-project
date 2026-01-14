# SQL Injection (SQLi)

SQL Injection (SQLi), web uygulamalarında en yaygın ve en tehlikeli güvenlik açıklarından biridir. Bu doküman, SQL kavramını, SQL Injection’ın nasıl çalıştığını, etkilerini ve saldırı türlerini temel seviyede açıklamayı amaçlamaktadır.

---

## SQL Nedir?

SQL, bir web sitesinde veya uygulamada kullanılan veri tabanına erişmeyi ve bu veri tabanı üzerinde işlem yapmayı sağlayan bir araçtır. *Structured Query Language* ifadesinin baş harflerinden oluşan SQL, Türkçeye **Yapılandırılmış Sorgu Dili** olarak çevrilebilir.

Her ne kadar “dil” olarak adlandırılsa da, klasik anlamda bir programlama dili değildir. Daha çok veri tabanlarıyla iletişim kurmayı sağlayan ve bu sistemlerle konuşabilen bir alt dil olarak tanımlanabilir.

SQL, veri tabanı kullanan sistemlerde veri tabanlarıyla etkileşim sağlamak amacıyla geliştirilmiştir. Veri tabanında bulunan verilere erişme, sorgulama, değiştirme ve silme işlemleri SQL aracılığıyla gerçekleştirilir. Günümüzde yaygın olarak kullanılan birçok veri tabanı SQL ile ilişkilidir.

SQL kullanılarak:
- Veriler sorgulanabilir
- Yeni kayıtlar oluşturulabilir
- Mevcut kayıtlar güncellenebilir veya silinebilir
- Veri tabanı erişim yetkileri düzenlenebilir

SQL’in kullanıldığı yaygın veri tabanları:
- Oracle  
- MySQL  
- Microsoft SQL Server  
- Microsoft Access  

---

## SQL Injection (SQLi) Nedir?

SQL Injection, bir web uygulamasının veri tabanına gönderdiği SQL sorgularının saldırganlar tarafından manipüle edilmesine olanak tanıyan bir güvenlik açığıdır. Bu açık, uygulamanın kullanıcıdan aldığı girdileri yeterince doğrulamaması durumunda ortaya çıkar.

Bu güvenlik açığı sayesinde saldırganlar:
- Yetkisiz veri erişimi sağlayabilir
- Uygulama güvenlik mekanizmalarını aşabilir
- Hassas bilgileri ele geçirebilir

---

## SQL Injection Nasıl Çalışır?

SQL Injection saldırıları genellikle kullanıcıdan veri alınan alanlar üzerinden gerçekleştirilir. Bunlara örnek olarak:
- Form alanları
- Arama kutuları
- URL parametreleri

verilebilir.

Kullanıcı girdileri doğru şekilde filtrelenmediğinde veya doğrulanmadığında, saldırganlar bu alanlara kötü amaçlı SQL ifadeleri ekleyerek uygulamanın çalıştırdığı sorguların yapısını değiştirebilir.

---

## Etkilenen Veri Tabanları

SQL Injection açıkları, SQL tabanlı veri tabanlarını kullanan birçok uygulamayı etkileyebilir. En yaygın kullanılanlar:
- MySQL  
- Oracle  
- SQL Server  

---

## Olası Etkiler

Bir SQL Injection açığının istismar edilmesi durumunda saldırganlar:
- Uygulamanın güvenlik kontrollerini aşabilir
- Kimlik doğrulama mekanizmalarını devre dışı bırakabilir
- Veri tabanlarına yetkisiz erişim sağlayabilir
- Hassas verileri görüntüleyebilir, değiştirebilir veya silebilir

---

## SQL Injection Türleri

SQL Injection saldırıları, saldırganların veri tabanına erişim yöntemine ve oluşturdukları etkiye göre üç ana kategoriye ayrılır.

### In-Band SQL Injection
Bu saldırı türünde, saldırıyı başlatmak ve sonuçları almak için aynı iletişim kanalı kullanılır. En yaygın ve en basit SQLi yöntemidir.

Alt türleri:
- **Error-Based SQLi:**  
  Veri tabanının ürettiği hata mesajları kullanılarak sistem hakkında bilgi toplanır.
- **Union-Based SQLi:**  
  `UNION` operatörü kullanılarak birden fazla sorgu tek bir yanıt içinde birleştirilir.

### Inferential SQL Injection (Blind SQLi)
Bu yöntemde veri tabanından doğrudan veri alınmaz. Saldırgan, uygulamanın verdiği tepkilere bakarak veri tabanı hakkında çıkarım yapar.

Alt türleri:
- **Time-Based SQLi:**  
  Sorgunun doğru veya yanlış olmasına göre sistemin yanıt süresi değişir.
- **Boolean-Based SQLi:**  
  Uygulamanın doğru veya yanlış yanıt üretmesi analiz edilir.

### Out-of-Band SQL Injection
Bu saldırı türünde, saldırının başlatılması ve verilerin elde edilmesi için farklı iletişim kanalları kullanılır. Genellikle bant içi yöntemlerin kullanılamadığı durumlarda tercih edilir.

---

## Sonuç

SQL Injection, günümüzde hâlâ web uygulamaları için ciddi bir tehdit oluşturmaktadır. Bu tür saldırıların önlenmesi için:
- Kullanıcı girdileri doğrulanmalı
- Parametreli sorgular kullanılmalı
- Güvenli yazılım geliştirme prensiplerine uyulmalıdır
