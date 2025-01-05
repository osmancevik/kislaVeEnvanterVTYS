Osman Çevik - 205260044
Muhammed Ali Işık - 205260010
Cihan Kara - 205260040

# Kışla ve Envanter Veritabanı

Veritabanı, bir askeri kışla ile ilişkili çeşitli operasyonel verileri tutmak için tasarlanmış görünüyor. Her bir tablo, farklı bir işlevi ve süreci temsil ediyor, ve tüm bu tablolar, kışla yönetimi ve personel işlemleri ile ilgili bilgileri düzenler. Aşağıda, veritabanının her bir tablosunun işlevi ve ilişkileri hakkında detaylı açıklamalar bulabilirsiniz:

# 1. Envanter (envanterID, malzemeAdi, malzemeTuru, miktar, kislaID)
   
- Bu tablo, kışlada bulunan malzemelerin yönetimi için kullanılır. Her malzeme için benzersiz bir ID (envanterID) belirlenir.
- Malzeme adı, türü ve miktarı hakkında bilgi içerir.
- kislaID ile hangi kışlaya ait olduğu belirtilir.
- İlişki: Kışla tablosuyla ilişkilidir.

# 2. Personel (personelID, adSoyad, rutbe, gorev, kislaID)

- Kışlada çalışan personelin bilgilerini içerir. Her personelin bir ID'si (personelID) vardır.
- Personelin adı, soyadı, rütbesi, görev tanımı ve hangi kışlada çalıştığı belirtilir.
- İlişki: Kışla tablosuyla ilişkilidir.

# 3. Egitim (egitimID, egitimAdi, baslangicTarihi, bitisTarihi, kislaID, persone)
   
- Kışlaya bağlı verilen eğitimlerin kaydını tutar. Eğitimlerin adı, başlangıç ve bitiş tarihleri yer alır.
- Ayrıca eğitimleri kimlerin aldığına dair bilgiler de yer alır.
- İlişki: Kışla ve Personel tablolarıyla ilişkilidir.
  
# 4. Verilen (egitimID, personelID, eğitmenAdı, egitmenRutbe)
   
- Kişilere verilen eğitimleri detaylandırır. Eğitim ID'si ve hangi personelin eğitim aldığını gösterir.
- Eğitim veren eğitmenin adı ve rütbesi de burada belirtilir.
- İlişki: Eğitim ve Personel tablolarıyla ilişkilidir.
  
# 5. Lojistik (lojistikID, tedarikciID, lojistikTuru, miktar, teslimTarihi, kislaID)
   
- Kışlada yapılan lojistik işlemlerinin kaydını tutar. Lojistik türü (örneğin, malzeme sevkiyatı) ve miktar belirtilir.
- Lojistiği sağlayan tedarikçinin ID'si ve teslim tarihi de yer alır.
- İlişki: Tedarikçi ve Kışla tablolarıyla ilişkilidir.
  
# 6. Saglik (saglikID, personelID, saglikDurumu, muayeneTarihi, tedaviDurumu, kislaID)
   
- Personelin sağlık durumu hakkında bilgi verir. Personelin sağlık durumu, muayene tarihi ve tedavi durumu kayıt altına alınır.
- İlişki: Personel ve Kışla tablolarıyla ilişkilidir.
  
# 7. Disiplin (disiplinID, personelID, disiplinDurumu, cezaTarihi, cezaAciklamasi)
   
- Personelin disiplin işlemleri ile ilgilidir. Hangi personelin disiplin cezası aldığı ve cezanın açıklaması gibi bilgiler içerir.
- İlişki: Personel tablosuyla ilişkilidir.

# 8. Izin (izinID, personelID, izinBaslangic, izinBitis, izinSebebi)

- Personelin izin durumlarını yönetir. İzin başlangıç ve bitiş tarihleri ile izin sebebi belirtilir.
- İlişki: Personel tablosuyla ilişkilidir.

# 9. Tedarikci (tedarikciID, tedarikciAdi, tedarikciTuru, telefonNo, email, adres)

- Kışlaya malzeme sağlayan tedarikçilerin bilgilerini içerir. Her tedarikçi için benzersiz bir ID vardır.
- Tedarikçi adı, türü, iletişim bilgileri ve adresi yer alır.
- İlişki: Lojistik tablosuyla ilişkilidir.

# 10. Tatbikat (tatbikatID, tatbikatAdi, baslangicTarihi, bitisTarihi, personelID)
    
- Personelin katıldığı tatbikatların bilgilerini içerir. Tatbikatın adı, başlangıç ve bitiş tarihleri ve hangi personelin katıldığı bilgisi yer alır.
- İlişki: Personel tablosuyla ilişkilidir.

# 11. Katıldığı (personelID, tatbikatID, tatbikatTürü)
    
- Personelin katıldığı tatbikatların türünü belirtir. Bu tablo, personelin hangi tatbikata katıldığını ve tatbikat türünü gösterir.
- İlişki: Tatbikat ve Personel tablolarıyla ilişkilidir.

# 12. Kışla (kislaID, kislaKapasite, kislaAdi, kislaSehri, kislaKomutan, kislaBölge)

- Kışlaya ait genel bilgileri içerir. Kışlanın adı, kapasitesi, komutanı ve bölgesi gibi bilgiler yer alır.
- İlişki: Diğer tüm tablolarla ilişkilidir, çünkü çoğu işlem belirli bir kışla ile bağlantılıdır.

# Veritabanı İlişkileri:

- Birçok tablo, Kışla tablosuyla ilişkilidir: Bu, tüm işlemlerin (envanter, personel, eğitim, lojistik, sağlık vb.) belirli bir kışla ile ilişkilendirilmesi gerektiğini gösterir.
- Personel, çeşitli tablolarla ilişkilidir: Personel, eğitimler, tatbikatlar, izinler, disiplinler gibi birçok işlemde yer alır.
- Tedarikçi ve lojistik ilişkisi: Lojistik işlemleri tedarikçilerle ilişkilidir, yani malzeme ve hizmet sağlayıcıları bu iki tablo arasında bağ kurar.
- Veritabanı, kışla yönetimi ve personel yönetimi için oldukça kapsamlı ve düzenli bir yapı sunmaktadır. Personel ve kışla içindeki süreçler hakkında ayrıntılı bilgi edinmek ve yönetim yapmak için etkili bir şekilde kullanılabilir.
