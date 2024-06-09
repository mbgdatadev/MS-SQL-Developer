- [SQL Nedir](#sql-nedir)
- [Veritabani Nedir](#veritabani-nedir)
- [SQLServer Kurulumu](#sqlserver-kurulumu)




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

