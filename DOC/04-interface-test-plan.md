# Arayüz Test Planı

> Son güncelleme: 2026-11-18
> Durum: Taslak. Test konuları listelendi; ayrıntılı senaryolar sonraki adımda yazılacaktır.

## 1. Kapsam

Bu belge arayüz (UI) testlerinde kapsanacak konuları listeler. Her konu, `02-developer-directives.md` bölüm 6'daki kimlik kalıbıyla numaralandırılır.

> Kısaltma: **WP** — açılımı teyit edilecek. Bu belgede iş paketi (work package) olarak değerlendirilmiştir.

## 2. Test konuları

### 2.1 WP — Tarih ve saat bilgisini güncelleme (`WP-DT`)

- Geçerli tarih ve saat girilip kaydedilebildiğini doğrulama
- Geçersiz tarih ve saat (boş, hatalı format, geçmiş tarih) için hata mesajlarını doğrulama
- Bitiş tarihinin başlangıç tarihinden önce girilememesini doğrulama
- Güncellenen tarih ve saatin liste ve detay ekranlarında doğru görünmesini doğrulama
- Değişikliğin iptal edildiğinde kaydedilmediğini doğrulama

### 2.2 WP — İstasyon bilgisini güncelleme (`WP-ST`)

- Listeden geçerli bir istasyon seçilip kaydedilebildiğini doğrulama
- Pasif veya listede olmayan istasyonun seçilemediğini doğrulama
- İstasyon zorunlu alanken boş bırakıldığında kaydın engellendiğini doğrulama
- İstasyon değişikliğinin WP ile ilişkili verilere (event'ler dahil) doğru yansıdığını doğrulama
- Değişikliğin iptal edildiğinde kaydedilmediğini doğrulama

### 2.3 WP içinde event atama (assign) ve atamayı kaldırma (deassign) (`WP-EV`)

- Atanmamış bir event'in WP'ye atanabildiğini doğrulama
- Başka bir WP'ye atanmış event'in davranışını doğrulama (uyarı mı, engel mi)
- Atanmış bir event'in WP'den kaldırılabildiğini (deassign) doğrulama
- Kaldırılan event'in "atanmamış" olarak listelendiğini doğrulama
- Birden fazla event'in toplu atanması ve toplu kaldırılmasını doğrulama
- Atama ve kaldırma sonrası WP'nin toplam ve durum bilgilerinin güncellendiğini doğrulama
- Yetkisi olmayan kullanıcının atama ve kaldırma işlemi yapamadığını doğrulama

### 2.4 WP oluşturma (`WP-CR`)

- Zorunlu alanlar doldurulduğunda WP oluşturulabildiğini doğrulama
- Zorunlu alanlardan biri boşken kaydın engellendiğini ve hata mesajlarını doğrulama
- Alan sınırlarını doğrulama (karakter uzunluğu, sayısal aralık, tarih aralığı)
- Oluşturulan WP'nin listede göründüğünü ve benzersiz bir numara aldığını doğrulama
- Aynı bilgilerle mükerrer WP oluşturulmasının engellendiğini doğrulama
- Oluşturma ekranında iptal davranışını doğrulama
- Varsayılan değerlerin doğru atandığını doğrulama

### 2.5 Ortak kontroller (`WP-CM`)

- Başarılı işlemden sonra bildirim (mesaj veya uyarı) gösterilmesini doğrulama
- Sunucu hatasında anlaşılır bir hata mesajı gösterilmesini ve sayfanın bozulmamasını doğrulama
- Ağ kesintisinde yarım kalan işlemin veri bütünlüğünü bozmadığını doğrulama
- Form alanlarında klavye ile gezinme ve gönderme işlemini doğrulama (erişilebilirlik)
- Masaüstü, tablet ve mobil genişliklerde düzen kontrolü
- Açık ve koyu tema varsa her iki temada görünüm kontrolü

## 3. Açık sorular

- WP kısaltmasının açılımı nedir?
- Test ortamı hangisi ve test verisi nereden alınacak?
- Test aracı belirlenecek mi? (örn. Playwright, Cypress)
- Her işlem için yetki rolleri nelerdir?
- Event atama kurallarında "başka WP'ye atanmış event" için kesin iş kuralı nedir?

## 4. Test senaryosu kayıt formatı

Her senaryo aşağıdaki alanlarla yazılır:

| Alan | Açıklama |
|---|---|
| Kimlik | Örn. `WP-DT-01` |
| Konu | Kısa başlık |
| Ön koşul | Test öncesi gerekli durum ve veri |
| Adımlar | Numaralı işlem adımları |
| Beklenen sonuç | Adım adım beklenen davranış |
| Gerçekleşen sonuç | Test sırasında gözlenen |
| Durum | Geçti / Kaldı / Engellendi / Çalıştırılmadı |
