- [SQL Nedir](#sql-nedir)
- [Veritabani Nedir](#veritabani-nedir)
- [SQL Server Kurulumu](#sqlserver-kurulumu)
- [SQL Connetion](#sql-connection)
- [Veri Tabani Olusturma](#veri-tabani-olusturma)
- [Veri Tipleri ve Normalizasyon](#veri-tipleri-ve-normalizasyon)
- 




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

















  
