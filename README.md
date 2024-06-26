- [SQL Nedir](#sql-nedir)
- [Veritabani Nedir](#veritabani-nedir)
- [SQL Server Kurulumu](#sqlserver-kurulumu)
- [SQL Connetion](#sql-connection)
- [Veri Tabani Olusturma](#veri-tabani-olusturma)
- [Veri Tipleri ve Normalizasyon](#veri-tipleri-ve-normalizasyon)
- [Veri Tabani Komutları](#veri-tabani-komutları)
- [SELECT Komutu](#select-komutu)
- [INSERT Komutu](#insert-komutu)
- [UPDATE Komutu](#update-komutu)
- [DELETE Komutu](#delete-komutu)
- [TRUNCATE Komutu](#truncate-komutu)
- [WHERE Sarti Kavrami](#where-sarti-kavrami)
- [DISTINCT Komutu](#distinct-komutu)
- [ORDER BY Komutu](#order-by-komutu)
- [TOP Komutu](#top-komutu)
- [ALTER Komutu](#alter-komutu)
- [DROP Komutu](#drop-komutu)
- [Aggregate Functions](#aggregate-functions)
- [GROUP BY Kavrami](#group-by-kavrami)
- [Iliskisel Veritabani Nedir](#iliskisel-veritabani-nedir)
- [JOIN Turleri](#join-turleri)
   





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
#### 1. SQL Server Management Studio (SSMS) ile (Fare ile)
- SSMS'i Başlatın: SQL Server Management Studio'yu başlatın ve SQL Server'a bağlanın.
- Veritabanları Düğümüne Sağ Tıklayın: Object Explorer penceresinde, "Databases" düğümüne sağ tıklayın.
- Yeni Veritabanı Oluşturun: Açılan menüden "New Database..." seçeneğine tıklayın.
- Veritabanı Adını Girin: Açılan "New Database" penceresinde, oluşturmak istediğiniz veritabanının adını girin (örneğin, "MyDatabase").
- Diğer Ayarları Yapın (Opsiyonel): Bu pencerede veritabanının dosya adları, boyutları ve büyüme ayarları gibi ek ayarları yapabilirsiniz.
- Veritabanını Oluşturun: "OK" düğmesine tıklayarak veritabanını oluşturun.

Her iki yöntem de veritabanınızı başarıyla oluşturacaktır. Kod yöntemi, özellikle otomatikleştirilmiş işlemler veya betik oluşturma için kullanışlıdır. Fare yöntemi ise görsel bir arayüz kullanarak işlemleri daha sezgisel bir şekilde yapmanızı sağlar.

#### 2. T-SQL Komutları ile Tablo Olştur (Kod ile)
  Öncelikle, veritabanınızı seçtiğinizden emin olun. Aşağıdaki komutları bir sorgu penceresine yapıştırarak çalıştırabilirsiniz:


```sql
USE MyDatabase; -- Veritabanınızı seçin

CREATE TABLE Customer (
    CustomerID INT PRIMARY KEY IDENTITY(1,1),
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    Email NVARCHAR(100),
    Phone NVARCHAR(15),
    Address NVARCHAR(200),
    CreatedDate DATETIME DEFAULT GETDATE()
);

```


#### 2. SQL Server Management Studio (SSMS) ile (Fare ile)
1. **SSMS'i Başlatın:** SQL Server Management Studio'yu başlatın ve SQL Server'a bağlanın.
2. **Veritabanınızı Seçin:** Object Explorer penceresinde, MyDatabase (veya kullanmak istediğiniz veritabanı) adını genişletin.
3. **Tablolar Düğümüne Sağ Tıklayın:** "Tables" düğümüne sağ tıklayın.
4. **Yeni Tablo Oluşturun:** Açılan menüden "Table" seçeneğine tıklayın. Yeni bir tablo tasarım penceresi açılacaktır.
5. **Kolonları Ekleyin:*
      - `CustomerID:` Column Name alanına CustomerID yazın, Data Type olarak INT seçin, Allow Nulls kutusunu işaretlemeyin. Sağ tıklayıp Primary Key olarak ayarlayın ve Identity özelliğini Yes olarak ayarlayın.
      - `FirstName:` Column Name alanına FirstName yazın, Data Type olarak NVARCHAR(50) seçin.
      - `LastName:` Column Name alanına LastName yazın, Data Type olarak NVARCHAR(50) seçin.
      - `Email:` Column Name alanına Email yazın, Data Type olarak NVARCHAR(100) seçin.
      - `Phone` Column Name alanına Phone yazın, Data Type olarak NVARCHAR(15) seçin.
      - `Address:` Column Name alanına Address yazın, Data Type olarak NVARCHAR(200) seçin.
      - `CreatedDate:` Column Name alanına CreatedDate yazın, Data Type olarak DATETIME seçin. Default Value kısmına GETDATE() yazın.

6. **Tabloyu Kaydedin:** Tablonuzu kaydetmek için sağ üst köşedeki disket simgesine tıklayın veya Ctrl + S tuşlarına basın. Tablonuz için bir ad girin, örneğin Customer.
Bu adımları takip ederek Customer adında bir tablo oluşturabilirsiniz. Kod yöntemi hızlı ve otomatize edilebilir bir çözüm sunarken, fare yöntemi daha sezgisel ve görseldir.


***

## Veri Tipleri ve Normalizasyon

Microsoft SQL Server'da tam sayı veri tipleri, farklı boyutlarda ve aralıklarda tam sayı değerlerini depolamak için kullanılır. İşte SQL Server'daki başlıca tam sayı veri tipleri ve kısa açıklamaları:

#### Tam Sayı Veri Tipleri
- **TINYINT**
  - Depolama Alanı: 1 bayt
  - Değer Aralığı: 0 ile 255 arasında

- **SMALLINT**
  - Depolama Alanı: 2 bayt
  - Değer Aralığı: -32,768 ile 32,767 arasında

- **INT**
  - Depolama Alanı: 4 bayt
  - Değer Aralığı: -2,147,483,648 ile 2,147,483,647 arasında

- **BIGINT**
  - Depolama Alanı: 8 bayt
  - Değer Aralığı: -9,223,372,036,854,775,808 ile 9,223,372,036,854,775,807 arasında

- **BIT**
  - Depolama Alanı: 1 bit
  - Değer Aralığı: 0 ile 1 arasında (boolean değerler için kullanılır)

***
#### Metin Veri Tipleri

- **CHAR(n)**
  - Depolama Alanı: Sabit uzunlukta n karakter (her karakter 1 bayt)
  - Açıklama: Sabit uzunlukta metin depolamak için kullanılır. Belirtilen n uzunluğunda alan ayırır. Kısa metinlerde boşluklarla doldurulur.

- **VARCHAR(n)**
  - Depolama Alanı: Değişken uzunlukta n karakter (her karakter 1 bayt)
  - Açıklama: Değişken uzunlukta metin depolamak için kullanılır. Belirtilen n uzunluğa kadar alan ayırır, ancak yalnızca gerçek verinin uzunluğu kadar yer kaplar.

- **TEXT**
  - Depolama Alanı: Değişken uzunlukta metin (2 GB'a kadar)
  - Açıklama: Büyük metin blokları depolamak için kullanılır. Bu veri tipi eski sürümlerde kullanılıyordu ve modern uygulamalarda VARCHAR(MAX) yerine kullanılması tavsiye edilmez.

- **NCHAR(n)**
  - Depolama Alanı: Sabit uzunlukta n karakter (her karakter 2 bayt)
  - Açıklama: Sabit uzunlukta Unicode metin depolamak için kullanılır. Belirtilen n uzunluğunda alan ayırır. Kısa metinlerde boşluklarla doldurulur.

- **NVARCHAR(n)**
  - Depolama Alanı: Değişken uzunlukta n karakter (her karakter 2 bayt)
  - Açıklama: Değişken uzunlukta Unicode metin depolamak için kullanılır. Belirtilen n uzunluğa kadar alan ayırır, ancak yalnızca gerçek verinin uzunluğu kadar yer kaplar.

- **NVARCHAR(MAX)**
  - Depolama Alanı: Değişken uzunlukta Unicode metin (2 GB'a kadar)
  - Açıklama: Çok büyük Unicode metin blokları depolamak için kullanılır. VARCHAR(MAX) ile benzer, ancak Unicode karakterler için kullanılır.

- **NTEXT**
  - Depolama Alanı: Değişken uzunlukta Unicode metin (2 GB'a kadar)
  - Açıklama: Büyük Unicode metin blokları depolamak için kullanılır. Bu veri tipi eski sürümlerde kullanılıyordu ve modern uygulamalarda NVARCHAR(MAX) yerine kullanılması tavsiye edilmez.
***

#### Ondalık Veri Tipleri

- **FLOAT**
  - Depolama Alanı: 4 bayt (float) veya 8 bayt (real)
  - Açıklama: Yaklaşık olarak kayan noktalı sayılar depolamak için kullanılır. Değer aralığı ve kesinlik, belirtildiği hassasiyet seviyesine bağlıdır. Daha fazla kesinlik gerektiren uygulamalarda `FLOAT(53)` kullanılması yaygındır.

- **REAL**
  - Depolama Alanı: 4 bayt
  - Açıklama: Yaklaşık olarak kayan noktalı sayılar depolamak için kullanılır. `FLOAT(24)` eşdeğeridir ve daha az bellek kullanır ancak daha düşük kesinlik sağlar.

- **DECIMAL(p, s)**
  - Depolama Alanı: Kullanılan hassasiyet ve ölçeklere bağlı olarak 5 ila 17 bayt
  - Açıklama: Sabit ondalık noktası ile kesin sayısal veriler depolamak için kullanılır. `p` (precision) toplam basamak sayısını, `s` (scale) ondalık basamak sayısını belirler. Yüksek kesinlik gerektiren finansal ve bilimsel hesaplamalar için idealdir.

- **NUMERIC(p, s)**
  - Depolama Alanı: Kullanılan hassasiyet ve ölçeklere bağlı olarak 5 ila 17 bayt
  - Açıklama: `DECIMAL` veri tipi ile eşdeğerdir. Sabit ondalık noktası ile kesin sayısal veriler depolamak için kullanılır. `p` (precision) toplam basamak sayısını, `s` (scale) ondalık basamak sayısını belirler.

- **MONEY**
  - Depolama Alanı: 8 bayt
  - Açıklama: Para birimi değerlerini depolamak için kullanılır. 4 ondalık basamağa kadar hassasiyet sağlar ve -922,337,203,685,477.5808 ile 922,337,203,685,477.5807 arasında değerler depolar.

- **SMALLMONEY**
  - Depolama Alanı: 4 bayt
  - Açıklama: Daha küçük aralıktaki para birimi değerlerini depolamak için kullanılır. 4 ondalık basamağa kadar hassasiyet sağlar ve -214,748.3648 ile 214,748.3647 arasında değerler depolar.

***
 #### Tarih ve Saat Veri Tipleri

 - **DATE**
  - Depolama Alanı: 3 bayt
  - Açıklama: Yalnızca tarih verilerini depolamak için kullanılır. 0001-01-01 ile 9999-12-31 arasındaki tarihleri destekler.

- **TIME**
  - Depolama Alanı: 3 ila 5 bayt
  - Açıklama: Yalnızca saat verilerini depolamak için kullanılır. 00:00:00.0000000 ile 23:59:59.9999999 arasındaki zamanları destekler. Kesinlik 100 nanosaniye.

- **DATETIME**
  - Depolama Alanı: 8 bayt
  - Açıklama: Tarih ve saat verilerini depolamak için kullanılır. 1753-01-01 00:00:00.000 ile 9999-12-31 23:59:59.997 arasındaki tarih ve saatleri destekler. Kesinlik 3.33 milisaniye.

- **DATETIME2**
  - Depolama Alanı: 6 ila 8 bayt
  - Açıklama: Gelişmiş tarih ve saat verilerini depolamak için kullanılır. 0001-01-01 00:00:00.0000000 ile 9999-12-31 23:59:59.9999999 arasındaki tarih ve saatleri destekler. Kesinlik 100 nanosaniye.

- **SMALLDATETIME**
  - Depolama Alanı: 4 bayt
  - Açıklama: Daha küçük aralıktaki tarih ve saat verilerini depolamak için kullanılır. 1900-01-01 00:00:00 ile 2079-06-06 23:59:59 arasındaki tarih ve saatleri destekler. Kesinlik 1 dakika.

- **DATETIMEOFFSET**
  - Depolama Alanı: 10 bayt
  - Açıklama: Saat dilimi bilgisi ile birlikte tarih ve saat verilerini depolamak için kullanılır. 0001-01-01 00:00:00.0000000 ile 9999-12-31 23:59:59.9999999 UTC arasında tarih ve saatleri destekler. Kesinlik 100 nanosaniye.

- **TIMESTAMP**
  - Depolama Alanı: 8 bayt
  - Açıklama: Her değişiklik yapıldığında otomatik olarak güncellenen bir benzersiz numara (sürüm damgası) depolar. Zaman bilgisi içermez, veri satırındaki değişiklikleri izlemek için kullanılır. `ROWVERSION` ile eşdeğerdir.
***

#### Diğer Veri Tipleri
- **BINARY(n)**
  - Depolama Alanı: Sabit uzunlukta n bayt
  - Açıklama: Sabit uzunlukta ikili veri depolamak için kullanılır. n, 1 ile 8,000 arasında bir değer olabilir.

- **VARBINARY(n)**
  - Depolama Alanı: Değişken uzunlukta n bayt
  - Açıklama: Değişken uzunlukta ikili veri depolamak için kullanılır. n, 1 ile 8,000 arasında bir değer olabilir.

- **VARBINARY(MAX)**
  - Depolama Alanı: Değişken uzunlukta ikili veri (2 GB'a kadar)
  - Açıklama: Çok büyük ikili veri blokları depolamak için kullanılır. Örneğin, dosyalar veya görüntüler.

- **IMAGE**
  - Depolama Alanı: Değişken uzunlukta ikili veri (2 GB'a kadar)
  - Açıklama: Büyük ikili veri blokları depolamak için kullanılır. Bu veri tipi eski sürümlerde kullanılıyordu ve modern uygulamalarda VARBINARY(MAX) yerine kullanılması tavsiye edilmez.

- **UNIQUEIDENTIFIER**
  - Depolama Alanı: 16 bayt
  - Açıklama: Küresel benzersiz tanımlayıcı (GUID) depolamak için kullanılır. Genellikle benzersiz anahtarlar için kullanılır.

- **ROWVERSION**
  - Depolama Alanı: 8 bayt
  - Açıklama: Her değişiklik yapıldığında otomatik olarak güncellenen bir benzersiz numara (sürüm damgası) depolar. Zaman bilgisi içermez, veri satırındaki değişiklikleri izlemek için kullanılır. `TIMESTAMP` ile eşdeğerdir.

- **SQL_VARIANT**
  - Depolama Alanı: 8,016 bayta kadar
  - Açıklama: Farklı veri tiplerinde veri depolamak için kullanılır. Aynı kolon içinde farklı veri tipleri depolamak gerektiğinde kullanılır.

- **XML**
  - Depolama Alanı: 2 GB'a kadar
  - Açıklama: XML verilerini depolamak ve sorgulamak için kullanılır. XML veri tipindeki veriler üzerinde XQuery ile sorgulamalar yapılabilir.

- **CURSOR**
  - Depolama Alanı: Değişken
  - Açıklama: Veri kümesinde gezinmek ve işlem yapmak için kullanılan bir gösterge depolar. SQL Server'da saklı yordamlar ve T-SQL betikleri içinde kullanılır.

- **TABLE**
  - Depolama Alanı: Değişken
  - Açıklama: Geçici sonuç kümelerini depolamak için kullanılır. Genellikle saklı yordamlar içinde kullanılır.

***
## Veri Tabani Komutları
SQL (Structured Query Language) çeşitli komutlar içerir ve bu komutlar genellikle işlevlerine göre farklı kategorilere ayrılır. Bu kategoriler DDL (Data Definition Language), DML (Data Manipulation Language), DCL (Data Control Language) ve TCL (Transaction Control Language) olarak sınıflandırılır. 


#### DDL (Data Definition Language)
DDL komutları, veritabanı yapısını tanımlamak ve yönetmek için kullanılır.
- **CREATE**: Yeni bir veritabanı nesnesi oluşturur (tablo, indeks, görünüm, vb.)
  - Örnek: `CREATE TABLE Customers (CustomerID INT, Name NVARCHAR(50));`

- **ALTER**: Varolan bir veritabanı nesnesini değiştirir.
  - Örnek: `ALTER TABLE Customers ADD Email NVARCHAR(100);`

- **DROP**: Varolan bir veritabanı nesnesini siler.
  - Örnek: `DROP TABLE Customers;`

- **TRUNCATE**: Bir tablodaki tüm verileri siler, ancak tablo yapısını korur.
  - Örnek: `TRUNCATE TABLE Customers;`

- **RENAME**: Bir veritabanı nesnesinin adını değiştirir (bu komut SQL Server'da doğrudan desteklenmez, ancak diğer SQL veritabanlarında bulunabilir).
  - Örnek: `EXEC sp_rename 'OldTableName', 'NewTableName';`
***
#### DML (Data Manipulation Language)
DML komutları, veritabanındaki verileri işlemek için kullanılır.
- **SELECT**: Veritabanından veri seçer ve getirir.
  - Örnek: `SELECT * FROM Customers;`

- **INSERT**: Bir tabloya yeni satırlar ekler.
  - Örnek: `INSERT INTO Customers (CustomerID, Name) VALUES (1, 'John Doe');`

- **UPDATE**: Varolan veriyi günceller.
  - Örnek: `UPDATE Customers SET Name = 'Jane Doe' WHERE CustomerID = 1;`

- **DELETE**: Varolan veriyi siler.
  - Örnek: `DELETE FROM Customers WHERE CustomerID = 1;`

***
#### DCL (Data Control Language)
DCL komutları, veritabanındaki erişim haklarını ve izinleri yönetmek için kullanılır.
- **GRANT**: Kullanıcılara belirli izinler verir.
  - Örnek: `GRANT SELECT ON Customers TO User1;`

- **REVOKE**: Kullanıcılardan belirli izinleri geri alır.
  - Örnek: `REVOKE SELECT ON Customers FROM User1;`

***
#### TCL (Transaction Control Language)
TCL komutları, veritabanı işlemlerini yönetmek için kullanılır.
- **BEGIN TRANSACTION**: Yeni bir işlem başlatır.
  - Örnek: `BEGIN TRANSACTION;`

- **COMMIT**: İşlemi onaylar ve yapılan değişiklikleri kalıcı hale getirir.
  - Örnek: `COMMIT;`

- **ROLLBACK**: İşlemi geri alır ve yapılan değişiklikleri iptal eder.
  - Örnek: `ROLLBACK;`

- **SAVE TRANSACTION**: Bir işlem içinde bir savepoint oluşturur.
  - Örnek: `SAVE TRANSACTION SavepointName;`
***
#### Yardımcı Komutlar
SQL'de ayrıca yardımcı komutlar da bulunur. Bu komutlar belirli durumlar için kullanışlıdır.
- **USE**: Belirli bir veritabanını seçer.
  - Örnek: `USE MyDatabase;`

- **EXEC**: Bir saklı yordamı veya dinamik SQL deyimini çalıştırır.
  - Örnek: `EXEC sp_helpdb;`

- **SET**: SQL Server oturumu için değişkenlerin veya seçeneklerin değerini ayarlar.
  - Örnek: `SET NOCOUNT ON;`
    
Bu komutlar, SQL Server'da çalışırken temel işlevlerin büyük bir kısmını gerçekleştirmenizi sağlar. Her kategori belirli bir işlev grubuna hizmet eder ve doğru kullanımı, veritabanı yönetimi ve veri işlemleri açısından önemlidir.
***

## SELECT Komutu
`SELECT` komutu, SQL'de veritabanından veri çekmek için kullanılır. `SELECT` komutu, belirtilen kolonları seçip, belirli kriterlere göre filtreleyerek sonuç döndürür.

#### SELECT Komutunun Temel Sözdizimi
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
1. Tablodaki Tüm Verileri Seçmek
```sql
SELECT * FROM Customers;
```
2. Belirli Kolonları Seçmek
```sql
SELECT CustomerID, Name, Email FROM Customers;
```

3. Koşul ile Veri Seçmek
```sql
SELECT * FROM Customers WHERE Country = 'Turkey';
```
## INSERT Komutu
 `INSERT` komutu, SQL'de bir tabloya yeni satırlar eklemek için kullanılır. `INSERT` komutu, belirtilen kolonlara uygun değerleri ekleyerek tabloya yeni veri satırları ekler.
#### INSERT Komutunun Temel Sözdizimi

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```
1. Tabloya Yeni Bir Satır Eklemek

```sql
INSERT INTO Customers (CustomerID, Name, Email)
VALUES (1, 'Burak Dev', 'burak.dev@example.com');
```
2. Belirli Kolonlara Değer Eklemek
```sql
INSERT INTO Customers (CustomerID, Name)
VALUES (3, 'Damla Can');
```
3. Birden Fazla Satır Eklemek
```sql
INSERT INTO Customers (CustomerID, Name, Email)
VALUES 
(4, 'Deniz Kara', 'deniz.kara@example.com'),
(5, 'Merve Kılıç', 'merve.kilic@example.com');
```

***
## UPDATE Komutu
`UPDATE` komutu, SQL'de varolan kayıtları güncellemek için kullanılır. `UPDATE` komutu, belirtilen kolonlarda yeni değerler ayarlayarak mevcut veri satırlarını günceller.

#### UPDATE Komutunun Temel Sözdizimi
```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
1. Bir Kolonu Güncellemek
```sql
UPDATE Customers
SET Email = 'new.email@example.com'
WHERE CustomerID = 1;
```
2. Birden Fazla Kolonu Güncellemek
```sql
UPDATE Customers
SET Name = 'Jane Smith', Email = 'jane.smith@example.com'
WHERE CustomerID = 2;
``` 
3. Koşul İle Güncelleme Yapmak
```sql
UPDATE Customers
SET Country = 'Turkey'
WHERE Country = 'USA';
```  
4. Tüm Satırları Güncellemek
```sql
UPDATE Customers
SET Country = 'Unknown';
```     
***
## DELETE Komutu
`DELETE` komutu, SQL'de varolan kayıtları silmek için kullanılır. `DELETE` komutu, belirtilen koşula uygun olan veri satırlarını bir tablodan siler.

#### DELETE Komutunun Temel Sözdizimi
```sql
DELETE FROM table_name
WHERE condition;
```
1. Belirli Satırı Silmek
```sql
DELETE FROM Customers
WHERE CustomerID = 1;
```
2. Belirli Koşula Uygun Satırları Silmek
```sql
DELETE FROM Customers
WHERE Country = 'Turkey';
``` 
3. Tüm Satırları Silmek
```sql
DELETE FROM Customers;
```     
***
## TRUNCATE Komutu
`TRUNCATE` komutu, SQL'de bir tablodaki tüm verileri hızlı bir şekilde silmek için kullanılır. `TRUNCATE` komutu, DELETE komutundan farklı olarak veritabanı günlük dosyalarını doldurmadan ve veri satırlarını fiziksel olarak silmeden tabloyu temizler. Bu nedenle `TRUNCATE` komutu genellikle `DELETE` komutundan daha hızlıdır ve büyük veri kümeleri üzerinde performans avantajı sağlar.

#### TRUNCATE Komutunun Temel Sözdizimi

```sql
TRUNCATE TABLE table_name;

TRUNCATE TABLE Customers;
```  
#### Dikkat Edilmesi Gereken Noktalar
   - `TRUNCATE` işlemi, veritabanı günlük dosyalarını doldurmadan ve log kaydı oluşturmadan tabloyu hızlıca temizler. Bu durum, büyük veri kümeleri üzerinde performans açısından avantaj sağlar.

   - `TRUNCATE` komutu, tablodaki tüm verileri siler ancak tablonun yapısını (şemasını) korur. Bu nedenle, tablonun yeniden oluşturulmasını veya veri yapısının bozulmasını gerektirmeyen durumlarda tercih edilir.

   - `TRUNCATE` işlemi geri alınamaz ve silinen verileri kurtarmak mümkün değildir. Dolayısıyla, veri koruma ve geri alma ihtiyacı olan durumlarda `DELETE` komutu kullanılmalıdır.

Bu bilgiler doğrultusunda, `TRUNCATE` komutunun kullanımını ve önemli noktalarını anlamış olmalısınız.

***
### WHERE Sarti Kavrami
`WHERE` koşulu, SQL sorgularında belirli bir koşula uyan satırları seçmek için kullanılır. Bu koşul, `SELECT`, `UPDATE`, `DELETE` gibi komutlarla birlikte kullanılabilir.

1. Eşittir (=)

```sql
SELECT * FROM Customers WHERE Country = 'Turkey';
```
***  
2. Eşit Değil (<>, !=)

```sql
SELECT * FROM Customers WHERE Country <> 'Turkey';
SELECT * FROM Customers WHERE Country != 'Turkey';
```
***
3. Küçüktür (<)

```sql
SELECT * FROM Products WHERE Price < 100;
```
***
4. Büyüktür (>)

```sql
SELECT * FROM Products WHERE Price > 100;
```
***
5. Küçük Eşittir (<=)

```sql
SELECT * FROM Products WHERE Price <= 100;
```
***
6. Büyük Eşittir (>=)
```sql
SELECT * FROM Products WHERE Price >= 100;
```
***
7. AND Operatörü
   
`AND` operatörü, birden fazla koşulun hepsinin doğru olduğu satırları seçer. Yani, tüm koşullar sağlanmalıdır.
```sql
SELECT * FROM Customers
WHERE Country = 'Turkey' AND Age > 30;
```
***
8. OR Operatörü
   
`OR` operatörü, birden fazla koşuldan en az birinin doğru olduğu satırları seçer. Yani, koşullardan biri veya daha fazlası sağlanmalıdır.
- İki Koşuldan Birinin Sağlanması
```sql
SELECT * FROM Customers
WHERE Country = 'Turkey' OR Age > 30;
```
- Birden Fazla Koşuldan Birinin Sağlanması
```sql
SELECT * FROM Products
WHERE Category = 'Electronics' OR Price < 1000 OR Stock > 50;
```
***
9. BETWEEN
   
Belirli bir aralıktaki satırları seçer (alt ve üst sınırlar dahildir).
```sql
SELECT * FROM Products WHERE Price BETWEEN 50 AND 150;
```
***
10. LIKE
    
Belirli bir desene uyan satırları seçer (genellikle joker karakterlerle birlikte kullanılır: `%` herhangi bir karakter dizisini, `_` ise tek bir karakteri temsil eder).
```sql
-- Bu sorgu, Name kolonu 'A' harfiyle başlayan tüm müşterileri seçer.
SELECT * FROM Customers WHERE Name LIKE 'A%';

-- Bu sorgu, Name kolonu 'son' ile biten tüm müşterileri seçer.
SELECT * FROM Customers WHERE Name LIKE '%son';

-- Bu sorgu, Name kolonu içinde 'ann' karakter dizisini içeren tüm müşterileri seçer.
SELECT * FROM Customers WHERE Name LIKE '%ann%';

-- Bu sorgu, Name kolonu 'A' harfiyle başlayan ve 'n' harfiyle biten tüm müşterileri seçer.
SELECT * FROM Customers WHERE Name LIKE 'A%n';

-- Bu sorgu, Name kolonu ikinci karakteri 'a' olan tüm müşterileri seçer.
SELECT * FROM Customers WHERE Name LIKE '_a%';

-- Bu sorgu, Name kolonu tam olarak üç karakter uzunluğunda olan tüm müşterileri seçer.
SELECT * FROM Customers WHERE Name LIKE '___';

-- Bu sorgu, Name kolonu ikinci karakteri 'a' olan ve en az üç karakter uzunluğunda olan tüm müşterileri seçer.
SELECT * FROM Customers WHERE Name LIKE '_a_%';
```
***
11. EXISTS
    
 `EXISTS` operatörü, bir alt sorgunun en az bir satır döndürüp döndürmediğini kontrol eder. Genellikle, bir tablonun başka bir tabloyla ilişkili olup olmadığını kontrol etmek için kullanılır.

```sql
SELECT * FROM Customers
WHERE EXISTS (SELECT 1 FROM Orders WHERE Orders.CustomerID = Customers.CustomerID);
-- Bu sorguda, EXISTS operatörü Orders tablosunda en az bir siparişi olan müşterileri kontrol eder ve bu müşterileri Customers tablosundan seçer.
```
***
12. NOT
    
`NOT` operatörü, bir koşulun sağlanmadığını belirtmek için kullanılır ve şu operatörlerle birlikte kullanılabilir:
- `NOT IN`
- `NOT LIKE`
- `NOT BETWEEN`
- `NOT EXISTS`
- `NOT` ile birleştirilmiş diğer mantıksal operatörler (AND, OR)
Bu operatörlerle birlikte NOT, SQL sorgularında daha esnek ve güçlü koşullar tanımlamanıza olanak tanır.
***

## DISTINCT Komutu
`DISTINCT` operatörü, bir SQL sorgusunda yinelenen değerleri kaldırmak ve yalnızca benzersiz değerleri döndürmek için kullanılır.

|CustomerID|Name|Country|City|
|---|---|---|---|
|1|John Doe|USA|New York|
|2|Jane Smith|USA|Los Angeles|
|3|Anna Brown|USA|New York|
|4|Mike Davis|Canada|Toronto|
|5|Emily Clark|Canada|Vancouver|
|6|Liam Johnson|UK|London|
|7|Olivia|Wilson|USA|Chicago|


DISTINCT Kullanımı
```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

1. Tek Kolonla Kullanım
```sql
SELECT DISTINCT Country FROM Customers;
-- Bu sorgu, Customers tablosundaki benzersiz ülke adlarını döndürür.
```
#### Sonuç
|Country|
|---|
|USA|
|Canada|
|UK|

2. Birden Fazla Kolonla Kullanım
```sql
SELECT DISTINCT Country, City FROM Customers;
-- Bu sorgu, Customers tablosundaki benzersiz ülke ve şehir kombinasyonlarını döndürür. Yani aynı ülke ve şehir ikilisine sahip olan satırlar tekrarlanmaz.
```
#### Sonuç
|Country|City|
|---|---|
|USA|New York|
|USA|Los Angeles|
|USA|New York|
|Canada|Toronto|
|Canada|Vancouver|
|UK|London|
|USA|Chicago|

***
## ORDER BY Komutu
`ORDER BY` ifadesi, SQL'de sorgu sonuçlarını belirli bir sütuna veya sütunlara göre sıralamak için kullanılır. Sonuçları artan (varsayılan olarak) veya azalan sıraya göre düzenleyebiliriz.

ORDER BY Kullanımı
```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1 [ASC | DESC], column2 [ASC | DESC], ...;

-- column1, column2, ... : Sıralama yapılacak sütunlar.
-- ASC : Artan sıraya göre sıralama (varsayılan).
-- DESC : Azalan sıraya göre sıralama.
```

|CustomerID|Name|Country|City|
|---|---|---|---|
|1|John Doe|USA|New York|
|2|Jane Smith|USA|Los Angeles|
|3|Anna Brown|USA|New York|
|4|Mike Davis|Canada|Toronto|
|5|Emily Clark|Canada|Vancouver|
|6|Liam Johnson|UK|London|
|7|Olivia|Wilson|USA|Chicago|

1. Tek Kolonla Artan Sıralama

```sql
SELECT * FROM Customers
ORDER BY Name;
```
### Sonuç
|CustomerID|Name|Country|City|
|---|---|---|---|
|3|Anna Brown|USA|New York|
|5|Emily Clark|Canada|Vancouver|
|1|John Doe|USA|New York|
|6|Liam Johnson|UK|London|
|4|Mike Davis|Canada|Toronto|
|2|Jane Smith|USA|Los Angeles|
|7|Olivia Wilson|USA|Chicago|

2. Birden Fazla Kolonla Sıralama
 ```sql
SELECT * FROM Customers
ORDER BY Country, City;
```
### Sonuç
|CustomerID|Name|Country|City|
|---|---|---|---|
|4|Mike Davis|Canada|Toronto|
|5|Emily Clark|Canada|Vancouver|
|6|Liam Johnson|UK|London|
|7|Olivia Wilson|USA|Chicago|
|2|Jane Smith|USA|Los Angeles|
|1|John Doe|USA|New York|
|3|Anna Brown|USA|New York|

3. Birden Fazla Kolonla Karışık Sıralama
```sql
SELECT * FROM Customers
ORDER BY Country ASC, CustomerID DESC;
```
### Sonuç
|CustomerID|Name|Country|City|
|---|---|---|---|
|7|Olivia Wilson|USA|Chicago|
|3|Anna Brown|USA|New York|
|2|Jane Smith|USA|Los Angeles|
|1|John Doe|USA|New York|
|5|Emily Clark|Canada|Vancouver|
|4|Mike Davis|Canada|Toronto|
|6|Liam Johnson|UK|London|


***
## TOP Komutu
`TOP` komutu, SQL'de belirli bir sorgunun sonucunda döndürülecek ilk N kaydı belirlemek için kullanılır. Özellikle büyük veri kümelerinde performansı artırmak ve sorgu sonuçlarını sınırlamak için yaygın olarak kullanılır.
TOP Komutu Kullanımı
```sql
SELECT TOP (N) column1, column2, ...
FROM table_name
WHERE condition
ORDER BY column1, column2, ...;
```
- `N`: Döndürülecek ilk N kayıt sayısı.
- `column1, column2, ...`: Sorgu sonucunda döndürülecek sütunlar.
- `table_name`: Kayıtların alınacağı tablo adı.
- `condition`: Opsiyonel olarak, sorgunun filtrelemesini yapacak koşullar.
- `ORDER BY`: Opsiyonel olarak, sıralama yapılacak sütunlar.

```sql
SELECT TOP (3) * FROM Customers;
-- Bu sorgu, Customers tablosundan ilk 3 müşteriyi döndürecektir. Sıralama belirtilmediği sürece, SQL sunucusunun takdirine bağlı olarak rastgele üç müşteri döndürebilir.
```
***
## ALTER Komutu

`ALTER` komutu, SQL'de mevcut bir veritabanı nesnesini (örneğin, tablo veya veritabanı) değiştirmek veya değiştirmek için kullanılır. Genellikle tabloları değiştirmek veya tabloya yeni sütunlar eklemek gibi işlemler için kullanılır.


1. Tabloya Sütun Ekleme

```sql
ALTER TABLE table_name
ADD column_name datatype;
-- Bu komut, table_name tablosuna column_name adında yeni bir sütun ekler. datatype, eklenen sütunun veri türünü belirtir.
```

2. Sütun Değiştirme
```sql
ALTER TABLE table_name
ALTER COLUMN column_name datatype;
-- Bu komut, table_name tablosundaki column_name adlı sütunun veri türünü datatype olarak değiştirir.
```

3. Sütun Değiştirme
```sql
ALTER TABLE table_name
ADD CONSTRAINT constraint_name constraint_type (columns);
-- Bu komut, table_name tablosuna belirtilen kısıtlamayı ekler. constraint_name, kısıtlamanın adıdır ve constraint_type, kısıtlama türünü belirtir (örneğin, PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK gibi).
```

***
## DROP Komutu
`DROP` komutu SQL'de mevcut olan veritabanı nesnelerini (tablo, indeks, kısıtlama vb.) silmek için kullanılır.

1. Tabloyu Silme
```sql
DROP TABLE table_name;
-- Bu komut, table_name adlı tabloyu tamamen siler. Tablo ve içindeki veriler kalıcı olarak kaybolur.
```

2. İndeksi Silme
```sql
DROP INDEX index_name ON table_name;
-- Bu komut, table_name tablosundaki index_name adlı indeksi siler.
```
3. Kısıtlamayı Silme
```sql
ALTER TABLE table_name
DROP CONSTRAINT constraint_name;
-- Bu komut, table_name tablosundaki constraint_name adlı kısıtlamayı (örneğin, PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK) siler.
```
***
## Aggregate Functions
SQL'deki toplu (aggregate) fonksiyonlar, bir grup değer üzerinde hesaplamalar yapmak ve tek bir sonuç döndürmek için kullanılır. En yaygın kullanılan toplu fonksiyonlar şunlardır: `COUNT`, `SUM`, `AVG`, `MIN`, `MAX`.
### COUNT
`COUNT` fonksiyonu, belirli bir sütundaki değerlerin sayısını döndürür.
```sql
SELECT COUNT(*) FROM Customers;
```
### SUM
`SUM` fonksiyonu, belirli bir sütundaki sayıların toplamını döndürür.
```sql
SELECT SUM(Salary) FROM Employees;
```
### AVG
`AVG` fonksiyonu, belirli bir sütundaki sayıların ortalamasını döndürür.
```sql
SELECT AVG(Salary) FROM Employees;
```
### MIN MAX
`MIN` fonksiyonu, belirli bir sütundaki en küçük değeri döndürür.
`MAX` fonksiyonu, belirli bir sütundaki en büyük değeri döndürür.
```sql
SELECT MIN(Salary) FROM Employees;
SELECT MAX(Salary) FROM Employees;
```
## GROUP BY Kavrami
`GROUP BY` ifadesi SQL'de verileri belirli bir veya birden fazla sütuna göre gruplandırmak için kullanılır. Genellikle toplu (aggregate) fonksiyonlarla birlikte kullanılır. `GROUP BY`, gruplandırılmış veri kümeleri üzerinde toplu hesaplamalar yapmayı sağlar. `HAVING` ifadesi, SQL'de `GROUP BY` ile gruplandırılmış veriler üzerinde filtreleme yapmak için kullanılır. `WHERE` ifadesi gruplama öncesinde satırları filtrelerken, `HAVING` ifadesi gruplama sonrasında grupları filtreler.
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
WHERE condition
GROUP BY column1;

-- column1: Gruplandırılacak sütun(lar).
-- aggregate_function(column2): Gruplanmış veriler üzerinde hesaplama yapmak için kullanılacak toplu fonksiyon.
-- table_name: Kayıtların alınacağı tablo adı.
-- condition: Opsiyonel olarak, sorgunun filtrelemesini yapacak koşullar.
```

|EmployeeID|Name|Department|Salary|
|---|---|---|---|
|1|John Doe|HR|50000|
|2|Jane Smith|HR|60000|
|3|Sam Brown|IT|55000|
|4|Nancy Jones|IT|70000|
|5|Emily Davis|IT|65000|
|6|Mike Johnson|Sales|45000|
|7|Sarah Black|Sales|48000|

#### Departmana Göre Toplam Maaş
```sql
SELECT Department, SUM(Salary) AS TotalSalary
FROM Employees
GROUP BY Department;
```
|Department|TotalSalary|
|---|---|
|HR|110000|
|IT|190000|
|Sales|93000|


#### HAVING Kullanımı
```sql
SELECT column1, aggregate_function(column2)
FROM table_name
WHERE condition
GROUP BY column1
HAVING condition;

-- column1: Gruplandırılacak sütun(lar).
-- aggregate_function(column2): Gruplanmış veriler üzerinde hesaplama yapmak için kullanılacak toplu fonksiyon.
-- table_name: Kayıtların alınacağı tablo adı.
-- condition: HAVING ifadesi ile gruplar üzerinde filtreleme yapacak koşullar.
```
#### Departmana Göre Toplam Maaşı 100000'den Fazla Olan Departmanlar

```sql
SELECT Department, SUM(Salary) AS TotalSalary
FROM Employees
GROUP BY Department
HAVING SUM(Salary) > 100000;
```
|Department|TotalSalary|
|---|---|
|HR|110000|
|IT|190000|

***

## Iliskisel Veritabani Nedir
İlişkisel veritabanı, verilerin tablo formatında saklandığı ve bu tablolardaki verilerin birbirleriyle ilişkili olduğu bir veritabanı türüdür. İlişkisel veritabanları, verilerin düzenli ve mantıklı bir şekilde organize edilmesini sağlar. Veritabanı yönetim sistemi (DBMS) olarak adlandırılan yazılımlar aracılığıyla yönetilir ve Structured Query Language (SQL) kullanılarak veri ekleme, güncelleme, silme ve sorgulama işlemleri gerçekleştirilir.

İlişkisel Veritabanı Türleri
### (Bir-Bir) İlişki
Bir tablodaki bir satırın, başka bir tabloda sadece bir satırla ilişkili olduğu ilişki türüdür. Genellikle detayları ayırmak veya veritabanını normalleştirmek amacıyla kullanılır.

Örnek: Bir kişinin bir pasaportu vardır ve her pasaport sadece bir kişiye aittir.
```sql
CREATE TABLE Persons (
    PersonID int PRIMARY KEY,
    Name varchar(255),
    PassportID int UNIQUE
);

CREATE TABLE Passports (
    PassportID int PRIMARY KEY,
    PassportNumber varchar(255),
    PersonID int UNIQUE,
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```

### (Bir-Çok) İlişki
Bir tablodaki bir satırın, başka bir tabloda birden fazla satırla ilişkili olduğu ilişki türüdür. En yaygın ilişki türüdür.

Örnek: Bir müşteri birçok sipariş verebilir, fakat her sipariş sadece bir müşteriyle ilişkilidir.
```sql
CREATE TABLE Customers (
    CustomerID int PRIMARY KEY,
    Name varchar(255)
);

CREATE TABLE Orders (
    OrderID int PRIMARY KEY,
    OrderDate date,
    CustomerID int,
    FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);
```

### (Çok-Çok) İlişki
Bir tabloda birden fazla satırın, başka bir tabloda birden fazla satırla ilişkili olduğu ilişki türüdür. Bu tür ilişkiler genellikle ara tablolar kullanılarak modellenir.

Örnek: Bir öğrenci birçok derse kayıt olabilir ve her ders birçok öğrenci tarafından alınabilir.

```sql
CREATE TABLE Students (
    StudentID int PRIMARY KEY,
    Name varchar(255)
);

CREATE TABLE Courses (
    CourseID int PRIMARY KEY,
    CourseName varchar(255)
);

CREATE TABLE StudentCourses (
    StudentID int,
    CourseID int,
    PRIMARY KEY (StudentID, CourseID),
    FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
    FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);
```


Bu temel ilişki türleri, veritabanı tasarımının temel yapı taşlarıdır ve verilerin düzenli, tutarlı ve etkin bir şekilde saklanmasını sağlar.


### Geleneksel Tablo Birleştirme

```sql
SELECT TOP(2)
u.USERNAME_ , u.NAMESURNAME,u.EMAIL,u.BIRTHDATE,
c.COUNTRY, 
ct.CITY,
t.TOWN,
d.DISTRICT,
a.POSTALCODE, a.ADDRESSTEXT 
FROM USERS u,ADDRESS a,COUNTRIES c, CITIES ct, TOWNS t, DISTRICTS d
WHERE a.USERID=u.ID
AND   a.COUNTRYID=c.ID
AND   a.CITYID=ct.ID
AND   a.TOWNID=t.ID
AND   a.DISTRICTID=d.ID

-- Açıklama:
-- SELECT TOP(2): En fazla 2 satır döndürmek için kullanılan SQL Server özel ifadesidir. Bu sorgu en fazla 2 satır döndürecektir.

-- FROM: Sorguda kullanılacak tabloları belirtir.

-- USERS u: USERS tablosunu u kısaltmasıyla temsil eder.
-- ADDRESS a: ADDRESS tablosunu a kısaltmasıyla temsil eder.
-- COUNTRIES c: COUNTRIES tablosunu c kısaltmasıyla temsil eder.
-- CITIES ct: CITIES tablosunu ct kısaltmasıyla temsil eder.
-- TOWNS t: TOWNS tablosunu t kısaltmasıyla temsil eder.
-- DISTRICTS d: DISTRICTS tablosunu d kısaltmasıyla temsil eder.
-- WHERE: İlişkisel koşulları belirtir, yani hangi sütunların hangi tablolar arasında eşleştirileceğini belirtir.

-- a.USERID = u.ID: ADDRESS tablosundaki USERID sütunu ile USERS tablosundaki ID sütunu arasında eşleştirme yapar.
-- a.COUNTRYID = c.ID: ADDRESS tablosundaki COUNTRYID sütunu ile COUNTRIES tablosundaki ID sütunu arasında eşleştirme yapar.
-- a.CITYID = ct.ID: ADDRESS tablosundaki CITYID sütunu ile CITIES tablosundaki ID sütunu arasında eşleştirme yapar.
-- a.TOWNID = t.ID: ADDRESS tablosundaki TOWNID sütunu ile TOWNS tablosundaki ID sütunu arasında eşleştirme yapar.
-- a.DISTRICTID = d.ID: ADDRESS tablosundaki DISTRICTID sütunu ile DISTRICTS tablosundaki ID sütunu arasında eşleştirme yapar.
-- SELECT: Sonuç olarak döndürülecek sütunları belirtir.

-- u.USERNAME_, u.NAMESURNAME, u.EMAIL, u.BIRTHDATE: USERS tablosundan kullanıcı adı, isim-soyisim, e-posta ve doğum tarihi sütunları.
-- c.COUNTRY: COUNTRIES tablosundan ülke adı sütunu.
-- ct.CITY: CITIES tablosundan şehir adı sütunu.
-- t.TOWN: TOWNS tablosundan kasaba adı sütunu.
-- d.DISTRICT: DISTRICTS tablosundan ilçe adı sütunu.
-- a.POSTALCODE, a.ADDRESSTEXT: ADDRESS tablosundan posta kodu ve adres metni sütunları.
-- Bu sorgu, USERS tablosu ile ADDRESS, COUNTRIES, CITIES, TOWNS ve DISTRICTS tabloları arasındaki ilişkileri kullanarak belirli sorgu kriterlerine göre veri çeker.
```
***
## JOIN Turleri
SQL'de `JOIN`, ilişkisel veritabanlarında birden fazla tabloyu birleştirmek için kullanılan bir operatördür. İki veya daha fazla tablo arasında ilişki kurarak, bu tablolardan gelen verileri birleştirir ve istenilen sonuçları elde etmeyi sağlar.

### JOIN Türleri
`INNER JOIN`: İki tablo arasında eşleşen kayıtları döndürür. Yani, her iki tabloda da ortak olan verileri getirir. Ortak olmayan verileri getirmez.

Örnek:
```sql
SELECT *
FROM Orders o
INNER JOIN Customers c ON o.CustomerID = c.CustomerID;
Bu örnekte, Orders tablosu ile Customers tablosu CustomerID sütunları üzerinden INNER JOIN ile birleştirilmiştir. Bu işlem, her bir siparişin müşteri bilgilerini getirir.
```


`LEFT JOIN (LEFT OUTER JOIN)`: Sol tablodaki tüm kayıtları ve sağ tablodaki eşleşen kayıtları getirir. Eşleşme olmayan sağ tablo kayıtları için NULL değerleri döner.

Örnek:
```sql
SELECT *
FROM Customers c
LEFT JOIN Orders o ON c.CustomerID = o.CustomerID;
Bu örnekte, Customers tablosu sol tarafta (sol tablo) ve Orders tablosu sağ tarafta (sağ tablo) olarak birleştirilmiştir. Sol tablodaki tüm müşteri kayıtları getirilir ve her bir müşteri için varsa sipariş bilgileri getirilir.
```

`RIGHT JOIN (RIGHT OUTER JOIN)`: Sağ tablodaki tüm kayıtları ve sol tablodaki eşleşen kayıtları getirir. Eşleşme olmayan sol tablo kayıtları için NULL değerleri döner.

Örnek:
```sql
SELECT *
FROM Orders o
RIGHT JOIN Customers c ON o.CustomerID = c.CustomerID;
Bu örnekte, Orders tablosu sağ tarafta (sağ tablo) ve Customers tablosu sol tarafta (sol tablo) olarak birleştirilmiştir. Sağ tablodaki tüm sipariş kayıtları getirilir ve her bir sipariş için varsa müşteri bilgileri getirilir.
```

`FULL JOIN (FULL OUTER JOIN)`: İki tablodan da eşleşen ve eşleşmeyen tüm kayıtları getirir. Eşleşme olmayan sütunlar için NULL değerleri döner.

Örnek:

```sql
SELECT *
FROM Customers c
FULL JOIN Orders o ON c.CustomerID = o.CustomerID;
Bu örnekte, Customers tablosu ve Orders tablosu CustomerID sütunları üzerinden FULL JOIN ile birleştirilmiştir. Bu işlem, müşterilerin ve siparişlerin tamamını içeren bir sonuç kümesi oluşturur.
```
Bu JOIN türleri, SQL sorgularında verilerin nasıl birleştirileceğini ve hangi koşullara göre eşleştirileceğini belirler. İhtiyaca göre doğru JOIN türünü seçmek, istenilen veri analizini veya raporlamayı elde etmek için önemlidir.










