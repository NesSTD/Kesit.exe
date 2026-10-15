<div align="center">

<img src="docs/icon.png" width="72" alt="Kesit">

# Kesit

**Windows için hafif ve hızlı ekran görüntüsü aracı — çizim, OCR ve yapay zekâ ile arka plan kaldırma.**

![Platform](https://img.shields.io/badge/platform-Windows%2010%20%7C%2011-0078D6)
![Dil](https://img.shields.io/badge/C%2B%2B-Win32-00599C)
![Boyut](https://img.shields.io/badge/exe-~300%20KB-success)
![Lisans](https://img.shields.io/badge/lisans-MIT-yellow)

[İndir](../../releases/latest) · [Özellikler](#özellikler) · [Kısayollar](#kısayollar) · [Derleme](#derleme) · [English](#english)

</div>

---

`PrtSc`'ye basın, alanı seçin, üzerine çizin; ardından kopyalayın, kaydedin, **içindeki yazıyı okuyun** ya da
**arka planını kaldırın**. Aynı işlemleri Dosya Gezgini'nde herhangi bir resme **sağ tıklayarak** da yapabilirsiniz.
Her şey bilgisayarınızda çalışır; hiçbir görüntü internete gönderilmez.

## Özellikler

### 📸 Ekran görüntüsü
- **PrtSc** ile anında yakalama (PrtSc başka bir uygulamadaysa otomatik olarak **Ctrl+Shift+X**)
- Sürükleyerek alan seçme, taşıma ve 8 tutamaçla boyutlandırma; seçim boyutu canlı gösterilir
- Tek tıkla tüm monitörü, `Ctrl+A` ile tüm ekranı seçme
- Çoklu monitör ve yüksek DPI desteği

### ✏️ Çizim araçları
- Kalem, çizgi, ok, dikdörtgen, işaretleyici (fosforlu kalem) ve metin
- Renk seçimi, fare tekerleğiyle kalınlık / yazı boyutu, sınırsız geri alma

### 🔤 Metni oku (OCR)
- Seçilen alandaki ya da resimdeki yazıyı okur, **panoya kopyalar** ve düzenlenebilir bir pencerede gösterir
- Windows'un yerleşik OCR motorunu kullanır; Türkçe dahil yüklü tüm dilleri destekler
- **Piksel doğrulamalı düzeltme:** Windows OCR'ın dil tahminiyle karıştırdığı karakterler, resimdeki gerçek şekle
  bakılarak yeniden belirlenir:
  - **I / İ / ı / i** — nokta gerçekten var mı?
  - **O / 0** ve **I / 1** — lisans anahtarı, seri numarası gibi kodlarda
  - Büyük/küçük harf (`s/S`, `c/C`…) ve tamamen büyük harfli kelimeler
- Küçük yazılar otomatik olarak büyütülüp yeniden okunur

> Kendi test setimizde (7 yazı tipi, 4 boyut, açık/koyu tema) satırın birebir doğru okunma oranı
> Windows OCR'da **%50,7** iken Kesit'te **%88,9**; karakter doğruluğu **%95,96 → %99,22**.

### ✂️ Arka planı kaldır
- Tek tıkla nesneyi arka plandan ayırır ([U²-Net](https://github.com/xuebinqin/U-2-Net) yapay zekâ modeli)
- Sonuç saydam PNG olarak kopyalanır ya da kaydedilir
- Tamamen çevrimdışı çalışır

### 🖱️ Sağ tık menüsü
Dosya Gezgini'nde herhangi bir resme sağ tıklayın:
- **Metni oku (Kesit)**
- **Arka planı kaldır (Kesit)** — sonuç, orijinalin yanına `resim (arka plansız).png` olarak kaydedilir

### 🪶 Hafif ve hızlı
- Tepside bekleyen `Kesit.exe` yalnızca **~300 KB**; boştayken Görev Yöneticisi'nde ~2 MB bellek
  (Lightshot'ta ~18 MB)
- OCR ve arka plan kaldırma, ihtiyaç anında açılıp iş bitince kapanan ayrı bir süreçte çalışır;
  yapay zekâ kütüphaneleri boşta hiç bellek kullanmaz
- Her işlemden sonra kullanılmayan bellek Windows'a geri verilir

### ⚙️ Diğer
- PNG / JPG / BMP olarak kaydetme (son kullanılan klasör hatırlanır)
- **Bilgisayar açılınca başlat** — kurulumda sorulur; tepsi menüsünden ya da Görev Yöneticisi → Başlangıç
  sekmesinden açılıp kapatılabilir
- Yönetici izni gerektirmeyen kurulum ve iz bırakmayan kaldırma

## Kurulum

1. [Releases](../../releases/latest) sayfasından **`Kesit-Setup-1.2.0.exe`** dosyasını indirin.
2. Çalıştırın ve sihirbazı takip edin (yönetici izni gerekmez).
3. Kurulum bitince Kesit tepsiye yerleşir — **PrtSc**'ye basın.

Kaldırmak için: **Ayarlar → Uygulamalar → Kesit → Kaldır**.

> Kurulum dosyası dijital olarak imzalı olmadığı için Windows SmartScreen "bilinmeyen yayıncı" uyarısı
> gösterebilir: **Ek bilgi → Yine de çalıştır**.

## Kısayollar

| Tuş | İşlem |
| --- | --- |
| `PrtSc` | Ekran görüntüsü al |
| `Ctrl+C` / `Enter` / çift tık | Panoya kopyala ve kapat |
| `Ctrl+S` | Kaydet |
| `Ctrl+T` | Metni oku (OCR) |
| `Ctrl+B` | Arka planı kaldır |
| `Ctrl+Z` | Geri al |
| `Ctrl+A` | Tüm ekranı seç |
| Fare tekerleği | Kalınlık / yazı boyutu |
| `Esc` / `Ctrl+X` / sağ tık | Kapat |

## Sık sorulan sorular

**PrtSc'ye basınca bir şey olmuyor.**
Windows'ta *Ayarlar → Erişilebilirlik → Klavye → "Ekran alıntısı için PrtScn düğmesini kullan"* açıksa
PrtSc'yi Windows kullanır; bu ayarı kapatın. Lightshot gibi başka bir araç PrtSc'yi tutuyorsa Kesit
otomatik olarak `Ctrl+Shift+X` kısayoluna geçer.

**OCR Türkçe karakterleri okumuyor.**
OCR, Windows'ta yüklü dil paketlerini kullanır. *Ayarlar → Saat ve dil → Dil* bölümünden Türkçe dil
paketinin yüklü olduğundan emin olun.

**Sağ tık menüsünde göremiyorum.**
Windows 11'de girişler *"Daha fazla seçenek göster"* altındadır. Menüyü tepsi simgesindeki
**Resimlerin sağ tık menüsünde göster** seçeneğiyle açıp kapatabilirsiniz.

## Derleme

Gereksinimler: Visual Studio 2019 veya üstü (*C++ ile masaüstü geliştirme*) ve Windows 10 SDK.

```bat
build.bat
```

`build.bat`, arka plan kaldırma için gereken `onnxruntime.dll` ve `models\u2netp.onnx` dosyalarını resmi
kaynaklarından indirir ve SHA-256 ile doğrular. Belirli bir Windows SDK için önce
`set WINSDK_VERSION=10.0.19041.0` çalıştırın.

Kurulum dosyasını (`dist\Kesit-Setup-<sürüm>.exe`) oluşturmak için
[Inno Setup 6](https://jrsoftware.org/isinfo.php) gerekir:

```bat
build.bat
installer.bat
```

### Proje yapısı

| Dosya | İçerik |
| --- | --- |
| `src/main.cpp` | Tepsi uygulaması, kısayol tuşu, başlangıç ve sağ tık menüsü kaydı |
| `src/overlay.cpp` | Ekran yakalama, alan seçimi, çizim araçları, araç çubuğu |
| `src/ocr.cpp` | Windows OCR çağrısı ve uyarlamalı ikinci okuma |
| `src/ocrfix.cpp` | Piksel doğrulamalı karakter düzeltme (I/İ/ı/i, O/0, I/1, büyük/küçük harf) |
| `src/bgremove.cpp` | U²-Net ile arka plan kaldırma (ONNX Runtime) |
| `src/imagetools.cpp` | Resim dosyaları, sonuç penceresi, sağ tık komutları |
| `installer/Kesit.iss` | Inno Setup kurulum betiği |

## Üçüncü taraf bileşenler

- [ONNX Runtime](https://github.com/microsoft/onnxruntime) 1.20.1 — MIT lisansı
- [U²-Net](https://github.com/xuebinqin/U-2-Net) `u2netp` modeli ([rembg](https://github.com/danielgatis/rembg) dağıtımı) — Apache 2.0

Ayrıntılar: [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt)

## Lisans

[MIT](LICENSE)

---

## English

**Kesit** is a tiny, fast screenshot tool for Windows. Press `PrtSc`, select a region, annotate it, then copy or
save it — or **extract its text (OCR)** or **remove its background**. Both actions are also available from the
right-click menu of any image file in File Explorer. Everything runs locally; nothing is uploaded.

- **Capture:** `PrtSc` hotkey (falls back to `Ctrl+Shift+X`), resizable selection, multi-monitor and high-DPI aware
- **Annotate:** pen, line, arrow, rectangle, highlighter, text, color picker, undo
- **OCR:** built-in Windows OCR plus a pixel-verified correction layer that fixes characters the OCR guesses from
  language statistics — `I/İ/ı/i`, `O/0`, `I/1` and letter case. On our test set (7 fonts × 4 sizes, light/dark)
  exact-line accuracy goes from 50.7% to 88.9%.
- **Remove background:** offline U²-Net model, copy or save as transparent PNG
- **Explorer integration:** *Read text* and *Remove background* on every image's context menu
- **Lightweight:** ~300 KB tray executable, ~2 MB idle working set; OCR and AI run in a short-lived worker process
- **Installer:** per-user setup (no admin), optional start with Windows, clean uninstall

Download the installer from [Releases](../../releases/latest). Build with `build.bat` (Visual Studio 2019+) and
`installer.bat` (Inno Setup 6). Licensed under [MIT](LICENSE).
