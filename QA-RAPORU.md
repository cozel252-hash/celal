# Sessiva™ tema QA raporu

## Sonuç

Tema paketi yerel ve bağlantısız testlerde yüklemeye hazırdır. Bu kontrol gerçek bir Shopify mağaza önizlemesi değildir; ürün, ödeme ve uygulama proxy'si mağazaya yüklendikten sonra Shopify üzerinde ayrıca test edilmelidir.

## Geçen kontroller

- Shopify CLI Theme Check: **0 hata**. Resmî Dawn tabanından gelen uyarılar ve Google Fonts için performans uyarıları kaldı; yüklemeyi engellemez.
- Tüm tema JSON dosyaları ve özel section schema'ları ayrıştırıldı.
- Ürün ve ana sayfa şablonlarının bölüm/ayar/blok eşleşmesi doğrulandı.
- Kit eşleşmesi: ürün, video, yorum, özellik, üç anlatım, önce/sonra, güvence, SSS ve CTA bölümleri açık.
- `as-product`: kapıda ödeme, ödeme logoları, teslimat çizelgesi, sabit çubuk ve 1/2/4 paket kartları açık.
- Video şeridi 8 blok; yorum şeridi 4 açık ve belirgin gerçek yorum yer tutucusu içeriyor.
- Kapıda ödeme formunda `localStorage` ve `sessionStorage` kullanılmıyor.
- Playwright masaüstü: 1400×900, `scrollWidth = innerWidth = 1400`, JavaScript hatası yok.
- Playwright mobil: 390×844, `scrollWidth = innerWidth = 390`, JavaScript hatası yok, sabit çubuk için 70 px alt boşluk var.
- Varsayılan 2'li paket, paket/fiyat/checkout bağlantısı senkronizasyonu, kapıda ödeme modalı açma-kapama ve form temizleme doğrulandı.
- Mobilde 3 video kartı ve 2 yorum kartı genişliği doğrulandı.
- Yorum şeridinin normal, hover ve `prefers-reduced-motion` durumlarında akmaya devam ettiği doğrulandı.

## Görsel inceleme

- Masaüstü tam sayfa: `qa/desktop-full.png`
- Mobil tam sayfa: `qa/mobile-full.png`
- Mobil inceleme dilimleri: `qa/mobile-part-00.png` – `qa/mobile-part-03.png`

Türkçe karakterlerde çakışma, yatay taşma veya kesilmiş kart görülmedi. Doğal yeşil koyu palet ile Outfit + DM Sans eşleşmesi tutarlı göründü.

## Yayından önce gerekli gerçek veriler

- Shopify ürün kaydı ve ürün görselleri
- Gerçek fiyat, karşılaştırma fiyatı ve varsa miktar indirimleri
- Gerçek kargo, hazırlık, teslimat, iade ve garanti koşulları
- Gerçek ürün ölçüsü, malzemesi, bakım ve kullanım bilgileri
- Doğrulanmış müşteri yorumları ve ürün videoları
- Gerçek ödeme sağlayıcısına uygun ödeme işaretleri
- Kapıda ödeme ücreti ile çalışan `/apps/kapida-odeme` uygulama proxy'si

Referans URL bu çalışma ortamının ağ geçidinde `403 CONNECT` ile engellendi. Bu nedenle referans sitenin doğrulanmamış metinleri, fiyatları, logoları ve görselleri pakete alınmadı.
