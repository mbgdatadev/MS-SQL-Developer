- [SQL Nedir](#sql-nedir)
- [Veritabani Nedir](#veritabani-nedir)
- [SQL Server Kurulumu](#sqlserver-kurulumu)
- [SQL Connetion](#sql-connection)
- [Veri Tabani Olusturma](#veri-tabani-olusturma)




## SQL Nedir
SQL (Structured Query Language), veritabanlarıyla etkileşimde bulunmak için kullanılan bir programlama dilidir. SQL, veritabanlarında veri sorgulama, ekleme, güncelleme ve silme işlemleri yapmanın yanı sıra, veritabanı yapısını (tablolar, indeksler, görünümler) tanımlamak ve kontrol etmek için kullanılır.

SQL'in temel komutları arasında şunlar yer alır:

- **SELECT:** Veritabanından veri sorgulamak için kullanılır.
- **INSERT:** Veritabanına yeni veri eklemek için kullanılır.
- **UPDATE:** Veritabanındaki mevcut veriyi güncellemek için kullanılır.
- **DELETE:** Veritabanındaki veriyi silmek için kullanılır.
- **CREATE TABLE:** Yeni bir tablo oluşturmak için kullanılır.
- **DROP TABLE:** Bir tabloyu silmek için kullanılır.
SQL, çeşitli veritabanı yönetim sistemleri (DBMS) tarafından desteklenir, bunlar arasında MySQL, PostgreSQL, Microsoft SQL Server ve Oracle Database bulunur. SQL'in standartları olsa da, her DBMS'in bazı özgün özellikleri ve genişletmeleri olabilir.
***

## Veritabani Nedir
Veritabanı, yapılandırılmış verilerin saklandığı, düzenlendiği ve yönetildiği bir bilgi deposudur. Veritabanları, büyük miktarda veriyi etkili bir şekilde depolamak, erişmek ve yönetmek için tasarlanmıştır. Veritabanları, bilgileri tablo, satır ve sütunlar gibi mantıksal yapılarla düzenler ve bu sayede veriler kolayca aranabilir, sıralanabilir ve analiz edilebilir hale gelir.


#### 
Veritabanlarının bazı temel özellikleri şunlardır:

- **Veri Saklama:** Büyük miktarda veriyi kalıcı olarak saklama imkanı sağlar.
- **Veri Yönetimi:** Verilerin eklenmesi, güncellenmesi, silinmesi ve sorgulanması için araçlar sunar.
- **Veri Bütünlüğü:** Verilerin doğruluğunu ve tutarlılığını sağlamak için kısıtlamalar ve kurallar uygulanır.
- **Veri Güvenliği:** Yetkisiz erişime karşı verileri korumak için güvenlik önlemleri alınır.
- **Veri Yedekleme ve Kurtarma:** Verilerin kaybolması durumunda yedekleme ve kurtarma işlemleri için mekanizmalar bulunur.

#### Veritabanları, ilişkisel ve ilişkisel olmayan (NoSQL) olmak üzere iki ana kategoriye ayrılır:

- **İlişkisel Veritabanları (RDBMS):** Veriler tablolar halinde saklanır ve SQL kullanılarak yönetilir. Örneğin, MySQL, PostgreSQL, Microsoft SQL Server.
- **İlişkisel Olmayan Veritabanları (NoSQL):** Veriler belge, anahtar-değer, grafik veya sütun aileleri gibi farklı yapılarla saklanır. Daha esnek veri modellerine sahiptir. Örneğin, MongoDB, Redis, Cassandra.
Veritabanları, modern yazılım uygulamalarında verilerin etkili bir şekilde saklanması ve yönetilmesi için kritik bir rol oynar.

***

## SQLServer Kurulumu
Sql Server next next şeklinde hızlaca kura bilirsin sadece aşağıda adımlarda dikkat et.

1. Sql Server kurulum dosyasını çalıştır.
2. New SQL Server stand-alone installation or add features to an existing installation tıkla.
3.  Featur Selection gelince Database Engine Services seçiyoruz.
4.  Database Engine Configuration gelince Mixed Mode bir şifre ver örneğin Sa123456* ve Add Current User butonuna tıkla
5. SQL Server Managment Studio kur.
***
## SQL Connetion
SQL Connection (SQL Bağlantısı), bir uygulama ile bir SQL veritabanı arasında iletişim kurulmasını sağlayan bir bağlantıdır. Bu bağlantı, uygulamanın veritabanına erişmesini, veri sorgulaması yapmasını, veri eklemesini, güncellemesini veya silmesini mümkün kılar.

SQL Server Managment Studio açtığımızda Server name yerine 
- `.`
- `localhost`
- `(local)`
- `Lenovo-CV855T98` ->Kullandığınız PC Adı
- Yukarıdaki isimleri yazarsak Windows Authentication ile sql server bağlana biliriz.
- `127.0.0.1` -> Named Pipes hatası alırsanız Sql server configuration manager aç. Sql server Network Configuration tıkla Named Pipes ve TCP/IP enable hale getir. Sql Server Restart işlemi yap. Sonra Windows Authentication ile sql server bağlana biliriz.
- `192.168.1.39` -> Active Directory yoksa kendi ip'niz ile Windows Authentication ile sql server bağlanamazsınız.
                     Sql Server Authentication ile login ve password girerek bağlana bilirsiniz. Örneğin Login:`sa` 
                     ve  Password:`Sa123456*` sql server kurarken `sa` için belirlediğiniz şifre.
  ***

  ## Veri Tabani Olusturma
Microsoft SQL Server'da yeni bir veritabanı oluşturmanın iki yolu vardır: T-SQL komutları kullanarak (kod ile) ve SQL Server Management Studio (SSMS) kullanarak (fare ile). Her iki yöntemi de aşağıda açıklayacağım. Sql Server bir database iki dosyadan bir `mdf` diğeri `ldf` tir. `mdf` data dosyasıdır, `ldf` log dosyasıdır.
#### 1. T-SQL Komutları ile (Kod ile)

```sql
CREATE DATABASE VeritabaniAdi;
```
#### 2. SQL Server Management Studio (SSMS) ile (Fare ile)
- SSMS'i Başlatın: SQL Server Management Studio'yu başlatın ve SQL Server'a bağlanın.
- Veritabanları Düğümüne Sağ Tıklayın: Object Explorer penceresinde, "Databases" düğümüne sağ tıklayın.
- Yeni Veritabanı Oluşturun: Açılan menüden "New Database..." seçeneğine tıklayın.
- Veritabanı Adını Girin: Açılan "New Database" penceresinde, oluşturmak istediğiniz veritabanının adını girin (örneğin, "MyDatabase").
- Diğer Ayarları Yapın (Opsiyonel): Bu pencerede veritabanının dosya adları, boyutları ve büyüme ayarları gibi ek ayarları yapabilirsiniz.
- Veritabanını Oluşturun: "OK" düğmesine tıklayarak veritabanını oluşturun.

Her iki yöntem de veritabanınızı başarıyla oluşturacaktır. Kod yöntemi, özellikle otomatikleştirilmiş işlemler veya betik oluşturma için kullanışlıdır. Fare yöntemi ise görsel bir arayüz kullanarak işlemleri daha sezgisel bir şekilde yapmanızı sağlar.


  
