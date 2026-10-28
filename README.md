# Klipo — Sınırsız pano geçmişi

Kopyaladığın her metni ve ekran görüntüsünü kaydeden, sade ve modern bir Windows uygulaması.
Kayıt sınırı yoktur, hiçbir şey kendiliğinden silinmez.

## Özellikler

- **Sınırsız geçmiş**: metinler, linkler ve ekran görüntüleri; aynı içerik tekrar kopyalanınca kopya oluşmaz, en üste taşınır
- **Arama**: metinlerde ve **görsellerin içindeki yazılarda** (Windows OCR, internetsiz, Türkçe destekli)
- **Sekmeler**: Tümü · Metin · Görsel · Link · Sabitli · Hazır
- **Tarih başlıkları**: Sabitlenenler · Bugün · Dün · Son 7 gün · Son 30 gün · Daha eski
- **Kaynak uygulama**: her kaydın hangi uygulamadan geldiği görünür; tıklayınca o uygulamaya göre filtreler
- **Akıllı tanıma**: link (tarayıcıda aç), renk kodu (renk örneği), kod parçası (eşit genişlikli yazı tipi)
- **Biçimli metin**: Word/web biçimlendirmesi korunur; istenirse düz metin olarak yapıştırılır
- **Hazır metinler**: imza, adres, sık kullanılan sorgular… adıyla kaydedilir
- **Önizleme ve düzenleme**: metni yapıştırmadan önce düzenle; görsel üzerine kalem, fosforlu kalem, ok, dikdörtgen,
  yazı ve numaralı adım ekle, kırp (orijinal korunur, düzenlenmiş hali yeni kayıt olur)
- **Metin dönüştürme**: büyük/küçük harf, JSON düzenle/sıkıştır, Base64, URL, boşluk temizle, satır sırala,
  tekrarları kaldır, Türkçe karakter çevir (önizlemede **Dönüştür ▾**)
- **Çoklu seçim**: birden çok metni seçip alt alta birleştirerek tek seferde yapıştır
- **Yapıştırma sırası**: seçilenleri `Ctrl+Q` ile sıraya al; her `Ctrl+V` bir sonrakini yapıştırır (form doldururken)
- **Ekrana iğneleme**: görüntüyü her zaman önde duran küçük bir pencere olarak bırak
- **Koruma**: sabitli kayıt ve hazır metinler silinmeden önce onay ister
- **Kurulum ve otomatik güncelleme**: yönetici izni gerekmez; yeni sürüm çıkınca bildirir, tek tıkla günceller

## Ekran görüntüsü (Print Screen)

1. **Print Screen**'e bas: imlecin bulunduğu ekran donar
2. Alanı sürükleyerek seç (sürüklemeden tıklarsan tüm ekran)
3. Araç çubuğu seçimin altında açılır, kalem hazırdır: çiz
4. **Önceki pencereye yapıştır** (`Enter`): Print Screen'den önce açık olan pencereye doğrudan yapıştırır
   · **Panoya kopyala** (`Ctrl+C`): sonra istediğin yere `Ctrl+V` ile yapıştırırsın · `Esc`: vazgeç

Araçlar: `1` kalem · `2` fosforlu kalem · `3` ok · `4` dikdörtgen · `5` yazı (tıkla, yaz, Enter) ·
`6` numaralı adım (her tıklama 1, 2, 3…) · `Ctrl+Z` geri al.

Seçimden sonra ayrıca:

- **Metni kopyala** (`T`): seçili alandaki yazıyı metin olarak kopyalar (seçilemeyen yazılar, hata pencereleri, videolar)
- **İğnele** (`P`): görüntüyü ekranın üstünde sabit bırakır. Sürükle: taşı · tekerlek: büyüt/küçült · çift tık veya `Esc`: kapat
- **Renk seç** (`R`, seçimden önce): büyüteçle bir noktaya tıkla, rengi `#hex` olarak kopyalar.
  Tepsi menüsünde **Ekrandan renk seç** olarak da var.

Seçimin dışına tıklayınca yeniden seçersin. Her ekran görüntüsü geçmişe de kaydedilir.
`Alt+PrtScn` ve `Win+PrtScn` Windows'un kendi işlevinde kalır.

## Kısayollar

| Kısayol | İşlem |
|---|---|
| `Ctrl+Shift+V` | Geçmişi aç / kapat (tepsi menüsünden değiştirilebilir) |
| Yazmaya başla | Ara |
| `↑` `↓` | Gezin |
| `Enter` veya tıklama | Önceki uygulamaya yapıştır |
| `Shift+Enter` | Düz metin olarak yapıştır |
| `Ctrl+Enter` | Yalnızca panoya kopyala |
| `Ctrl+1` … `Ctrl+9` | Numaralı kaydı doğrudan yapıştır |
| `Space` | Önizle (arama kutusu boşken) |
| `Ctrl+E` | Düzenle |
| `Ctrl+N` | Yeni hazır metin |
| `Ctrl+tık`, `Shift+↑↓` | Çoklu seçim |
| `Ctrl+Q` | Seçilenleri sırayla yapıştır (her `Ctrl+V` bir sonrakini) |
| `Ctrl+P` | Sabitle / sabitlemeyi kaldır |
| `Del` | Sil |
| `Tab` | Sekmeler arasında geç |
| `Esc` | Aramayı temizle → seçimi bırak → filtreyi kaldır → kapat |

Önizleme penceresinde: `Ctrl+Enter` yapıştır, `Ctrl+C` kopyala (görsel), `Ctrl+Z` geri al, `Ctrl+S` hazır metni kaydet, `Esc` kapat.

## Veriler

Her şey yerel olarak `%LOCALAPPDATA%\Klipo` içinde durur:

- `history.db`: kayıtlar (SQLite)
- `images\`, `thumbs\`: ekran görüntüleri ve önizlemeleri (PNG)
- `settings.json`, `error.log`

Parola yöneticilerinin "geçmişe kaydetme" işareti koyduğu içerikler kaydedilmez.

## Temizleme

Tepsi simgesine sağ tıkla (veya penceredeki **⋯**) → **Temizle**:

- **30 / 90 günden, 1 yıldan eski kayıtlar**: sabitliler ve hazır metinler korunur
- **Sabitlenmemiş tüm kayıtlar**: sabitliler ve hazır metinler korunur
- **Her şey (sabitliler dahil)**: geri alınamaz

Menüde toplam kayıt sayısı ve kapladığı alan görünür. Silmeden sonra veritabanı küçültülür, görsel dosyaları diskten kaldırılır.

## Derleme

.NET 8 SDK ve Windows 10 1809 veya üzeri gerekir.

```powershell
dotnet run                     # geliştirme
dotnet publish -c Release -r win-x64 --self-contained false `
  -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true -p:DebugType=none -o publish
```

`publish\Klipo.exe` tek dosyadır; çalıştırmak için .NET 8 Desktop Runtime yeterlidir.

## Kurulum ve güncelleme

`Klipo.exe` kurulu olmayan bir yerden açılınca kurmayı önerir: `%LOCALAPPDATA%\Programs\Klipo` içine kopyalanır,
Başlat menüsüne eklenir ve **Ayarlar → Uygulamalar**'dan kaldırılabilir. Yönetici izni gerekmez.

Güncellemeler GitHub Releases'tan (`mpalazli/klipo`) gelir. Yeni sürüm yayımlamak için `Klipo.csproj` içindeki
`<Version>`'ı artır, yayımla ve `Klipo.exe`'yi `v1.2.0` gibi etiketli bir release'e ekle:

```powershell
gh release create v1.2.0 publish\Klipo.exe --repo mpalazli/klipo --title "Klipo 1.2.0" --notes "Neler yeni…"
```

Klipo açılışta ve 6 saatte bir kontrol eder; yeni sürüm varsa bildirim gösterir, tıklayınca indirip yeniden başlar.
