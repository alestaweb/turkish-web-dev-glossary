# Site Sahipleri İçin 20 Terim: Alan Adı, E-posta, Güvenlik ve Arama Motoru

Web sitesi yaptıran ya da yöneten biri, teknik ekiple konuşurken aynı kelimelerle sık sık karşılaşır: "MX kaydını değiştirdik", "DMARC yok", "sayfa noindex kalmış", "önce hazırlık ortamında deneyelim". Bu yazı, bu kelimelerin ne anlama geldiğini ve sizin açınızdan neden önemli olduğunu sade bir dille anlatır. Terimler kod bilgisi gerektirmeyecek şekilde açıklanmıştır.

## Alan adı ve DNS

### 1. Alan adı (Domain)

Sitenizin adresi: ornek.com.tr gibi. Alan adı satın alınmaz, belirli bir süre için kiralanır ve her yıl (ya da birkaç yıllık dönemlerle) yenilenir. Yenileme unutulursa site ve e-postalar birlikte durur. Alan adının kayıtlı sahibi şirketiniz ya da siz olmalısınız; işi yapan kişinin ya da firmanın adına kayıtlı alan adı, ayrılık durumunda en sık yaşanan sorundur.

### 2. Kayıt firması (Registrar)

Alan adını adınıza kaydeden ve yenilemesini yapan aracı firma. Alan adı paneline giriş bilgileri, barındırma (hosting) bilgilerinden ayrı tutulur. Bu panele erişiminiz yoksa alan adını başka bir firmaya taşımanız da zorlaşır.

### 3. Ad sunucusu (Nameserver, NS)

Alan adınızın "telefon rehberi"nin hangi sunucuda tutulduğunu gösterir. Ad sunucusu değiştirildiğinde sitenin ve e-postanın nereye gideceğine artık yeni sunucu karar verir. Site taşımalarında e-postanın kesilmesinin en yaygın nedeni, ad sunucusu değiştirilirken e-posta kayıtlarının yeni yere aktarılmamasıdır.

### 4. A kaydı

Alan adını bir sunucu adresine bağlayan kayıt. Ziyaretçi alan adınızı yazdığında tarayıcı bu kayda bakar ve siteyi o sunucudan ister. Siteniz taşındığında değişmesi gereken ilk kayıt budur.

### 5. MX kaydı

E-postalarınızın hangi sunucuya teslim edileceğini söyleyen kayıt. Site ile e-posta farklı yerlerde olabilir: site bir firmada, e-posta başka bir hizmette durabilir. MX kaydı yanlışsa site açılır ama gelen e-postalar kaybolur ya da geri döner.

### 6. TTL (Time To Live)

Bir DNS kaydının internetteki önbelleklerde ne kadar süre saklanacağını belirten değer. TTL bir saat ise yaptığınız değişiklik bazı kullanıcılara bir saate kadar eski hâliyle görünebilir. Planlı taşımalardan bir gün önce TTL'i kısaltmak, geçişi hızlandırır. "Değişiklik yaptık ama bende eski site açılıyor" durumunun çoğu bundandır.

### 7. Alt alan adı (Subdomain)

Ana alan adının önüne eklenen bölüm: magaza.ornek.com.tr, blog.ornek.com.tr gibi. Ayrı bir site gibi çalışabilir, ayrı bir sunucuya bağlanabilir. Kullanılmayan alt alan adları silinmezse, boşta kalan bir hizmete bağlı kalıp başkalarınca ele geçirilebilir; bu yüzden envanterde tutulmalıdır.

## E-posta güvenliği

### 8. SPF

Alan adınız adına hangi sunucuların e-posta gönderebileceğini ilan eden kayıt. Site formları, bülten aracı, muhasebe programı gibi sizin adınıza e-posta gönderen her hizmet bu listede olmalıdır. Listede olmayan bir hizmetin gönderdiği e-posta karşı tarafta istenmeyen kutusuna düşebilir. Alan adı başına tek SPF kaydı olur; iki ayrı SPF kaydı eklemek, hiç olmamasına benzer sonuç verir.

### 9. DKIM

Giden e-postaya eklenen dijital imza. Alıcı sunucu bu imzayı alan adınızdaki herkese açık anahtarla karşılaştırır ve e-postanın yolda değiştirilmediğini anlar. E-posta hizmetinizi değiştirdiğinizde yeni hizmetin DKIM kaydının da eklenmesi gerekir; bu adım sık unutulur.

### 10. DMARC

SPF ve DKIM kontrolünden geçemeyen bir e-postaya ne yapılacağını söyleyen kayıt: "bir şey yapma, sadece raporla", "istenmeyen kutusuna koy" ya da "reddet". Önce yalnız raporlama ile başlanır, raporlar okunup bütün meşru gönderenler SPF ve DKIM'e eklendikten sonra kural sıkılaştırılır. Büyük e-posta sağlayıcıları, çok sayıda e-posta gönderen alan adlarından SPF, DKIM ve DMARC kayıtlarını birlikte beklemektedir.

## Barındırma ve çalışma düzeni

### 11. Barındırma (Hosting)

Sitenizin dosyalarının ve veritabanının durduğu, sürekli açık sunucu hizmeti. Paylaşımlı barındırmada aynı sunucuyu başka siteler de kullanır; ucuzdur ama komşu bir sitenin yoğunluğu sizi de etkileyebilir. Barındırma sözleşmesinde yedeklemenin dahil olup olmadığı ve yedeğin size nasıl teslim edileceği yazılı olmalıdır.

### 12. SSL/TLS sertifikası

Tarayıcı ile siteniz arasındaki bağlantıyı şifreleyen ve adres çubuğunda kilit simgesinin görünmesini sağlayan belge. Sertifikaların bir bitiş tarihi vardır ve çoğu artık otomatik yenilenir. Otomatik yenileme sessizce durursa ziyaretçi "bağlantınız gizli değil" uyarısı görür ve çoğu kişi siteyi kapatır. Bitiş uyarılarının okunan bir e-posta adresine gitmesi gerekir.

### 13. Hazırlık ortamı (Staging)

Canlı sitenin bir kopyası; değişiklikler önce burada denenir, sorun yoksa canlıya alınır. Hazırlık ortamı arama motorlarına kapatılmalı, mümkünse parolayla korunmalıdır. Açık unutulan hazırlık ortamı, sitenizin kopyası olarak arama sonuçlarına girebilir.

### 14. Sürüm denetimi (Version Control)

Kodda yapılan her değişikliğin kim tarafından, ne zaman ve neden yapıldığını kaydeden sistem. Bir güncelleme sorun çıkarırsa önceki hâle dönmeyi kolaylaştırır. Site yaptıran açısından önemli soru şudur: kodun güncel hâli bir sürüm denetimi deposunda mı duruyor ve iş biterse bu depo size teslim edilecek mi?

## Arama motorları

### 15. robots.txt

Sitenin kökünde duran ve arama motoru tarayıcılarına hangi bölümlere girmemeleri gerektiğini söyleyen metin dosyası. Bir sayfayı arama sonuçlarından çıkarmak için doğru araç değildir: taranması engellenen bir sayfa, başka sitelerden bağlantı alıyorsa adresi yine sonuçlarda görünebilir. Yanlışlıkla bütün siteyi kapatan tek bir satır, trafiğin günler içinde düşmesine yol açabilir.

### 16. noindex

Bir sayfanın arama sonuçlarında gösterilmemesini isteyen işaret. Teşekkür sayfası, sepet, iç arama sonuçları gibi sayfalar için uygundur. Dikkat: tarayıcı noindex işaretini görebilmek için sayfayı tarayabilmelidir; aynı sayfayı hem robots.txt ile engellemek hem noindex vermek işareti görünmez kılar. Yeni sitelerde yayına alırken hazırlık döneminden kalan noindex işaretinin kaldırılması unutulabilir.

### 17. Yumuşak 404 (Soft 404)

Aslında var olmayan ya da boş bir sayfanın, "bulunamadı" (404) yerine "başarılı" (200) yanıtıyla gösterilmesi. Örneğin stokta kalmayan ürün sayfasında yalnız "ürün yok" yazması ya da silinen her adresin ana sayfaya yönlendirilmesi. Arama motoru bu sayfaları düşük değerli sayar ve arama konsolunda ayrı bir uyarı olarak gösterir. Kalıcı olarak kaldırılan içerik 404 ya da 410, yeni yerine taşınan içerik kalıcı yönlendirme (301) ile karşılanmalıdır.

## Hesap ve erişim güvenliği

### 18. İki adımlı doğrulama (2FA)

Parolaya ek olarak telefondaki uygulamadan gelen kod ya da güvenlik anahtarı istenmesi. Parola çalınsa bile tek başına yetmez. Alan adı paneli, barındırma paneli, site yönetim paneli, e-posta ve ödeme hesapları ilk açılması gereken yerlerdir. Yedek kodlar basılıp güvenli bir yerde saklanmalıdır; telefon kaybolduğunda hesaba dönmenin yolu bunlardır.

### 19. Oltalama (Phishing)

Bankanızdan, kargo firmasından, alan adı firmanızdan ya da bir kamu kurumundan geliyormuş gibi görünen sahte e-posta veya mesajla parola, kart bilgisi ya da ödeme alınmaya çalışılması. "Alan adınızın süresi doluyor, hemen ödeyin" türü mesajlar site sahiplerine sık gelir. Bağlantıya tıklamak yerine kayıt firmanızın panelini kendiniz açıp kontrol etmek en güvenli yoldur.

### 20. DDoS (Dağıtık Hizmet Engelleme)

Çok sayıda cihazdan aynı anda gönderilen isteklerle sitenin yavaşlatılması ya da tamamen erişilemez hâle getirilmesi. Verileri çalmaz ama satış ve haber yayını gibi işleri durdurur. Barındırma firmanızın bu tür saldırılara karşı nasıl bir koruma sunduğunu, saldırı sırasında kime ve nasıl ulaşacağınızı önceden öğrenmek gerekir.

## Kontrol listesi

- [ ] Alan adı şirketin ya da benim adıma kayıtlı, kayıt firmasının paneline kendim girebiliyorum.
- [ ] Alan adı, barındırma ve sertifika bitiş tarihleri bir takvimde yazılı.
- [ ] Ad sunucusu ve MX kayıtlarının nereyi gösterdiğini biliyorum.
- [ ] Taşıma öncesinde TTL değerinin kısaltılması planlandı.
- [ ] Kullanılmayan alt alan adları silindi.
- [ ] Adıma e-posta gönderen bütün hizmetler SPF kaydında, DKIM imzaları açık.
- [ ] DMARC kaydı var ve raporları okunuyor.
- [ ] Barındırma sözleşmesinde yedekleme ve yedek teslimi yazılı.
- [ ] Hazırlık ortamı arama motorlarına kapalı ve parolalı.
- [ ] Kodun güncel hâli bir sürüm denetimi deposunda ve teslim koşulu yazılı.
- [ ] robots.txt yanlışlıkla bütün siteyi kapatmıyor.
- [ ] Yayındaki sayfalarda hazırlık döneminden kalan noindex yok.
- [ ] Silinen sayfalar 404/410, taşınanlar 301 ile karşılanıyor.
- [ ] Bütün yönetim hesaplarında iki adımlı doğrulama açık, yedek kodlar saklanıyor.
- [ ] Ödeme ve yenileme isteyen mesajlarda bağlantıya tıklamadan panel kendim açılarak kontrol ediliyor.

## Resmî kaynaklar

- SPF — RFC 7208: https://datatracker.ietf.org/doc/html/rfc7208
- DKIM — RFC 6376: https://datatracker.ietf.org/doc/html/rfc6376
- DMARC — RFC 7489: https://datatracker.ietf.org/doc/html/rfc7489
- Google Search Central — robots.txt'e giriş: https://developers.google.com/search/docs/crawling-indexing/robots/intro
- Google Search Central — noindex ile dizine eklemeyi engelleme: https://developers.google.com/search/docs/crawling-indexing/block-indexing
- Google Search Central — HTTP durum kodları ve yumuşak 404: https://developers.google.com/search/docs/crawling-indexing/http-network-errors
- Google — E-posta gönderen yönergeleri: https://support.google.com/a/answer/81126
- USOM (Ulusal Siber Olaylara Müdahale Merkezi): https://www.usom.gov.tr

---

Bu yazı genel bilgilendirme amaçlıdır. Hazırlayan: Alesta WEB — İzmir
