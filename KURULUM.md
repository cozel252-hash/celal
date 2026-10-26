# Sessiva™ Shopify tema kurulumu

Bu paket, Shopify'ın resmi ve ücretsiz Dawn teması üzerine hazırlanmıştır. Tema tüm mağazaya uygulanır; ana sayfa, ürün sayfası, sepet ve koleksiyon sayfaları Sessiva™ tasarım dilini kullanır.

## Temayı yükleme

1. Teslim edilen `sessiva-shopify-tema.zip` dosyasını açmayın.
2. Shopify yöneticisinde **Online Mağaza → Temalar** sayfasına gidin.
3. **Tema ekle → Zip dosyası yükle** seçeneğini açın ve ZIP'i yükleyin.
4. Yükleme bitince temanın üç nokta menüsünden **Önizle** seçeneğini kullanın.
5. Masaüstü ve mobil görünümü kontrol ettikten sonra temayı siz yayınlayın.

## İlk özelleştirme

Shopify tema düzenleyicisinde aşağıdaki alanları doldurun:

1. **Ana sayfa → Sessiva ürün bölümü:** Satılacak ürünü seçin. Ürün adı, fiyatı, karşılaştırma fiyatı ve görseller Shopify ürün kaydından gelir.
2. **Ürünler:** En az dört yüksek çözünürlüklü ürün görseli ekleyin. İlk görsel temiz ürün fotoğrafı; diğerleri kullanım, yakın plan ve ölçü görselleri olabilir.
3. **Ürün paketleri:** 1, 2 ve 4 adet seçeneklerini kontrol edin. Sayfadaki paket toplamı varsayılan olarak ürün birim fiyatı ile adet çarpımından hesaplanır. Özel paket indirimi sunacaksanız Shopify'da aynı tutarı veren otomatik miktar indirimi oluşturun; ödeme sayfasında ayrıca test edin.
4. **Karşılaştırma fiyatı:** İndirim rozeti göstermek için ürüne gerçek bir karşılaştırma fiyatı girin. Doğrulanmamış eski fiyat kullanmayın.
5. **Teslimat ve iade metinleri:** Gerçek kargo, teslim ve iade koşullarınızla değiştirin.
6. **Marka:** Mağaza adını `Sessiva` yapın veya marka logonuzu Header bölümünden yükleyin; metin logo mağaza adını otomatik kullanır.

## Yayından önce doldurulacaklar

- **Yorumlar:** Temadaki `[Gerçek müşteri yorumu …]` metinleri belirgin yer tutucudur. Bunları yalnızca doğrulanmış, gerçek yorumlarla değiştirin. Sahte isim, puan veya yorum eklemeyin.
- **Videolar:** Video şeridinde sekiz alan bulunur. Gerçek ürün videolarını Shopify'a yükleyip bölüm ayarlarından seçin. Video yoksa yer tutucu kartlar düzenleyicide görünür.
- **Sağlık ifadeleri:** Ürün açıklamalarında yalnızca belgeleyebildiğiniz ifadeleri kullanın. Tedavi, iyileştirme veya ağrıyı kesin giderme gibi tıbbi iddialar eklemeyin.
- **Ödeme logoları:** Kart ve güven işaretleri temsili yer tutucudur. Kullandığınız gerçek ödeme sağlayıcısına uygun görseli tema düzenleyicisinden yükleyin.
- **Garanti, teslimat ve ücretsiz kargo:** Temadaki metinleri mağazanızın gerçek ticari koşullarıyla eşleştirin.

## Kapıda ödeme

Tema, hareketli bir **Kapıda Ödemeyle Sipariş Ver** düğmesi ve Türkçe sipariş formu içerir. Form alanları tarayıcıda saklanmaz; form her açılış ve kapanışta temizlenir. E-posta isteğe bağlıdır.

Gerçek sipariş oluşturmak için mağazanızda `/apps/kapida-odeme` yoluna bağlı, imza doğrulayan bir Shopify uygulama proxy'si gerekir. Tema tek başına sipariş servisi kurmaz.

Kurulumdan sonra şu kontrolleri yapın:

1. Uygulama proxy'sinin doğru endpoint'e bağlı olduğunu doğrulayın.
2. Kapıda ödeme ücretini hem tema ayarında hem sunucu tarafındaki sipariş servisinde aynı tutara getirin.
3. Sunucu tarafında ürün/varyant ve paket fiyatlarını doğrulayın; tarayıcıdan gelen fiyata güvenmeyin.
4. E-postasız bir test siparişi verin; ürün, adet, ücret, telefon ve adres alanlarını Shopify yöneticisinde kontrol edin.
5. Test siparişini iptal edin.

## Kalite kontrol listesi

- Ana sayfa, ürün sayfası, `/cart` ve `/collections/all` adreslerini masaüstü ve mobilde açın.
- Ürün galerisinin kaydırıldığını ve sayacın güncellendiğini kontrol edin.
- Sayfa ilk açıldığında ikinci paket seçili olmalı; paket değişince ana ve sabit düğmedeki fiyat/adet birlikte değişmelidir.
- **Hemen Satın Al** düğmesi seçilen varyant ve adetle doğrudan ödeme akışına gitmelidir.
- Kapıda ödeme formu açılmalı, Türkçe doğrulama mesajları vermeli ve kapatılıp yeniden açıldığında boş olmalıdır.
- Video şeridinin mobilde üç kart, yorum şeridinin iki kart gösterdiğini kontrol edin.
- Yorum şeridi fare üzerindeyken ve azaltılmış hareket ayarında da akmaya devam etmelidir.
- SSS akordeonları, önce/sonra sürgüsü ve sabit satın alma çubuğu çalışmalıdır.
- Yatay taşma, kesilen Türkçe karakter veya İngilizce arayüz metni kalmamalıdır.

## Tema bileşenleri

Ana sayfa şablonunda banner, güven şeridi, fayda kartları, ürün satın alma alanı, video şeridi, yorum şeridi, üç anlatım bloğu, önce/sonra, garanti, SSS ve son çağrı bölümleri açık gelir. Sepet ve koleksiyon sayfalarında Dawn'ın işlevsel ana bölümleri korunur; Sessiva güven ve garanti bölümleri bunlara eklenir.
