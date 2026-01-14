# SQL Nedir?

Veritabanlarında veri yönetimini sağlayan bu dil, bilgilerin düzenlenmesi, saklanması, güncellenmesi ve sorgulanmasını kolaylaştırır. Verilere hızlı bir şekilde erişmek, analiz etmek ve yönetmek için kullanılır. Örneğin, bir şirketin müşteri bilgilerini içeren bir veritabanında, belirli bir müşterinin bilgilerini sorgulamak, yeni müşteri eklemek ya da mevcut verileri güncellemek mümkündür.

Her ne kadar dil olarak adlandırılsa da, klasik anlamda bir programlama dili değildir. Daha çok veri tabanlarıyla iletişim kurmayı sağlayan ve bu sistemlerle konuşabilen bir alt dil olarak tanımlanır.


SQL’in kullanıldığı yaygın veri tabanları:
- Oracle  
- MySQL  
- Microsoft SQL Server  
## SQL Injection Nedir? (SQLi)

---
 
SQL enjeksiyonu (SQLi), bir saldırganın bir uygulamanın veritabanına yaptığı sorgulara müdahale etmesine olanak tanıyan bir web güvenlik açığıdır. Bu, bir saldırganın normalde erişemeyeceği verilere erişmesini sağlar. Bu, diğer kullanıcılara ait verileri veya uygulamanın erişebildiği diğer verileri içerebilir. Çoğu durumda, bir saldırgan bu verileri değiştirebilir veya silebilir ve bu da uygulamanın içeriğinde veya davranışında kalıcı değişikliklere neden olabilir.

---

### SQL Enjeksiyon Saldırısı Nasıl  Gerçekleştirilir?
SQL Enjeksiyon saldırısı gerçekleştirmek için, saldırganın öncelikle web sayfası veya web uygulamasındaki savunmasız kullanıcı girdilerini bulması gerekir. SQL Enjeksiyon güvenlik açığı bulunan bir web sayfası veya web uygulaması, bu tür kullanıcı girdilerini doğrudan bir SQL sorgusunda kullanır. Saldırgan, kendi içeriğini oluşturabilir. Bu tür içerik genellikle kötü amaçlı yük olarak adlandırılır ve saldırının en önemli noktasıdır. Saldırgan bu içeriği gönderdikten sonra, veritabanında kötü amaçlı SQL kodları yürütebilir

Birçok web uygulaması ve web sitesi tüm verilerini SQL veritabanlarında saklar. Bazı durumlarda, işletim sistemi komutlarını çalıştırmak için de SQL komutları kullanabilirsiniz. Bu nedenle, başarılı bir SQL Injection saldırısının çok ciddi sonuçları olabilir.

- Saldırganlar, SQL enjeksiyonlarını kullanarak veritabanındaki diğer kullanıcıların kimlik bilgilerini bulabilirler. Daha sonra bu kullanıcıların kimliğine bürünebilirler. Kimliğine bürünülen kullanıcı, tüm veritabanı ayrıcalıklarına sahip bir veritabanı yöneticisi olabilir.

- SQL, veritabanından veri seçmenize ve çıktı almanıza olanak tanır. SQL Enjeksiyonu güvenlik açığı, saldırganın veritabanı sunucusundaki tüm verilere tam erişim sağlamasına olanak tanıyabilir.

---

## SQL Injection Türleri

SQL Enjeksiyon saldırılarının çeşitli türleri vardır: bant içi SQLi (veritabanı hataları veya UNION komutları kullanılarak), kör SQLi ve bant dışı SQLi .

#### Bantiçi SQLİ
Normal SQL enjeksiyonu, saldırganın saldırıyı gerçekleştirdiği şekilde sonuçları alabilmesi nedeniyle bant içi SQL enjeksiyonu olarak da adlandırılır.

Saldırgan, saldırılarını başlatmak ve sonuçlarını toplamak için aynı iletişim kanalını kullanır. Bant içi SQLi'nin sadeliği ve verimliliği, onu en yaygın SQLi saldırısı türlerinden biri haline getirir. Bu yöntemin iki alt varyasyonu vardır:

- Error-Based SQLi :  Saldırgan , veritabanının hata iletileri üretmesine neden olan eylemler gerçekleştirir. Saldırgan, veritabanının yapısı hakkında bilgi toplamak için bu hata iletileri tarafından sağlanan verileri kullanabilir.
- Union-Based SQL :  Bu teknik , tek bir HTTP yanıtı almak için veritabanı tarafından oluşturulan birden çok seçme ifadeyi birleştiren UNION SQL işlecinden yararlanır. Bu yanıt, saldırgan tarafından kullanılabilecek veriler içerir.


#### Bant dışı SQLi
Bir SQL enjeksiyon saldırısı ve sonuçları farklı kanallar kullandığında, bant dışı  SQL enjeksiyonu söz konusudur. OOB saldırıları, saldırganın istek gönderebildiği ancak yanıtı göremediği durumlarda kullanılır. Yaygın OOB teknikleri arasında saldırı sonuçlarını saldırganın kontrolündeki bir sunucuya göndermek ve bunları DNS sorgularında gizlemek yer alır.

---

## SQLİ Saldırılarından Nasıl Korunulur

 Geliştiriciler , bağlı, belirli parametrelere sahip  veritabanı sorguları ve veritabanında parametreli saklı prosedürlerin dikkatli kullanımı yoluyla web uygulamalarındaki SQL Enjeksiyonu güvenlik açıklarını önleyebilirler  
 
Bu, Java, .NET, PHP ve daha birçok programlama dili kullanılarak gerçekleştirilebilir.

- Kütüphaneler, eklentiler, çerçeveler, web sunucu yazılımı ve veritabanı sunucu yazılımı dahil olmak üzere tüm web uygulama yazılım bileşenlerini temin edilebilen en son güvenlik yamalarıyla güncel tutun.
- Veritabanı hata mesajlarının istemci web tarayıcısına asla gönderilmemesi için web sunucusunda ve kodda uygun hata raporlama ve işleme yapılandırması yapın. Saldırganlar, başarılı bir istismar için sorgularını ayarlamak amacıyla ayrıntılı hata mesajlarındaki teknik detaylardan yararlanabilirler.
- Blacklist yaklaşımında, SQL Injection saldırılarında sıkça kullanılan zararlı karakterler, kelimeler veya desenler engellenmeye çalışılır. (' ,  --  ,  ;  , OR 1=1 ,  UNION SELECT ,  DROP  , INSERT ,  DELETE)

---

#### Sonuç
SQL Injection, günümüzde hâlâ web uygulamaları için ciddi bir tehdit oluşturmaktadır. Bu tür saldırıların önlenmesi için:

- Kullanıcı girdileri doğrulanmalı
- Parametreli sorgular kullanılmalı
- Güvenli yazılım geliştirme prensiplerine uyulmalıdır
- SQL sorgularına filtreleme işlemi yapılmalı
