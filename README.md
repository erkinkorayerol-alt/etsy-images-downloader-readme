# etsy-images-downloader-readme
# Etsy Media Downloader (ZIP)

Etsy ürün sayfasındaki tüm görselleri tek tıkla indirip **tek bir ZIP dosyası** halinde bilgisayarınıza kaydeder.

## Kurulum
1. `chrome://extensions` adresine gidin.
2. Sağ üstten "Geliştirici modu"nu açın.
3. "Paketlenmemiş öğe yükle" butonuna tıklayın ve bu klasörü seçin.

## Kullanım
1. Bir Etsy ürün sayfasını açın (`https://www.etsy.com/listing/...`).
2. Eklenti simgesine tıklayın.
3. "Görselleri ZIP olarak indir" butonuna basın.
4. Eklenti sayfadaki tüm ürün görsellerini bulur, indirir ve `etsy-images.zip` adıyla tek bir dosyada paketler.

## Nasıl çalışır
- `content.js` sayfadaki yüksek çözünürlüklü görsel URL'lerini toplar.
- `background.js` (service worker) bu görselleri indirir, JSZip ile ZIP'e paketler ve Chrome'un indirilenler klasörüne kaydeder.
- Popup kapansa bile indirme arka planda (service worker) devam eder.

## Notlar
- Sadece `www.etsy.com` ürün sayfalarında ve etsystatic.com üzerindeki görsellerde çalışır (manifest'teki host_permissions).
- Görsel sayısı çok fazlaysa ZIP oluşturma birkaç saniye sürebilir; popup'ta ilerleme durumu gösterilir.
