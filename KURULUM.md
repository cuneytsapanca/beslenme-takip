# Sayarak — iPhone'a kurulum

Tek dosyalık bir web uygulaması (`index.html`). Kurulum ücretsiz, App Store hesabı gerekmiyor.

## Önemli: dosyayı doğrudan açma

Safari, `file://` ile açılan sayfalarda veri saklamayı engelliyor. Yani `index.html`'i
Dosyalar uygulamasından açarsan **girdiğin veriler kaybolur**. Uygulama bu durumu algılayıp
kırmızı bir uyarı gösterir. Bir adres üzerinden açman gerekiyor.

## Yöntem 1 — GitHub Pages (önerilen, ücretsiz ve kalıcı)

1. github.com'da yeni bir depo aç. **Public** olmalı (Pages ücretsiz katmanı için).
   Ad örneği: `beslenme`.
2. `index.html` dosyasını depoya yükle (Add file → Upload files).
3. Settings → Pages → Source: **Deploy from a branch**, Branch: **main / (root)** → Save.
4. 1-2 dakika sonra adres hazır olur:
   `https://<kullanıcı-adın>.github.io/beslenme/`
5. iPhone'da Safari ile bu adresi aç → **Paylaş** → **Ana Ekrana Ekle**.

Artık ikonu ana ekranında, tam ekran ve çevrimdışı çalışır. Adres public olsa da
içinde kişisel veri yok — veriler yalnızca telefonun içinde tutulur.

## Yöntem 2 — Yerel ağ üzerinden hızlı deneme

Mac'te, dosyanın olduğu klasörde:

```
python3 -m http.server 8080
```

Sonra iPhone'da (aynı Wi-Fi'da) `http://<mac-ip-adresin>:8080` adresini aç.
Sadece test için; Mac kapanınca erişim biter.

## Yedekleme

Ayarlar → **Yedek al (JSON)**. Ayda bir almanı öneririm; Safari uzun süre
kullanılmayan sitelerin verisini temizleyebiliyor (ana ekrana eklenmiş
uygulamalarda bu risk düşük ama sıfır değil).

Yeni telefona geçerken: aynı adresi aç → Ayarlar → **Yedekten yükle**.

## Eşinle kullanım

İki profil aynı uygulamada. Herkes kendi telefonuna kurar ve kendi profilini kullanır;
veriler birbirinden bağımsızdır. Aynı telefondan iki profili de takip etmek de mümkün —
üstteki sekmelerden geçiş yapılır.

---

## Sonraki adımlar (istersen)

- **Bulut senkron**: Supabase ücretsiz katmanıyla iki telefon aynı veriyi görebilir.
- **Gerçek APK/IPA**: Capacitor ile paketlenebilir; iOS için Apple Developer hesabı ($99/yıl) gerekir.
- **Fotoğraftan tanıma**: Yemek fotoğrafı çekip porsiyon tahmini. Bir API anahtarı gerektirir.
- **Haftalık rapor**: Hafta sonunda özet e-posta / bildirim.
