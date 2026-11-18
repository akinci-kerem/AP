# Geliştirici Direktifleri

> Son güncelleme: 2026-11-18

Bu belge projede çalışan herkes için bağlayıcı kuralları tanımlar. Kurallar değişirse bu dosya önce güncellenir, sonra kod.

## 1. Dil

| Alan | Dil | Not |
|---|---|---|
| Dosya ve klasör adları | İngilizce | Küçük harf, tire ile ayrılmış (bkz. bölüm 2) |
| Dokümantasyon içeriği | Türkçe | `DOC/` ve `UI/` içindeki tüm metinler |
| Kod tanımlayıcıları (değişken, fonksiyon, sınıf, tablo, alan) | İngilizce | Örn. `invoiceList`, `getInvoiceById` |
| Kod yorumları | Türkçe veya İngilizce | Projede tek dil seçilip tutarlı kullanılır: [TODO] |
| Commit mesajları | İngilizce, Conventional Commits | Örn. `feat: add invoice search screen` *(öneri)* |

## 2. Dosya ve klasör adları

**Kural:** İngilizce, küçük harf, kelimeler arası tire (`-`). Boşluk, parantez ve Türkçe karakter (ç, ğ, ı, ö, ş, ü) kullanılmaz.

| Doğru | Yanlış | Neden |
|---|---|---|
| `01-integration-guide.md` | `Entegrasyon Rehberi.docx` | Boşluk, büyük harf ve Türkçe karakter yol sorunlarına yol açar |
| `01-invoice-list.png` | `Fatura Liste (son).png` | Parantez ve boşluk script ve CI araçlarını bozar |
| `screenshots/` | `Ekran Görüntüleri/` | Türkçe karakter ve boşluk işletim sistemleri arasında farklı davranır |

Gerekçe: Mac, Windows ve Linux arasında ve OneDrive üzerinde dosya adı sorunlarını önlemek.

## 3. Dosya formatları ve adlandırma kalıpları

| Tür | Format | Ad kalıbı | Konum |
|---|---|---|---|
| Ana rehber | Markdown (`.md`), UTF-8 | `NN-topic.md` | `DOC/` |
| Ekran görüntüsü | PNG | `NN-module-screen.png` | `DOC/screenshots/` |
| Arayüz test planı | Markdown (`.md`), UTF-8 | `NN-interface-test-plan.md` | `DOC/` |
| Arayüz ikonu / vektör görsel | SVG | `name.svg` | `UI/assets/` |
| Mimari karar kaydı (ADR) *(öneri)* | Markdown | `NNNN-decision-title.md` | `DOC/decisions/` |
| API sözleşmesi *(öneri, API varsa)* | OpenAPI 3.x, YAML | `openapi.yaml` | `DOC/api/` |
| Sürüm notları *(öneri)* | Markdown | `CHANGELOG.md` | Proje kökü |
| Akış diyagramı | Mermaid kod bloğu | — | İlgili `.md` içinde |

`NN` iki haneli sıra numarasıdır: `01`, `02`, … Yeni dosya eklenirken son numaraya bir eklenir.

Örnekler:
- `01-integration-guide.md`
- `03-screenshots.md`
- `04-interface-test-plan.md`
- `0001-database-selection.md`
- `01-invoice-list.png`
- `02-invoice-detail.png`
- `03-invoice-detail_dark.png` (koyu tema varyantı)

## 4. Ekran görüntüsü standardı

- **Format:** PNG. Fotoğraf değil, ekran yakalama kullanılır.
- **Genişlik:** En fazla 1600 px.
- **Dosya boyutu:** En fazla 1 MB. Aşılırsa sıkıştırılır veya kırpılır.
- **Renk profili:** sRGB.
- **Tema varyantları:** Açık tema dosyası eksiz kalır; koyu tema `_dark` soneki alır, örn. `01-invoice-list_dark.png`.
- **Dizin kaydı:** Her ekran görüntüsü `03-screenshots.md` içinde açıklanır (amaç, adımlar, alt metin).
- **Gizlilik:** TC kimlik, IBAN, müşteri adı, gerçek tutar ve e-posta adresi maskelenir. Maskeleme yapılmadan commit veya paylaşım yapılmaz.

## 5. Erişilebilirlik *(öneri)*

- Her ekran görüntüsü için Türkçe alt metin yazılır.
- Metin ve arka plan kontrastı en az 4.5:1 olmalıdır (WCAG AA).
- Renk tek başına anlam taşımaz; durum bilgisi metin veya ikonla da verilir.

## 6. Test kimlikleri

Arayüz test senaryoları `04-interface-test-plan.md` içinde tanımlanır. Her senaryo bir kimlik taşır:

- Kalıp: `<MODÜL>-<KONU>-<NN>`, örn. `WP-DT-01`
- Konu kısaltmaları: `DT` (tarih ve saat), `ST` (istasyon), `EV` (event atama / kaldırma), `CR` (oluşturma), `CM` (ortak kontroller)

## 7. Sürüm ve değişiklik kuralları

- Dokümantasyon değişikliği, ilgili kod değişikliğiyle aynı commit içinde yapılır.
- Her Markdown dosyasının başında `Son güncelleme: YYYY-AA-GG` satırı bulunur (ISO tarih biçimi).
- Kırıcı değişiklikler `CHANGELOG.md` içinde ayrıca belirtilir.

## 8. Git *(öneri, depo henüz oluşturulmadı)*

- Ana dal: `main`. Doğrudan `main` üzerinde geliştirme yapılmaz.
- Dal adları: `feature/short-description`, `fix/short-description`, `docs/short-description`.
- Gizli bilgiler (`.env`, anahtar dosyaları, şifreler) asla depoya eklenmez.
