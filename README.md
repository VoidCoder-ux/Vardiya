# Vardiya

Vardiya, haftalik calisan vardiyalarini planlamak, ozetlemek ve paylasmak icin hazirlanmis statik bir PWA uygulamasidir. Kurulum gerektirmez; `index.html`, `manifest.json`, `sw.js` ve ikon dosyalariyla calisir.

## Ozellikler

- Haftalik vardiya planlama ve calisan yonetimi
- Sabah, aksam, gece, ogle, izin ve ozel saat vardiyalari
- Haftalik ozet, aylik rapor ve CSV disa aktarma
- JSON yedek alma ve geri yukleme
- WhatsApp vardiya bildirimi ve paylasilabilir salt okunur hafta linki
- PWA destegi ve offline kullanim icin service worker cache'i

## Kullanim

Dosyalari herhangi bir statik web sunucusundan yayinlayin veya yerelde basit bir HTTP sunucusu ile acin. Tarayicida uygulamayi actiktan sonra once Calisanlar sekmesinden calisan ekleyin, ardindan Haftalik Plan uzerinden vardiya atayin.

## Veri Saklama

Uygulama verileri tarayicinin `localStorage` alaninda `weeklyShiftTracker` anahtariyla saklanir. Veriler sunucuya gonderilmez. Farkli cihaz veya tarayiciya gecmeden once Haftalik Ozet ekranindaki Yedekle secenegiyle JSON yedegi alin.

## Yedekleme ve Geri Yukleme

Yedekleme JSON formatindadir ve calisanlar, vardiyalar, sablonlar ve veri surumunu icerir. Geri yukleme sirasinda dosya yapisi kontrol edilir; bozuk veya gecersiz dosyalar mevcut verinin uzerine yazilmaz.

## PWA ve Offline Davranis

Service worker statik varliklari cache'e alir. Sayfa HTML'i yeni surumlerin hizli gorunmesi icin network-first stratejisiyle istenir; baglanti yoksa cache'teki son surum kullanilir.

## Guvenlik Notu

Calisan bilgileri, vardiya notlari, sablon adlari ve paylasim linki icerikleri ekrana basilmeden once HTML olarak escape edilir. Paylasilabilir linklerden gelen veri guvenilmeyen kabul edilir ve temel sekil dogrulamasindan gecer.
