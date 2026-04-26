# Knight Online UI Editor (UIE) Kullanım Kılavuzu

**Versiyon:** v2.3.26.400  
**Geliştirici:** Kirasoftware (2016-2026)

---

## İçindekiler

1. [Giriş](#bölüm-1-giriş)
2. [UIE Nedir?](#bölüm-2-uie-nedir)
3. [Sistem Gereksinimleri](#bölüm-3-sistem-gereksinimleri)
4. [Kurulum](#bölüm-4-kurulum)
5. [Arayüz](#bölüm-5-arayüz)
6. [UIF Format](#bölüm-6-uif-format)
7. [UI Bileşenleri](#bölüm-7-ui-bileşenleri)
8. [Yeni UI Oluşturma](#bölüm-8-yeni-ui-oluşturma)
9. [Düzenleme](#bölüm-9-düzenleme)
10. [Animasyon](#bölüm-10-animasyon)
11. [Texture Yönetimi](#bölüm-11-texture-yönetimi)
12. [Kısayollar](#bölüm-12-kısayollar)
13. [İpuçları ve Teknikler](#bölüm-13-ipuçları-ve-teknikler)
14. [SSS (FAQ)](#bölüm-14-sss-faq)

---

## Bölüm 1: Giriş

Knight Online UI Editor (UIE), Knight Online oyunu için UI (Kullanıcı Arayüzü) dosyalarını oluşturmak, düzenlemek ve yönetmek için tasarlanmış profesyonel bir grafik editörüdür.

### Bu Kılavuz Hakkında

Bu dokümantasyon, UIE'nin tüm özelliklerini kapsamlı bir şekilde açıklamaktadır:

- UIE'nin temel özellikleri ve kullanım alanları
- Sistem gereksinimleri ve kurulum
- Arayüz tanıtımı ve navigasyon
- UI bileşenlerinin oluşturulması ve düzenlenmesi
- Animasyon sistemi
- Texture yönetimi
- İleri düzey teknikler ve ipuçları

---

## Bölüm 2: UIE Nedir?

UIE (UI Editor), Knight Online için UI tasarımı yapmanıza olanak tanıyan bir Windows masaüstü uygulamasıdır.

### Temel Özellikler

| Özellik | Açıklama |
|---------|----------|
| **Çoklu UI Bileşen Desteği** | Button, Image, String, Static, Edit, Progress, TrackBar, ScrollBar, Area, List, Tree, Flash |
| **Görsel Düzenleme** | Sürükle-bırak ile UI elemanlarını konumlandırma |
| **Hiyerarşi Görünümü** | Tüm UI elemanlarının ağaç yapısında görüntülenmesi |
| **Özellik Paneli** | Seçili elemanların tüm özelliklerini düzenleme |
| **Texture Yönetimi** | DX Texture formatında görselleri düzenleme |
| **Animasyon Sistemi** | UI elemanları için animasyon oluşturma |
| **Toplu İşlemler** | Birden fazla dosya üzerinde toplu değişiklik |

### UIF Formatı

UIE, `.UIF` uzantılı dosyalar kullanır. Bu dosyalar şu bilgileri içerir:

- UI elemanlarının pozisyonları ve boyutları
- Texture referansları ve UV koordinatları
- Font bilgileri ve metin içerikleri
- Olay işleyicileri (event handlers)
- Animasyon verileri

---

## Bölüm 3: Sistem Gereksinimleri

### Minimum Sistem Gereksinimleri

| Bileşen | Gereksinim |
|---------|------------|
| İşletim Sistemi | Windows XP / Vista / 7 / 8 / 10 / 11 |
| İşlemci | Intel Pentium 4 veya üzeri |
| RAM | 512 MB |
| Ekran Kartı | DirectX 9.0c uyumlu, 128 MB VRAM |
| Disk Alanı | 100 MB boş alan |
| Çözünürlük | 1024x768 veya üzeri |

### Önerilen Sistem Gereksinimleri

| Bileşen | Önerilen |
|---------|----------|
| İşletim Sistemi | Windows 10/11 64-bit |
| İşlemci | Intel Core i5 veya üzeri |
| RAM | 4 GB veya daha fazla |
| Ekran Kartı | DirectX 11 uyumlu, 1 GB VRAM |

### Desteklenen Dosya Formatları

| Format | Açıklama |
|--------|----------|
| .UIF | UI Editor dosya formatı |
| .DXT | DirectX Texture formatı |
| .BMP | Bitmap görsel formatı |
| .TGA | Truevision TGA formatı |

---

## Bölüm 4: Kurulum

### Kurulum Adımları

1. UIE kurulum dosyasını indirin
2. Kurulum dosyasını çalıştırın
3. Kurulum sihirbazını takip edin
4. Kurulum konumunu seçin
5. "Kur" butonuna tıklayın
6. UIE'yi başlatın

### İlk Yapılandırma

- **Base Path:** Knight Online veri dosyalarının bulunduğu klasörü seçin
- **Tema Ayarları:** Arayüz rengi ve görünüm tercihlerinizi belirleyin
- **Kısayol Tuşları:** İsterseniz kısayol tuşlarını özelleştirin

---

## Bölüm 5: Arayüz

### Pencere Düzeni

```
┌─────────────────────────────────────────────────────────┐
│ Menu Bar (Üst Menü)                                     │
├──────────┬──────────────────────────┬──────────────────┤
│          │                          │                  │
│Hierarchy │       Canvas             │   Property View  │
│  View    │    (Çalışma Alanı)       │  (Özellik Paneli│
│ (Sol)    │                          │    (Sağ)         │
│          │                          │                  │
├──────────┴──────────────────────────┴──────────────────┤
│ Status Bar (Durum Çubuğu)                              │
└─────────────────────────────────────────────────────────┘
```

### Hiyerarşi Görünümü (Sol Panel)

- UI elemanlarının hiyerarşik ilişkilerini görüntüler
- Elemanları sürükleyerek yeniden düzenleyebilir
- Elemanları seçme ve vurgulama imkanı
- Context menü ile hızlı işlemlere erişim

### Canvas (Orta Panel)

İki modda çalışır:

- **Preview Mode:** UI'yi son haliyle görüntüler
- **Edit Mode:** UI elemanlarını seçme, taşıma ve boyutlandırma

### Özellik Paneli (Sağ Panel)

- **Base Properties:** ID, pozisyon, boyut
- **Appearance:** Renk, stil, görünürlük
- **Behavior:** Olaylar, animasyonlar
- **Type-Specific:** Eleman türüne göre değişen özellikler

---

## Bölüm 6: UIF Format

### Dosya Yapısı

UIF dosyaları şu bölümlerden oluşur:

- **Header:** Dosya formatı ve versiyon bilgisi
- **UI Tree:** Tüm UI elemanlarının hiyerarşik yapısı
- **Properties:** Her elemanın özellikleri
- **Resources:** Texture ve font referansları

### Kaydetme ve Yükleme

| Kısayol | İşlev |
|---------|-------|
| Ctrl+S | Kaydet |
| Ctrl+O | Dosya aç |
| Ctrl+Shift+S | Farklı kaydet |

---

## Bölüm 7: UI Bileşenleri

### Temel Bileşenler

| Bileşen | Açıklama |
|---------|----------|
| **Image** | Texture görüntüleme |
| **Button** | Tıklanabilir butonlar (4 durum) |
| **String** | Metin görüntüleme |
| **Static** | Arka plan + metin kombinasyonu |
| **Edit** | Kullanıcı girişi için metin kutusu |
| **Progress** | İlerleme çubuğu |
| **TrackBar** | Değer seçimi |
| **ScrollBar** | İçerik kaydırma |
| **Area** | Tıklanabilir boş alan |
| **List** | Listedeki string öğeleri |
| **Tree** | Hiyerarşik liste yapısı |
| **Flash** | Adobe Flash içeriği |

---

## Bölüm 8: Yeni UI Oluşturma

### UI Ekleme Temelleri

1. Eklemek istediğiniz eleman türünü seçin
2. Canvas üzerinde konumlandırın
3. Özellikler panelinde ayarları yapın

### Button Oluşturma

1. `Insert > Button` seçin
2. Texture seçin (4 durum için)
3. Her durum için UV koordinatlarını ayarlayın
4. Region'ı düzenleyin

---

## Bölüm 9: Düzenleme

### Seçme İşlemleri

- **Tek seçim:** Eleman üzerine tıklayın
- **Çoklu seçim:** Ctrl tuşunu basılı tutarak tıklayın
- **Alan seçimi:** Canvas üzerinde sürükleme yapın

### Taşıma

| Kısayol | İşlev |
|---------|-------|
| Ok tuşları | Piksel piksel hareket |
| Shift+Ok | 10 piksel hareket |

---

## Bölüm 10: Animasyon

### Animasyon Dialogu

`Tools > Animate` seçerek animasyon oluşturabilirsiniz.

### Desteklenen Animasyon Türleri

- **Position:** X,Y koordinat değişimi
- **Scale:** Boyut değişimi
- **Alpha:** Şeffaflık değişimi
- **Color:** Renk geçişleri

---

## Bölüm 11: Texture Yönetimi

### Desteklenen Formatlar

| Format | Uzantı |
|--------|--------|
| DXT | .dxt |
| BMP | .bmp |
| TGA | .tga |

### UV Koordinatları

UV koordinatları 0.0 ile 1.0 arasında değerler alır:

- **U (Yatay):** Soldan sağa 0.0 - 1.0
- **V (Dikey):** Yukarıdan aşağıya 0.0 - 1.0

---

## Bölüm 12: Kısayollar

### Genel Kısayollar

| Kısayol | İşlev |
|---------|-------|
| Ctrl+N | Yeni dosya |
| Ctrl+O | Dosya aç |
| Ctrl+S | Kaydet |
| Ctrl+Z | Geri al |
| Delete | Sil |
| F5 | Önizleme modu |
| F6 | Düzenleme modu |

---

## Bölüm 13: İpuçları ve Teknikler

### Verimlilik İpuçları

- Base Path'i doğru ayarlayın
- Sık kaydedin (Ctrl+S)
- Hiyerarşiyi aktif kullanın
- Klavye kısayollarını öğrenin
- Hassas hizalama için grid kullanın

### Texture Atlas Kullanımı

Texture atlas avantajları:

- Daha az dosya sayısı
- Daha hızlı yükleme
- Daha az bellek kullanımı

---

## Bölüm 14: SSS (FAQ)

### UIE hangi işletim sistemlerinde çalışır?

Windows XP ve üzeri tüm Windows sürümlerinde çalışır. Windows 10 ve 11'de en iyi performansı sağlar.

### Texture boyutu sınırı var mı?

Texture boyutu, ekran kartınızın desteklediği maksimum çözünürlükle sınırlıdır. Performans için 1024x1024 ve altı önerilir.

### İletişim

- **Web Sitesi:** https://kiraguard.com
- **Forum:** https://forum.kiraguard.com
- **Discord:** https://discord.com/invite/grYZDXXSEy
- **E-posta:** denizsukelebek@proton.me

---
------------------------------------------------------------------------------------------------------------------------
# KO - 27.04.2026 2026 - UI Editor Güncelleme Notları

## Bug Düzeltmeleri
- **UI Elemanı Silme Crash'i Düzeltildi**
  Bir butonun altındaki image elemanı (img_l, img_r vb.) silindiğinde uygulama crash ediyordu. Bu sorun giderildi.

- **Alt Eleman Referans Bellek Sorunu Giderildi**
  UI elemanları silindikten sonra bellek yönetimi düzeltildi. Artık crash oluşmuyor.

- **Render Sistem Koruması Güçlendirildi**
  UI elemanları render edilirken oluşabilecek hatalara karşı ek kontroller eklendi.

- **TexViewer Derleme Sorunu Giderildi**
  TexViewer Debug modunda derlenememe sorunu düzeltildi.
  
------------------------------------------------------------------------------------------------------------------------

**© Knight Online UI Editor (UIE) Kullanım Kılavuzu**  
*Versiyon: v2.3.26.400 | Kirasoftware (2016-2026)*
