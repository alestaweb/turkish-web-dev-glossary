# Türkçe Web Geliştirici Sözlüğü

Türkçe yazılım, web geliştirme ve dijital terimler için açıklamalı sözlük. Her terim için Türkçe karşılık, İngilizce orijinal ve sade anlatımlı tanım yer alır.

Bu sözlük; üniversite öğrencileri, sektöre yeni giren geliştiriciler, müşteriyle yazılım konuşan satış/proje yöneticileri, içerik üreten teknik yazarlar ve Türkçe doküman okuyan yabancı geliştiriciler için hazırlandı.

## İçindekiler

- [PHP & Backend](#php--backend)
- [JavaScript & Frontend](#javascript--frontend)
- [Veritabanı](#veritabanı)
- [HTTP & Ağ](#http--ağ)
- [SEO & Arama Motorları](#seo--arama-motorları)
- [Yapay Zeka](#yapay-zeka)
- [E-Ticaret](#e-ticaret)
- [Haber Yazılımı](#haber-yazılımı)
- [Güvenlik](#güvenlik)
- [DevOps & Sunucu](#devops--sunucu)
- [Yasal & Uyumluluk](#yasal--uyumluluk)
- [İçerik & Tasarım](#i̇çerik--tasarım)
- [Katkı](#katkı)

---

## PHP & Backend

### Sınıf (Class)

Nesne yönelimli programlamada bir veri tipinin şablonu. PHP'de `class Urun { ... }` şeklinde tanımlanır. Bir sınıftan birçok nesne (instance) üretilir; her nesne kendi veri kümesini taşır.

### Arayüz (Interface)

Sınıfların uygulamak zorunda olduğu metot imzalarını tanımlayan sözleşme. Gövdesi yok, sadece imza. Aynı arayüzü uygulayan sınıflar birbirinin yerine kullanılabilir. Bağımlılık tersine çevirme prensibinin temelidir.

### Kalıtım (Inheritance)

Bir sınıfın başka bir sınıfın tüm özelliklerini ve metotlarını miras alması. PHP'de `class Roman extends Kitap` şeklinde yazılır. Aşırı kalıtım kötü tasarımdır; çoğu durumda kompozisyon tercih edilir.

### Bileşim / Kompozisyon (Composition)

Bir sınıfın başka bir sınıfı içerik olarak tutması (kalıtım yerine). "Bir araba bir motor *içerir*" mantığı. Modern tasarım örüntülerinin temel yapı taşı; kalıtımdan daha esnek ve test edilebilir kod üretir.

### Bağımlılık Enjeksiyonu (Dependency Injection)

Bir sınıfın ihtiyaç duyduğu nesneleri kendisi oluşturmak yerine dışarıdan alması. Test yazılabilirliği ve modülerliği artırır. PHP'de constructor injection en yaygın yöntemdir.

### Anonim Fonksiyon (Closure)

İsimsiz, bir değişkene atanabilen, başka fonksiyona parametre olarak geçilebilen fonksiyon. PHP 8'de `fn ($x) => $x * 2` ok söz dizimiyle tek satırlık yazılır. JavaScript'in arrow function eşdeğeri.

### Tip İpucu (Type Hint)

Fonksiyon parametre ve dönüş değerlerinin tipini önceden bildirmek. `function topla(int $a, int $b): int` örneğinde girdi ve çıktı tipleri sabittir. PHP 8.2 ile birlikte tip sistemi neredeyse statik dil seviyesine ulaştı.

### Geriye Dönük Uyumluluk (Backward Compatibility / BC Break)

Yeni sürümün eski kodu çalıştırabilmesi. "BC kırıldı" demek yeni sürüme geçince eski kodun çalışmaması anlamına gelir. PHP 7 → 8 geçişi büyük BC değişimleri içerdi.

### Yapısal Tip (Trait)

PHP'de çoklu kalıtım eksikliğini gideren mekanizma. Birden fazla sınıfa aynı kod parçasını dağıtmak için kullanılır. Aşırı kullanılırsa "ne nereden geliyor" karmaşası doğurur.

### Numaralandırma (Enum)

Sabit değerler kümesi. PHP 8.1 ile birlikte first-class destek geldi. `enum SiparisDurumu: string { case Beklemede = 'pending'; case Onaylandi = 'approved'; }` şeklinde yazılır. Hatalı string karşılaştırmaları önler.

### Yansıma (Reflection)

Çalışma zamanında bir sınıfın yapısını (metot, özellik, attribute) sorgulamak. Framework geliştirmede yaygın; iş kodunda nadiren gerekir, kullanılırsa performans bedeli vardır.

### Salt Okunur (Readonly)

PHP 8.1+ özelliği. Bir özelliğin tek seferlik atandıktan sonra değiştirilememesi. Immutable nesne tasarımının temel yapı taşı. PHP 8.2 ile sınıf bazlı `readonly class` geldi.

### Adlandırılmış Argüman (Named Argument)

Fonksiyon çağırırken parametreyi pozisyonu yerine ismiyle vermek. `mb_substr(string: $s, length: 10)` örneğinde sıra önemsizdir. Çok parametreli fonksiyonların okunabilirliğini artırır.

---

## JavaScript & Frontend

### Yapım Aşaması (Build Process)

Geliştirici kodunun (TypeScript, JSX, Sass) tarayıcının anlayacağı sade JavaScript ve CSS'e dönüştürülmesi süreci. Vite, esbuild, webpack gibi araçlar üstlenir. Üretim ortamına gönderilen kod genelde minify ve uglify edilmiş haldedir.

### Paket Boyutu (Bundle Size)

Tarayıcıya gönderilen JavaScript dosyalarının toplam ağırlığı. 100KB altı modern siteler için tatmin edici, 500KB üstü mobilde ciddi performans kaybıdır. Lighthouse skoru paket boyutuna duyarlıdır.

### Ağaç Sallama (Tree Shaking)

Build aşamasında kullanılmayan import edilmiş kodun otomatik silinmesi. Modern bundler'ların standart özelliği. Bir kütüphaneden tek bir fonksiyon kullanıyorsanız, geri kalanını taşımanıza gerek kalmaz.

### Hidrasyon (Hydration)

Sunucuda HTML olarak gönderilmiş içeriği tarayıcıda etkileşimli hale getirme süreci. React/Vue/Next gibi framework'lerde server-side rendering sonrası gerekli. Yavaş hidrasyon ilk etkileşim süresini (TTI) uzatır.

### Ada Mimari (Islands Architecture)

Sayfanın çoğu statik HTML, sadece etkileşimli adacıkları JavaScript ile çalıştıran model. Astro framework'ünün öncülüğüyle yaygınlaştı. Tüm sayfayı SPA yapmaktan daha hızlı, daha az JavaScript.

### Sanal DOM (Virtual DOM)

Gerçek DOM'un bellekte tutulan hafif bir kopyası. Değişiklikleri önce sanal kopyada yapıp, gerçek DOM'a yalnızca farkı uygulamak performans avantajı sağlar. React'in temel tasarımı.

### İmza Olayı (Event Listener)

Belirli bir kullanıcı eylemine (tıklama, klavye, scroll) tepki vermek için DOM elemanına bağlanan fonksiyon. Eksik kaldırılması bellek sızıntısına yol açar; SPA'larda öncelikli optimizasyon hedeflerinden biri.

### Akış Programlama (Reactive Programming)

Verinin akışını ve değişimlerini bir veri kaynağı olarak modelleme. RxJS, Solid.js, Vue 3 reactivity gibi sistemler bu paradigmaya dayanır. UI tutarlılığı manuel state yönetiminden daha güvenli.

### Geçişli (Transient) State

Sadece bir bileşenin görsel ihtiyacı için tutulan, kalıcı veriye ihtiyaç duymayan durum. "Modal açık mı?", "Hover edildi mi?" gibi. Global state yönetiminde tutulmaz, bileşen içinde kalır.

### Servis İşçisi (Service Worker)

Tarayıcı sayfası dışında, arka planda çalışan JavaScript. Önbellek yönetimi, çevrimdışı erişim, anlık bildirim için kullanılır. PWA (Progressive Web App) altyapısının temel bileşeni.

---

## Veritabanı

### Birincil Anahtar (Primary Key)

Bir tablodaki her satırı eşsiz şekilde tanımlayan sütun. Genelde `id` adıyla otomatik artan tamsayı olur. Tablonun "kimlik kartı"dır; null olamaz, tekrar edemez.

### Yabancı Anahtar (Foreign Key)

Bir tablodaki sütunun, başka tablodaki birincil anahtara referans vermesi. İlişkisel veritabanlarının temel yapı taşı. `siparis.kullanici_id → kullanici.id` örneği yaygın kullanımıdır.

### İndeks (Index)

Sorgu hızını artırmak için sütun(lar) üzerinde tutulan ek veri yapısı. Telefon rehberindeki alfabetik dizin gibi düşünülebilir. Yazma işlemlerini biraz yavaşlatır, okuma işlemlerini katbekat hızlandırır.

### İşlem (Transaction)

Birden fazla SQL ifadesinin tek bir atomik birim olarak çalışması. Ya hepsi başarılı, ya hepsi geri alınır. Ödeme + stok güncelleme gibi kritik akışlarda zorunludur. ACID prensiplerinin başlangıç noktası.

### Denormalizasyon (Denormalization)

İlişkisel veritabanı kurallarını bilerek esnetip aynı veriyi birden fazla tabloya kopyalama. Okuma performansı için yazma karmaşıklığını feda etmek. Büyük ölçekli analitik sistemlerde yaygın.

### Saklı Yordam (Stored Procedure)

Veritabanı sunucusunda kayıtlı, uygulamadan çağrılabilen SQL kod bloğu. Karmaşık iş mantığını DB tarafına taşır. Modern web'de pek tercih edilmez (test edilemez, sürüm yönetimi zor).

### Tetikleyici (Trigger)

Bir tabloda INSERT/UPDATE/DELETE olduğunda otomatik çalışan SQL kod parçası. Audit log oluşturmak için kullanılır. Gizli yan etki ürettiği için aşırı kullanımı debugging'i zorlaştırır.

### Sorgu Planı (Query Plan / EXPLAIN)

Veritabanının bir sorguyu nasıl çalıştırdığını gösteren çıktı. Yavaş sorgu optimizasyonunun ilk adımı `EXPLAIN` ile plan analizidir. Hangi indeksin kullanıldığı, kaç satır okunduğu burada görülür.

### N+1 Problemi

ORM kullanırken döngü içinde her elemana ilişkili veri çekme. 100 ürün varsa 1 ana sorgu + 100 alt sorgu = 101 sorgu. Eager loading veya JOIN ile tek sorguya indirilir. Yavaş web sayfalarının en yaygın sebebi.

### Bağlantı Havuzu (Connection Pool)

Veritabanına yeni bağlantı açmak yerine açık bağlantıları yeniden kullanan yapı. Bağlantı açma maliyetli olduğu için yüksek trafikte ciddi performans farkı yaratır. PostgreSQL'de PgBouncer, MySQL'de ProxySQL yaygın çözümlerdir.

### Çoğaltma (Replication)

Veritabanının birebir kopyasının başka sunucuda gerçek zamanlı tutulması. Yüksek erişilebilirlik ve okuma trafiğini dağıtma amacıyla kullanılır. Ana → Yedek (master → replica) yapısı standarttır.

### Parçalama (Sharding)

Veritabanını mantıksal olarak parçalara bölüp her parçayı ayrı sunucuda tutmak. Tek bir DB'nin kaldıramayacağı kadar büyük veri için zorunlu. Kullanıcı ID veya coğrafi bölgeye göre parçalama yaygındır.

---

## HTTP & Ağ

### Durum Kodu (Status Code)

HTTP yanıtının üst satırındaki üç haneli sayı. 2xx başarı, 3xx yönlendirme, 4xx istemci hatası, 5xx sunucu hatası. 200, 301, 404, 500 en sık karşılaşılan kodlardır.

### Yönlendirme (Redirect)

Bir URL'den başka URL'e otomatik gönderim. 301 kalıcı, 302 geçici. SEO'da 301 sıralama gücünü aktarır, 302 aktarmaz. Yanlış yönlendirme kullanımı arama motorlarında ciddi kayıp doğurur.

### Önbellek (Cache)

Pahalı işlem sonucunu hızlı erişilebilir bir yerde tutmak. Tarayıcı önbelleği, CDN önbelleği, sunucu uygulama önbelleği, veritabanı sorgu önbelleği — her katmanda farklı tür. Performans optimizasyonunun temel aracı.

### CDN (Content Delivery Network)

İçeriği kullanıcıya en yakın sunucudan dağıtan ağ. Resim, CSS, JS gibi statik dosyalar için ortalama latency'i 10-100ms düşürür. Cloudflare, Akamai, BunnyCDN yaygın sağlayıcılardır.

### HTTPS (Şifreli HTTP)

SSL/TLS ile şifrelenmiş HTTP. 2024'ten sonra modern tarayıcılar HTTPS'siz siteleri uyarı veriyor. Let's Encrypt sayesinde ücretsiz sertifika edinmek standart hale geldi.

### Çapraz Köken (Cross-Origin / CORS)

Farklı alan adındaki bir kaynağa tarayıcıdan erişim. Güvenlik nedeniyle varsayılan olarak engellenir; sunucu `Access-Control-Allow-Origin` başlığıyla izin verir. CORS hataları frontend geliştiricilerin sık karşılaştığı sorundur.

### Yük Dengeleyici (Load Balancer)

Gelen trafiği birden fazla sunucuya dağıtan ara katman. NGINX, HAProxy, Cloudflare gibi araçlar üstlenir. Yüksek erişilebilirlik ve yatay ölçekleme için zorunlu bileşendir.

### Ters Vekil Sunucu (Reverse Proxy)

İstemci ile uygulama sunucusu arasında duran, gelen istekleri yönlendiren sunucu. SSL termination, cache, IP filtreleme, rate limiting gibi işleri tek noktada yapar.

### WebSocket

Tarayıcı ile sunucu arasında çift yönlü, sürekli açık bağlantı. Anlık mesajlaşma, canlı bildirim, oyun gibi uygulamaların temel altyapısı. HTTP'ye göre düşük gecikmeli ama daha karmaşık.

### Server-Sent Events (SSE)

Sunucudan tarayıcıya tek yönlü canlı veri akışı. WebSocket'ten daha basit. Borsa fiyatları, canlı maç skoru, ChatGPT tarzı akışlı yanıtlar için yeterli.

### Sıkıştırma (Compression)

Veriyi göndermeden önce boyutunu küçültmek. Gzip eski standart, Brotli daha verimli modern alternatif. CDN ve sunucu seviyesinde otomatik yapılır, geliştirici eylemi gerektirmez.

---

## SEO & Arama Motorları

### Tarama (Crawling)

Arama motoru botunun web sayfalarını otomatik gezmesi. Google için Googlebot, Bing için Bingbot başlıca aktörlerdir. `robots.txt` ile hangi sayfalara erişebilecekleri belirlenir.

### Dizinleme (Indexing)

Taranmış sayfanın arama motorunun veritabanına eklenmesi. Tarama başarılı olsa bile dizinleme garanti değildir; içerik kalitesi ve teknik şartlar belirleyicidir.

### Birincil URL (Canonical URL)

Aynı içeriğin birden fazla URL'den erişilebildiği durumda hangisinin "asıl" sayılacağını belirten etiket. Duplicate content sorununun standart çözümü. `<link rel="canonical" href="...">` ile işaretlenir.

### Hreflang

Aynı sayfanın farklı dil/bölge sürümleri arasındaki ilişkiyi belirten etiket. Türkiye için Türkçe, Almanya için Almanca sürüm arasında hreflang gerekir. Yanlış kullanımı duplicate content sayılır.

### Yapısal Veri (Schema.org / Structured Data)

Sayfa içeriğini makinelerin anlayacağı JSON formatında işaretlemek. NewsArticle, Product, FAQPage, BreadcrumbList yaygın şemalardır. Doğru schema rich snippet'lere yol açar, tıklama oranını artırır.

### Zengin Sonuç (Rich Snippet)

Arama sonuçlarında normal başlık ve açıklamaya ek olarak yıldız puanı, fiyat, soru-cevap, görsel gibi öğelerin görünmesi. Schema markup'ın doğru çalışmasının kanıtıdır.

### Kaynak Bağlantısı (Backlink)

Başka bir siteden sizin sitenize verilen link. Arama motorları için "güven oyu" anlamına gelir. Kalite niceliğe galip gelir; tek bir otoriter site backlink'i yüzlerce spam linkten değerlidir.

### Anahtar Kelime (Keyword)

Kullanıcının arama motoruna yazdığı sorgu. SEO çalışmasının temel birimi. Tek kelimeler rekabetli, uzun kuyruk (long-tail) sorgular daha az rekabetli ve dönüşüm oranı daha yüksek.

### Site İçi Bağlantılar (Internal Linking)

Aynı domain içindeki sayfalar arası bağlantılar. Sayfaların "otoritesini" siteye yayar, kullanıcı yolculuğunu yönlendirir. Hub-spoke yapısı yaygın bir stratejidir.

### Site Hızı (Page Speed / Core Web Vitals)

Sayfanın yüklenme ve etkileşim performansı. Google 2021'den beri sıralama faktörü olarak kullanır. LCP, INP, CLS üç ana metriktir.

### LCP (Largest Contentful Paint)

Sayfanın en büyük görünür öğesinin yüklenme süresi. 2.5 saniye altı iyi, 4 saniye üstü kötü. Genellikle ana görsel veya başlığın render süresidir.

### INP (Interaction to Next Paint)

Kullanıcının ilk etkileşiminden sonraki ekran güncellemesine kadar geçen süre. 200ms altı iyi. Hızlı JavaScript ve hafif DOM gerektirir.

### CLS (Cumulative Layout Shift)

Sayfa yüklenirken öğelerin yer değiştirme oranı. 0.1 altı iyi. Görsel ve reklamların boyutu önceden bildirilirse 0'a yakın olur.

### Site Haritası (Sitemap)

Sitenizdeki tüm önemli URL'lerin listesini içeren XML dosyası. Arama motorlarının siteyi keşfetmesini kolaylaştırır. Haber siteleri için `sitemap-news.xml` 48 saatlik içerik penceresi için ayrıca gereklidir.

### IndexNow

Bing ve Yandex'in geliştirdiği anlık URL bildirim protokolü. Yeni içerik yayınlandığında saniyeler içinde tarayıcı kuyruğuna düşer. Google IndexNow'ı desteklemiyor; ona ayrıca sitemap gönderimi gerekir.

---

## Yapay Zeka

### Büyük Dil Modeli (Large Language Model / LLM)

Milyarlarca metin örneğiyle eğitilmiş, doğal dil üretebilen yapay zeka modeli. GPT, Claude, Gemini, Mistral, DeepSeek, Groq üzerinde çalışan modeller başlıca örneklerdir.

### Çıkarım (Inference)

Eğitilmiş modele girdi verip çıktı almak. Eğitim pahalı ve nadir, çıkarım sık ve hızlı olmalı. Üretim ortamında latency ve maliyet odaklı optimizasyon çıkarım üzerinde yapılır.

### Token

Modelin bir defada işlediği metin parçası. Türkçede ortalama 1 kelime ≈ 1.5-2 token. Modellerin fiyatlandırması token bazlıdır; uzun istemler hızla pahalanır.

### İstem (Prompt)

Modele verilen talimat metni. İstem mühendisliği (prompt engineering) modelin davranışını yönetme sanatı. Sistem istemi (system prompt) tüm konuşma boyunca geçerlidir.

### Bağlam Penceresi (Context Window)

Modelin tek seferde "hatırlayabildiği" en fazla token sayısı. GPT-4 için 128K, Claude için 200K-1M, Gemini için 1M+ tokendir. Bağlam aşıldığında modelin baş kısmı unutulmaya başlar.

### İnce Ayar (Fine-tuning)

Hazır bir modeli, kendi verilerinizle ek eğitime tabi tutmak. Belirli domain için (hukuk, sağlık, e-ticaret) doğruluğu artırır. Eğitim pahalı, çıkarım için ek model kaydı gerekir.

### RAG (Retrieval-Augmented Generation)

Modele soru sormadan önce ilgili belgeleri vektör veritabanından çekip istemin içine eklemek. İnce ayara göre daha esnek, daha ucuz; çoğu kurumsal LLM uygulaması RAG ile yapılır.

### Vektör Veritabanı (Vector Database)

Metin parçalarının matematiksel temsillerini (embedding) tutan ve benzerlik araması yapan veritabanı. Pinecone, Weaviate, pgvector yaygın seçeneklerdir. RAG'in altyapı bileşeni.

### Halüsinasyon (Hallucination)

Modelin uydurma ama emin görünen yanıt vermesi. LLM'lerin temel zaafı. RAG, doğrulama katmanı ve düşük sıcaklık (temperature) ile azaltılır ama tamamen yok edilemez.

### Çağrı Toplu İşlem (Batch API)

Birden fazla LLM çağrısını tek istekte gönderip 24 saat içinde yanıt almak. Gerçek zamanlı olmayan işler için %50'ye varan indirim sağlar. Toplu içerik üretimi, gece çalışan ETL süreçleri için ideal.

### İstem Önbelleği (Prompt Cache)

Tekrar eden büyük istemlerin (sistem istem, doküman bağlamı) bir kez işlenip saklanması, sonraki çağrılarda yeniden hesaplanmaması. Maliyeti %60-90 düşürür.

### Şelale Yönlendirme (Cascade Routing)

Bir görevi önce ucuz modele gönderip, gerekirse pahalı modele yükseltmek. "Bu cevap iyi mi?" kontrolü ucuz modelin çıktısına yapılır. Üretim LLM ekonomisinin temel deseni.

### Sıcaklık (Temperature)

Modelin yaratıcılık derecesi. 0'a yakın deterministik ve tutarlı, 1.0+ yaratıcı ve değişken. Bilgi sorgusu için düşük, yaratıcı yazım için yüksek değer kullanılır.

---

## E-Ticaret

### Sanal POS (Virtual POS)

Bir bankanın çevrim içi kredi kartı ödemesi alma altyapısı. Türkiye'de 15+ bankanın kendi sanal POS sistemi vardır. Mağaza her bankayla ayrı sözleşme yapıp birden fazla sanal POS bağlayabilir.

### Ödeme Aracısı (Payment Aggregator)

Birden fazla bankayı tek entegrasyonla erişilebilir kılan platform. iyzico, PayTR, Param yerel örneklerdir. Tek entegrasyonla 10+ banka destek + alternatif ödeme yöntemleri sağlar; karşılığında işlem başına komisyon alır.

### 3D Secure

Kart sahibinin kimliğinin SMS veya tıklama ile doğrulandığı katmanlı güvenlik. 2020'den beri Türkiye'de zorunludur. Hatalı doğrulama akışı kart işleyiciden ceza alabilir.

### Taksit (Installment)

Tek alışveriş tutarının birden fazla aya bölünüp faturalanması. Türk e-ticaret kültüründe vazgeçilmezdir. Her bankanın taksit sayıları ve kart segmentleri farklıdır; kampanya yönetimi karmaşıktır.

### B2B Bayi Sistemi

Toptan satış yapan firmalar için özel fiyat, müsait stok, vade ödeme, sipariş onayı, hesap özeti modüllerini barındıran ayrı panel. Tek e-ticaret yazılımı hem B2C hem B2B destekleyebilir.

### Pazaryeri (Marketplace)

Birden fazla satıcının ortak çatı altında satış yaptığı platform. Trendyol, Hepsiburada, n11, Çiçeksepeti, Amazon TR yerel örneklerdir. Mağaza kendi sitesinden + pazaryerlerinden eşzamanlı satış yapabilir; senkronizasyon kritik.

### Çoklu Mağaza (Multi-store / Multi-vendor)

Aynı yazılım altyapısında birden fazla ayrı mağaza yönetmek. Marka çatı altında farklı bayilik, farklı domain, farklı tema. Yönetimi tek panelden yapılır.

### Sepet Bırakma (Cart Abandonment)

Kullanıcının sepete ürün ekleyip ödeme yapmadan çıkması. E-ticarette %60-80 oranındadır. Otomatik e-posta hatırlatma ve sosyal mecra remarketing ile %5-15'i kurtarılabilir.

### E-fatura / E-arşiv / E-irsaliye

Gelir İdaresi Başkanlığı'nın (GİB) zorunlu kıldığı dijital belge sistemleri. E-fatura B2B, e-arşiv B2C, e-irsaliye kargo süreci içindir. 3 GİB onaylı sağlayıcı (Foriba/Logo, Mikro, İzibiz) yaygın entegrasyon noktasıdır.

### Kargo Entegrasyonu

Kargo firmasının API'siyle otomatik gönderi oluşturma, etiket basma, takip bildirimi gönderme. Aras, Yurtiçi, MNG, Sürat, PTT, UPS, Trendyol Express, Hepsijet en yaygın entegrasyonlardır.

### Dropshipping (Stoksuz Satış)

Sipariş geldikten sonra ürünü tedarikçiden alıp doğrudan müşteriye gönderme modeli. Mağaza stok tutmaz. Düşük başlangıç maliyeti, ama tedarikçi kalite riski yüksektir.

---

## Haber Yazılımı

### Haber Yönetim Sistemi

Bir haber sitesinin yazar paneli, kategori yönetimi, yayın kuyruğu, ajans entegrasyonu, manşet/sürmanşet yönetimi gibi modüllerini barındıran yazılım. Genel amaçlı CMS'lere göre habere özgü iş akışları sunar.

### Ajans Entegrasyonu

Anadolu Ajansı (AA), Demirören Haber Ajansı (DHA), İhlas Haber Ajansı (İHA), ANKA, Türk Haber Ajansı (THA), HİBYA, İGFA, BHA gibi ulusal ajansların haber akışını otomatik çeken modül. Her ajansın kendi protokolü vardır; adapter pattern ile yönetilir.

### Manşet Yönetimi

Anasayfanın görsel hiyerarşisinin (sürmanşet, manşet, alt manşet, kategori bantları) editör tarafından sürükle-bırak ile düzenlenmesi. Çoğu haber sitesinin günde 5-15 kez güncellediği alandır.

### Yayın Kuyruğu

Onay bekleyen, yayınlanmaya hazır, programlanmış, taslak haberlerin ayrı bir liste olarak görüntülenmesi. Editöryal iş akışının görsel temsili.

### Manşet Devri

Bir haberin belirli sürede başka kategoriye veya ön sayfa dışına otomatik geçişi. Anasayfa sürekli güncel kalır, eski haberler kategori arşivine kayar.

### Haber Tekilleştirme

Aynı haberin birden fazla ajanstan gelmesi durumunda yalnızca birinin yayınlanması için içerik benzerliği analizi. Hash karşılaştırma, başlık benzerliği, çekirdek kelime kümesi yöntemleri kullanılır.

### Paywall (Ödeme Duvarı)

Belirli sayıda makaleden sonra ya da belirli premium içerikler için ödeme isteme mekanizması. The New York Times modeli yumuşak duvar (3 makale ücretsiz), bazı yerel siteler sert duvar (her makale ödeme) kullanır.

### Sürmanşet

Anasayfanın en üstündeki büyük görsel + başlık alanı. Genellikle tek tek seçilir, ortalama 5-15 dakika canlı kalır. Yüksek tıklama oranı ve sosyal medyaya yansıma için kritik.

### AMP (Accelerated Mobile Pages)

Google'ın geliştirdiği, mobilde hızlı yüklenen HTML standardı. Haber sitelerinde Google News kapsamına girmek için yaygın kullanıldı. 2024'ten sonra Google AMP zorunluluğunu kaldırdı, ama özellik hâlâ destekli.

### Google News Onayı

Bir haber sitesinin Google News'e dahil edilmesi için yapılan başvuru. Schema.org NewsArticle, NewsMediaOrganization markup, doğrulanmış yayıncı bilgisi, sitemap-news.xml, AMP HTML, IndexNow zorunluluk olarak görülür.

### Yazı İşleri Paneli

Editör, yazar, fotoğrafçı, video editörü gibi farklı rolleri ayrı yetkilendirme altında yöneten arayüz. Rol bazlı izin sistemi gerektirir.

---

## Güvenlik

### XSS (Cross-Site Scripting)

Kötü amaçlı JavaScript kodunun bir başka kullanıcının tarayıcısında çalıştırılması. Kullanıcı girdisinin HTML'e doğrudan yazılması en yaygın sebebidir. Çıktı kaçışı (output escaping) tek savunma.

### SQL Enjeksiyonu (SQL Injection)

Kullanıcı girdisinin SQL sorgusuna parametrik olmadan eklenmesi sonucu sorgunun amaçtan çıkması. Prepared statement / parametrik sorgu standart savunmadır. Modern ORM'ler bu sorunu büyük ölçüde çözer.

### CSRF (Cross-Site Request Forgery)

Kullanıcının oturumu açıkken farkında olmadan başka bir sitede tetiklenen sahte istek. Token bazlı koruma standarttır; her form submit'inde sunucu tarafından doğrulanan rastgele token gönderilir.

### Şifreleme (Encryption)

Veriyi şifreleyerek yetkisiz erişimi engelleme. Aktarımda (TLS) ve depolamada (AES-256) farklı katmanlardır. Şifre saklamada bcrypt veya argon2 hash kullanılır, asla düz metin değil.

### Kimlik Doğrulama (Authentication)

Kullanıcının iddia ettiği kişi olduğunu doğrulama. Şifre, biyometri, SMS, e-posta, TOTP, donanım anahtarı farklı katmanları. İki faktörlü kimlik doğrulama (2FA) modern standarttır.

### Yetkilendirme (Authorization)

Kimlik doğrulama yapılmış kullanıcının hangi işlemleri yapabileceğini belirlemek. Rol bazlı (RBAC), izin bazlı (PBAC), öznitelik bazlı (ABAC) modeller yaygındır.

### Oturum Yönetimi (Session Management)

Giriş yapan kullanıcının hangi cihazda, ne süre, hangi izinle aktif olduğunu takip etme. Çerez tabanlı (cookie), token tabanlı (JWT) farklı modeller var. Oturum kaçırma (session hijacking) en yaygın saldırı vektörü.

### Brute Force (Kaba Kuvvet)

Şifre veya token denemelerini otomatik olarak yapan saldırı. Rate limiting (saniyede maksimum X deneme), CAPTCHA, IP bloklama standart savunma katmanlarıdır.

### Sıfır Gün (Zero-day)

Henüz keşfedilip yamalanmamış güvenlik açığı. Açıklandığı anda saldırı yüzeyi açılır, yama yayımlanana kadar sistemler savunmasızdır. Düzenli güncelleme tek koruma.

### WAF (Web Application Firewall)

Web uygulamasının önünde duran, kötü amaçlı isteği filtreleyen güvenlik katmanı. Cloudflare WAF, ModSecurity yaygın çözümlerdir. SQL enjeksiyonu, XSS gibi paternleri otomatik bloklar.

---

## DevOps & Sunucu

### Sürekli Entegrasyon (Continuous Integration / CI)

Geliştiricinin kodunu ana dala her gönderdiğinde otomatik test ve kontrol çalıştırılması. GitHub Actions, GitLab CI, Jenkins yaygın araçlardır. Hata erken yakalanır, ekip uyumu artar.

### Sürekli Dağıtım (Continuous Deployment / CD)

CI başarılı olduğunda kodun otomatik olarak üretim sunucusuna gönderilmesi. Olgun ekiplerin çalışma şekli; manuel deploy adımı kalmaz, hatalar geri alma (rollback) ile düzeltilir.

### Konteyner (Container)

Uygulamayı bağımlılıkları ile birlikte izole eden hafif sanallaştırma birimi. Docker en yaygın çalıştırıcıdır. "Bende çalışıyordu" sorununu büyük ölçüde çözer.

### Orkestrasyon (Orchestration)

Birden fazla konteyneri yönetme, ölçekleme, yönlendirme katmanı. Kubernetes endüstri standardı, Docker Swarm daha hafif alternatif, Nomad farklı bir yaklaşım.

### Sanal Özel Sunucu (VPS / VDS)

Tek bir fiziksel sunucunun sanallaştırılarak birden fazla bağımsız sunucu olarak sunulması. Kendine ayrılan CPU, RAM, disk kaynakları vardır. Paylaşımlı hostinge göre çok daha güçlü, kendi sunucuya göre çok daha ucuz.

### Yatay Ölçekleme (Horizontal Scaling)

Sistem yükünü karşılamak için sunucu sayısını artırma. Yük dengeleyici arkasında 2 sunucu, 5 sunucu, 50 sunucu olabilir. Modern yaklaşım dikey (tek sunucuyu büyütme) yerine yatay ölçekleme.

### Yedekleme (Backup)

Veri kaybına karşı dosyaların ve veritabanlarının ayrı yere kopyalanması. 3-2-1 kuralı: 3 kopya, 2 farklı medya, 1 offsite. Geri yükleme test edilmemiş yedek, yedek değildir.

### İzleme (Monitoring)

Sistem sağlığını sürekli takip etme. CPU, RAM, disk, ağ, uygulama metrikleri, hata oranları. Grafana, Prometheus, Datadog yaygın araçlardır. Alarm kurmadan izleme yarıdır.

### Günlük (Log)

Sistemin yaptığı işlemlerin metin kayıtları. Hata ayıklama, güvenlik denetimi, performans analizi için kritik. Yapılandırılmış (JSON) log modern standardı; grep'lenebilirlik için tek satır olmalı.

### Sıfır Kesinti Dağıtımı (Zero-downtime Deployment)

Yeni sürüm canlıya alınırken kullanıcının kesinti yaşamaması. Blue-green deployment, rolling update, canary release farklı teknikleridir.

### CDN Önbelleği Geçersizleştirme (Cache Invalidation)

İçerik değiştiğinde CDN'in eski sürümü tutmaması için bildirim göndermek. "İki zor problem var: cache invalidation ve isimlendirme" sözü bu konunun zorluğundandır.

---

## Yasal & Uyumluluk

### KVKK (Kişisel Verileri Koruma Kanunu)

Türkiye'nin GDPR muadili kişisel veri koruma kanunu. Açık rıza, veri silme hakkı, veri taşıma, aydınlatma metni gibi zorunluluklar getirir. 2016'da yürürlüğe girdi.

### VERBİS (Veri Sorumluları Sicili)

KVKK kapsamındaki şirketlerin Veri Sorumluları Sicil Bilgi Sistemi'ne kayıt zorunluluğu. Hangi verileri ne amaçla işlediğinizi beyan etmek gerekir. Kayıtsız çalışmak idari para cezası doğurur.

### Açık Rıza (Explicit Consent)

Kişisel veri işlenmesi için kullanıcının özgür iradesi, aydınlatılmış ve özelleştirilmiş onayı. Önceden işaretli kutucuk, genel rıza gibi yöntemler geçersizdir. Her amaç için ayrı rıza alınmalıdır.

### Çerez Politikası (Cookie Policy)

Web sitesinin hangi çerezleri ne amaçla kullandığını belirten beyan + kullanıcının yönetim arayüzü. Reklam ve analitik çerezler için açık rıza zorunludur.

### BİK (Basın İlan Kurumu)

Yerel haber gazetelerinin resmi ilan dağıtım otoritesi. Online haber siteleri için ayrı kayıt ve denetim kuralları vardır. Mahreç gösterme, fotoğraf telifi gibi konuları denetler.

### İYS (İleti Yönetim Sistemi)

Ticari elektronik ileti (SMS, e-posta) göndermek için zorunlu izin kontrol sistemi. İzin alınmamış kişiye reklam SMS atmak idari para cezası doğurur. https://iys.org.tr üzerinden yönetilir.

### GİB (Gelir İdaresi Başkanlığı)

Türkiye'nin vergi otoritesi. E-fatura, e-arşiv, e-irsaliye, e-defter zorunluluklarını GİB yönetir. E-ticaret yazılımları GİB onaylı sağlayıcılarla entegre olmak zorundadır.

### Mahreç

Haber içeriğinin kaynağının (ajans, gazete, muhabir) belirtilmesi. BİK kurallarına göre zorunlu, gösterilmediği takdirde yaptırım uygulanır. Otomatik bot çekimlerde mahreç doldurma yazılım tarafında halledilir.

### Mücbir Sebep

Sözleşmeden doğan yükümlülüğün ifa edilmesini engelleyen olağanüstü hal (deprem, salgın, savaş). Yazılım hizmet sözleşmelerinde sıkça atıf yapılır; SLA hesaplamalarında istisna sayılır.

### SLA (Hizmet Seviyesi Anlaşması)

Hizmet sağlayıcının taahhüt ettiği uptime, yanıt süresi, destek kalitesi gibi metriklerin yazılı belgelenmesi. %99.9 (yıllık 8.76 saat kesinti) endüstri ortalaması, %99.99 (52 dakika) premium kabul edilir.

---

## İçerik & Tasarım

### Kullanıcı Deneyimi (User Experience / UX)

Kullanıcının ürünü kullanırken yaşadığı duygusal ve işlevsel deneyim. Estetikten daha geniş; bilgi mimarisi, akış, mikro etkileşimler, performans hepsi UX'in parçası.

### Kullanıcı Arayüzü (User Interface / UI)

Kullanıcının uygulamayla etkileşim kurduğu görsel katman. Renkler, tipografi, ikonlar, düğmeler, kartlar. UX'in görsel ifadesi.

### Bilgi Mimarisi (Information Architecture)

Bir uygulamadaki içerik ve özellik hiyerarşisinin organizasyonu. Menü yapısı, kategorizasyon, etiketleme sistemi. Karmaşık uygulamalarda hayati önemli.

### Etkileşim Tasarımı (Interaction Design)

Kullanıcı bir öğeye tıkladığında ne olduğu, hover ettiğinde nasıl tepki verdiği, hatalı işlem sonucunda nasıl bilgilendirildiği. Mikro animasyonlar bu kategoride değerlendirilir.

### Responsive Tasarım

Site içeriğinin farklı ekran boyutlarına (telefon, tablet, masaüstü) otomatik uyum sağlaması. CSS media queries, esnek grid sistemleri, görsel boyut ayarları üzerinden gerçekleştirilir.

### Mobile-First

Önce mobil ekran için tasarım yapıp sonra masaüstüne genişletme yaklaşımı. 2015 sonrası Google da bu yaklaşımı sıralama faktörü olarak benimsedi.

### Erişilebilirlik (Accessibility / a11y)

Engelli kullanıcıların da uygulamayı kullanabilmesi. Ekran okuyucu uyumluluğu, klavye navigasyonu, yüksek kontrast, alt text. WCAG 2.2 standart kontrol listesidir.

### Tipografi (Typography)

Yazı tipi seçimi, boyut hiyerarşisi, satır yüksekliği, harf aralığı düzenlemesi. Okunabilirlik ve marka kimliği açısından kritik. 16px minimum gövde metni mobil için standart.

### Renk Paleti (Color Palette)

Bir tasarımda kullanılan ana, ikincil, vurgu, nötr renklerin tutarlı seti. Marka kimliğinin görsel temeli. Hex, HSL, OKLCH farklı tanımlama sistemleridir.

### Boş Durum (Empty State)

Hiç veri olmadığında gösterilen ekran (örneğin yeni sepet, hiç sipariş yok). Tasarımın sık unutulan ama kullanıcı deneyimini ciddi etkileyen kısmı.

### Yükleme Durumu (Loading State)

Bir işlem devam ederken gösterilen geri bildirim (spinner, skeleton, progress bar). 1 saniyenin üstündeki bekleme süreleri için zorunludur; kullanıcı sayfanın donduğunu sanmasın.

### Onay Penceresi (Modal / Dialog)

Sayfa üstüne açılan, kullanıcının onayını veya bilgisini bekleyen pencere. Kapatma, kaçış tuşu, dış tıklama davranışları net olmalıdır.

---

## Katkı

Bu sözlüğe katkı yapmak istiyorsan:

1. Yeni terim ekleme: Pull request açın, mevcut yapıya uygun şekilde yazın
2. Düzeltme: Yanlış veya eksik açıklamalar için issue açın
3. Çeviri: Türkçe karşılığı tartışmalı terimleri tartışma için issue olarak getirin
4. Kategori önerisi: Yeni bir başlık eklenmeli mi? Issue açın

İçerik kuralları:

- Her terim için: Türkçe karşılık, parantez içinde İngilizce orijinal, 2-4 cümle sade açıklama
- Belirli ürün veya şirket adına referans verme (banka, kargo, ajans, AI sağlayıcısı gibi sektörel partner kategorisi hariç)
- Kod örneği vermekten kaçın (markdown only repo)
- Tarafsız bilgi; tavsiye vermek yerine ne olduğunu açıklayan dil

---

## Lisans

MIT License — eğitim ve referans amaçlı serbest kullanım. Atıf yaparsanız memnun oluruz, zorunlu değildir.

---

Hazırlayan: [Mahmut Gündüzalp](https://github.com/alestaweb) — Alesta WEB (alestaweb.com), Şanlıurfa, Türkiye. 2005'ten beri Türk pazarına haber yazılımı, e-ticaret yazılımı ve kurumsal web geliştirme çözümleri üretiyoruz. İlgili kaynak: [awesome-turkish-cms](https://github.com/alestaweb/awesome-turkish-cms), [turkce-web-yazilim-rehberi](https://github.com/alestaweb/turkce-web-yazilim-rehberi).
