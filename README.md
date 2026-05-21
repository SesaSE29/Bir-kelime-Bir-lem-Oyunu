# Bir Kelime Bir İşlem — Çoklu Cihaz Sürümü

Herkes kendi telefonundan/bilgisayarından bağlanıp birlikte oynayabileceğiniz online sürüm.

## Nasıl Çalışır?

1. Birisi (host) sunucu üzerinden yeni oda kurar → 4 karakterli oda kodu alır.
2. Diğerleri aynı adrese girip oda kodunu yazar.
3. Herkes aynı 9 harfi/6 sayıyı görür, kendi cihazından gizli cevap girer.
4. Süre bitince herkesin cevabı açıklanır, puanlar otomatik hesaplanır.

Tüm kişilerin aynı Wi-Fi ağında olmasına gerek yok; sunucu internette olduğu için herkes nereden olursa olsun bağlanabilir.

## Kurulum Seçenekleri

### Seçenek 1: Render.com (En Kolay, Tamamen Ücretsiz)

1. https://render.com adresinde ücretsiz hesap aç (GitHub ile giriş yapabilirsin).
2. Bu klasördeki dosyaları bir GitHub repo'suna yükle (yeni repo oluştur, dosyaları sürükle bırak).
3. Render'da "New +" → "Web Service" tıkla.
4. GitHub repo'nu bağla.
5. Ayarlar:
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
   - **Instance Type:** Free
6. "Create Web Service" tıkla. 2-3 dakikada hazır.
7. Render sana `https://senin-uygulaman.onrender.com` gibi bir adres verir. Arkadaşlarınla paylaş.

**Not:** Free plan'da 15 dakika kullanılmayınca uyur, ilk açılışta 30 saniye yavaş olabilir. Sonrası akıcı.

### Seçenek 2: Glitch.com (Daha da Kolay, Hesap Bile Gerekmez)

1. https://glitch.com → "New project" → "glitch-hello-node"
2. Sol panelden tüm dosyaları sil.
3. Bu klasördeki `server.js`, `package.json` ve `public/index.html` dosyalarını yükle (sürükle-bırak).
4. Otomatik olarak çalışmaya başlar. URL'in sağ üstte "Share" tuşundadır.

**Not:** Glitch free plan'da daha sınırlı; küçük gruplar için yeterli.

### Seçenek 3: Kendi Bilgisayarın (Aynı Wi-Fi'daki Arkadaşlar)

1. Node.js'i kur: https://nodejs.org (LTS sürüm)
2. Terminal'de bu klasöre git:
   ```
   cd multi-device
   npm install
   npm start
   ```
3. Bilgisayarının yerel IP'sini öğren:
   - **Windows:** Cmd → `ipconfig` → IPv4 Adresi (örn. 192.168.1.10)
   - **Mac/Linux:** Terminal → `ifconfig` → inet (örn. 192.168.1.10)
4. Arkadaşların aynı Wi-Fi'da telefonundan tarayıcıya yazsın: `http://192.168.1.10:3000`
5. Sen kendi bilgisayarında `http://localhost:3000` adresinden bağlan.

## Oyun Akışı

1. **Host** "Yeni Oda Oluştur" der, oda kodunu görür.
2. **Diğerleri** "Bir Odaya Katıl" der, kodu girer.
3. Host ayarları yapar (tur sayısı, süre, joker hakkı vb.).
4. Host "Oyunu Başlat" der.
5. Her turda host "Süreyi Başlat" der.
6. Herkes kendi ekranından cevabını girer. Cevaplar gizlidir.
7. Herkes bitirince veya süre dolunca host "Sonuçları Göster" der.
8. Sonraki tura geçilir. Sonunda madalyalı sıralama.

## Sorun Giderme

- **"Oda bulunamadı"** → Kodu büyük harfle ve eksiksiz yaz.
- **TDK çalışmıyor** → Tarayıcı CORS engelliyor olabilir; o tur "grup karar versin" moduna düşer.
- **Bağlantı kopuyor** → Sayfayı yenile, aynı isimle tekrar gir; sistem seni eski yerine geri koyar.
- **Render uyumuş** → İlk yüklemede 30 saniye bekleyin; sonra normal hızda çalışır.

## Dosyalar

```
multi-device/
├── server.js          # Node.js sunucusu
├── package.json       # bağımlılıklar
├── public/
│   └── index.html     # Oyun arayüzü
└── README.md          # bu dosya
```
