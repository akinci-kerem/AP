# UI — Görsel Arayüzler

Bu klasör projenin tüm görsel arayüz tasarımlarını ve arayüz varlıklarını içerir.

## Klasör yapısı

```
UI/
├── screens/      # Tam ekran ve sayfa tasarımları
├── components/   # Yeniden kullanılan bileşenler (buton, tablo, form alanı, uyarı kutusu...)
├── styles/       # Renk, yazı tipi, boşluk, köşe yuvarlama gibi tasarım değerleri
└── assets/       # Logo, ikon ve diğer görsel dosyalar
```

## Kurallar

- Dosya ve klasör adları `DOC/02-developer-directives.md` içindeki adlandırma kuralına uyar (İngilizce, küçük harf, tire ile ayrılmış).
- Bir ekran değiştiğinde ilgili ekran görüntüsü `DOC/screenshots/` içinde de güncellenir ve `DOC/03-screenshots.md` dizini buna göre düzenlenir.
- Arayüz testleri `DOC/04-interface-test-plan.md` içinde listelenir; ekran değişikliği test kapsamını da etkiliyorsa bu belge güncellenir.
- Tekrar kullanılan öğeler `screens/` içinde kopyalanmaz; `components/` içinde tek kez tanımlanır.
