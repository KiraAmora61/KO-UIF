# Knight Online UI Editor (UIE) Kullanım Kılavuzu

**Kapsamlı Kullanım Kılavuzu**

Versiyon 2.3.26.400 | Kirasoftware (2016-2026)

---

## İçindekiler

1. [Başlık ve Tanıtım](#1-başlık-ve-tanıtım)
2. [UIE Nedir?](#2-uie-nedir)
3. [Sistem Gereksinimleri](#3-sistem-gereksinimleri)
4. [Kurulum ve Çalıştırma](#4-kurulum-ve-çalıştırma)
5. [Arayüz Tanıtımı](#5-arayüz-tanıtımı)
6. [UIF Dosya Formatı](#6-uif-dosya-formatı)
7. [UI Bileşen Türleri](#7-ui-bileşen-türleri)
8. [Yeni UI Oluşturma](#8-yeni-ui-oluşturma)
9. [Mevcut UIF Düzenleme](#9-mevcut-uif-düzenleme)
10. [Animasyon Sistemi](#10-animasyon-sistemi)
11. [Texture/Doku Yönetimi](#11-texturedoku-yönetimi)
12. [Klavye Kısayolları](#12-klavye-kısayolları)
13. [İpuçları ve Püf Noktaları](#13-ipuçları-ve-püf-noktaları)
14. [Sıkça Sorulan Sorular](#14-sıkça-sorulan-sorular-faq)

---

## 1. Başlık ve Tanıtım

Bu dokümantasyon, Knight Online için UI (Kullanıcı Arayüzü) dosyalarını oluşturmak, düzenlemek ve yönetmek amacıyla geliştirilen UIE editörünün kapsamlı kullanım kılavuzudur.

### Versiyon Bilgileri

| Özellik | Değer |
|---------|-------|
| Program Adı | Knight Online UI Editor (UIE) |
| Versiyon | v2.3.26.400 |
| Geliştirici | Kirasoftware |
| Geliştirme Dönemi | 2016-2026 |
| Platform | MFC + Direct3D 9, Windows |
| Çıktı Dizini | [`build/x64-Release/UIE.exe`](build/x64-Release/UIE.exe) |

> **Not:** Bu dokümantasyon kaynak kod içermemektedir. Sadece programın kullanımı hakkında bilgi sağlamaktadır.

---

## 2. UIE Nedir?

UIE (UI Editor), Knight Online oyununun kullanıcı arayüzü dosyalarını (.uif) oluşturmak ve düzenlemek için özel olarak tasarlanmış bir editördür.

### Temel Özellikler

- **Görsel Arayüz Düzenleme:** Sürükle-bırak yöntemiyle UI bileşenlerini yerleştirme
- **18 Farklı Bileşen Türü:** Button, görsel, metin, progress bar ve daha fazlası
- **Animasyon Desteği:** Frame bazlı animasyon sistemi
- **Texture Yönetimi:** DX Texture (.dxt) dosya formatı desteği
- **Çoklu Versiyon Desteği:** 1068, 1264, 1298, 2062, CURR, HERO
- **Görsel Önizleme:** Direct3D 9 tabanlı gerçek zamanlı önizleme
- **Toplu İşlemler:** Batch tool ile toplu düzenleme imkanı

> UIE, Knight Online'un ikon, buton, panel ve diğer arayüz öğelerini profesyonel bir ortamda oluşturmanızı sağlar.

---

## 3. Sistem Gereksinimleri

### Minimum Gereksinimler

| Bileşen | Minimum |
|---------|---------|
| İşletim Sistemi | Windows 7 (64-bit) |
| İşlemci | Intel Core i3 veya eşdeğeri |
| RAM | 4 GB |
| Ekran Kartı | DirectX 9 destekli (1 GB VRAM) |
| Disk Alanı | 500 MB boş alan |
| Çözünürlük | 1280x720 |

### Önerilen Gereksinimler

| Bileşen | Önerilen |
|---------|----------|
| İşletim Sistemi | Windows 10/11 (64-bit) |
| İşlemci | Intel Core i5/i7 veya AMD Ryzen |
| RAM | 8 GB veya daha fazla |
| Ekran Kartı | DirectX 11 destekli (2 GB VRAM) |
| Disk Alanı | 1 GB boş alan |
| Çözünürlük | 1920x1080 veya daha yüksek |

> **Not:** UIE çalışması için DirectX 9 Runtime bileşenlerinin sisteminizde yüklü olması gerekmektedir.

---

## 4. Kurulum ve Çalıştırma

### Adım 1: Programı Açma

- Program çıktısı: [`build/x64-Release/UIE.exe`](build/x64-Release/UIE.exe)
- Bu dosyayı çift tıklayarak veya kısayol oluşturarak çalıştırabilirsiniz

### Adım 2: Yeni Proje Oluşturma

- Menü: **File > New** (Ctrl+N)
- Karşınıza gelen pencerede versiyon seçimi yapın
- Versiyonlar: 1068, 1264, 1298, 2062, CURR, HERO

### Adım 3: Dosya Açma

- Menü: **File > Open** (Ctrl+O)
- Dosya türü: **.uif** (UI Interface File)
- Mevcut bir UI dosyasını seçin ve açın

### Adım 4: Proje Kaydetme

- Menü: **File > Save** (Ctrl+S)
- Farklı kaydet: **File > Save As**
- Dosya uzantısı otomatik olarak .uif olarak belirlenir

> **Kurulum İpuçları:** Eğer program çalışmıyorsa, DirectX 9 Runtime'ın yüklü olduğundan emin olun. Windows Update üzerinden veya Microsoft'un web sitesinden indirebilirsiniz.

---

## 5. Arayüz Tanıtımı

### 5.1 Menü Yapısı

#### File Menüsü

| Seçenek | Açıklama | Kısayol |
|---------|----------|---------|
| New | Yeni proje oluştur | Ctrl+N |
| Open | Mevcut dosya aç | Ctrl+O |
| Save | Proje kaydet | Ctrl+S |
| Save As | Farklı isimle kaydet | Ctrl+Shift+S |
| Close | Proje kapat | - |

#### Edit Menüsü

| Seçenek | Açıklama | Kısayol |
|---------|----------|---------|
| Undo | Son işlemi geri al | Ctrl+Z |
| Cut | Kes | Ctrl+X |
| Copy | Kopyala | Ctrl+C |
| Paste | Yapıştır | Ctrl+V |
| Delete | Sil | Delete |
| Select All | Tümünü seç | Ctrl+A |
| Move | Taşı | - |

#### View Menüsü

| Seçenek | Açıklama | Kısayol |
|---------|----------|---------|
| Zoom In | Yakınlaştır | Ctrl++ |
| Zoom Out | Uzaklaştır | Ctrl+- |
| Grid Toggle | Grid aç/kapa | Ctrl+G |
| Snap to Grid | Grid'e yasla | - |

#### Insert Menüsü

18 farklı UI bileşeni bu menüden eklenebilir:

- Button, Image, String, Static
- Progress, TrackBar, ScrollBar
- Edit, Area, Tooltip
- List, Tree, TreeItem
- IconSlot, Flash
- BaseEx, Board

#### Option Menüsü

| Seçenek | Açıklama |
|---------|----------|
| Grid Size | Grid boyutunu ayarla |
| Snap Settings | Yaslama ayarları |

#### Batch Tool Menüsü

Toplu işlemler için kullanılır. Büyük projelerde zaman tasarrufu sağlar.

### 5.2 Panel/Sistem

#### HierarchyView (Hiyerarşi Görünümü)

> Sol tarafta bulunan ağaç yapısında tüm UI bileşenlerini gösterir. Bileşenler arasındaki parent-child ilişkisini yönetmenizi sağlar.

#### PropertyView (Özellik Görünümü)

> Sağ tarafta bulunan panel, seçili bileşenin tüm özelliklerini düzenlemenize olanak tanır. Position, Size, Color, Font gibi ayarlar buradan yapılır.

#### TexViewer (Doku Görüntüleyici)

> Ayrı bir modül olarak texture'ları görüntülemek ve yönetmek için kullanılır. [`build/x64-Release/TexViewer.exe`](build/x64-Release/TexViewer.exe) olarak da çalıştırılabilir.

### 5.3 Dialog Pencereleri

| Dialog | Açıklama |
|--------|----------|
| DlgAnimate | Animasyon düzenleme (frame bazlı) |
| DlgBar | Bar/ilerleme çubuğu düzenleme |
| DlgChangeImage | Görsel değiştirme |
| DlgReplace | Toplu bul-değiştir |
| DlgTexture | Doku yönetimi |
| DlgUnusedFileList | Kullanılmayan dosyaların listesi |

---

## 6. UIF Dosya Formatı

### 6.1 Dosya Formatı Hakkında

UIF (UI Interface File), Knight Online'un kullanıcı arayüzü dosyalarının kaydedildiği binary formattır. Bu format, UI bileşenlerinin tüm özelliklerini, pozisyonlarını, texture referanslarını ve animasyon verilerini içerir.

### 6.2 Desteklenen Versiyonlar

| Versiyon | Kullanım Alanı | Not |
|----------|---------------|-----|
| 1068 | Eski oyun versiyonu | Geriye dönük uyumluluk |
| 1264 | Orta dönem versiyon | Geçiş dönemi |
| 1298 | Güncel kullanım | Yaygın olarak kullanılır |
| 2062 | Yeni versiyon | Gelişmiş özellikler |
| CURR | Mevcut versiyon | En güncel format |
| HERO | Hero sınıfı | Özel karakterler için |

> **Önemli:** Farklı versiyonlar arasında geçiş yaparken bazı özelliklerin uyumsuz olabileceğini unutmayın.

### 6.3 .dxt Dosya Formatı

DX Texture formatı, UI'de kullanılan görsellerin saklandığı formattır. Bu format, DirectX 9 ile uyumlu sıkıştırılmış texture'ları içerir.

> Texture dosyaları genellikle .dxt uzantısıyla kaydedilir ve UIF dosyaları içinde referans olarak gösterilir.

---

## 7. UI Bileşen Türleri

UIE'de toplam **18 farklı UI bileşen türü** bulunmaktadır. Her bileşenin kendine özgü özellikleri ve kullanım alanları vardır.

### 7.1 Temel Bileşenler

#### 1. Button (Buton)

> Tıklanabilir buton bileşenidir. Kullanıcı etkileşiminin temel öğesidir. Normal, Hover, Click ve Disable olmak üzere 4 durum destekler.

- Tıklanabilir etkileşim sağlar
- 4 farklı durum gösterimi
- Event/Mesaj bağlama desteği

#### 2. Image (Görsel)

> Statik veya animasyonlu görsel gösterimi için kullanılır.

- Texture referansı gösterebilir
- Opacity ayarı yapılabilir
- Animasyon desteği

#### 3. String (Metin)

> Metin içeriği görüntülemek için kullanılan bileşendir.

- Font ayarları (boyut, stil, renk)
- Metin hizalama (sol, orta, sağ)
- Çoklu dil desteği

#### 4. Static (Statik)

> Değiştirilemeyen statik görsel öğeler için kullanılır.

- Arka plan görselleri
- Dekoratif öğeler
- Statik ikonlar

### 7.2 İlerleme ve Kaydırma Bileşenleri

#### 5. Progress (İlerleme Çubuğu)

> HP, MP, EXP gibi değerlerin görsel olarak gösterimi için kullanılır.

- Minimum ve maksimum değer
- Dolgu yüzdesi
- Animasyonlu dolgu

#### 6. TrackBar (Kaydırma Çubuğu)

> Ses seviyesi, parlaklık gibi sürekli değerleri ayarlamak için kullanılır.

- Min/max aralığı belirleme
- Adım değeri ayarı
- Görsel tutamak (handle)

#### 7. ScrollBar (Kaydırma Çubuğu)

> İçerik kaydırma için kullanılan dikey veya yatay çubuktur.

- Dikey veya yatay yönelim
- Kaydırma adımı
- Otomatik görünürlük

### 7.3 Giriş Bileşenleri

#### 8. Edit (Metin Giriş Alanı)

> Kullanıcıdan metin girişi almak için kullanılan bileşendir.

- Karakter sınırı belirleme
- Placeholder metni
- Password mode desteği

#### 9. Area (Alan Container)

> Diğer bileşenleri gruplandırmak için kullanılan container bileşenidir.

- Child bileşen barındırma
- Arka plan görseli
- Padding/margin ayarları

### 7.4 Bilgi ve Gezinme Bileşenleri

#### 10. Tooltip (Bilgi Baloncuğu)

> Bir öğe üzerine gelindiğinde gösterilen bilgi penceresidir.

- Gecikme süresi ayarı
- Pozisyon belirleme
- Rich text desteği

#### 11. List (Liste Görünümü)

> Çoklu satır veri göstermek için kullanılan bileşendir.

- Sütun desteği
- Satır seçimi
- Otomatik kaydırma

#### 12. Tree (Ağaç Görünüm)

> Hiyerarşik veri yapılarını göstermek için kullanılır.

- Collapsible dallanma
- Ağaç ikonları
- Çoklu seçim

#### 13. TreeItem (Ağaç Öğesi)

> Tree bileşeninin tek bir öğesini temsil eder.

- Alt öğe barındırma
- İkon gösterme
- Özel görünüm

### 7.5 Özel Bileşenler

#### 14. IconSlot (İkon Yuvası)

> Eşya, yetenek veya karakter ikonları için özel yuva bileşenidir.

- Slot boyutu ayarı
- İkon çerçevesi
- Doluluk durumu

#### 15. Flash

> Adobe Flash animasyonları embed etmek için kullanılır.

- SWF dosya desteği
- Kontrol butonları
- Parametre geçirme

#### 16. BaseEx (Genişletilmiş Taban)

> Özel bileşenler için temel sınıf olarak kullanılır.

- Genişletilebilir yapı
- Özel render
- Plugin desteği

#### 17. Board (Pencere Paneli)

> Başlık çubuğu ve kapatma butonu içeren pencere bileşenidir.

- Sürüklenebilir pencere
- Başlık çubuğu
- Minimize/maximize

### 7.6 Bileşen Durumları

| Durum | Açıklama |
|-------|----------|
| Normal | Bileşenin varsayılan görünümü |
| Hover | Fare üzerine gelindiğinde |
| Click | Tıklandığında |
| Disable | Pasif/engelli durum |

---

## 8. Yeni UI Oluşturma

### Adım Adım Yeni UI Projesi Oluşturma

#### 1. Adım: Yeni Proje Başlatma

> **File > New** veya **Ctrl+N** tuşlarına basın. Açılan pencerede kullanmak istediğiniz versiyonu seçin.

#### 2. Adım: Versiyon Seçimi

> Uyumlu bir versiyon seçin (önerilen: CURR veya 1298). Versiyon seçimi ileride sorunlara yol açabilir, dikkatli olun.

#### 3. Adım: Board (Pencere) Eklenmesi

> **Insert > Board** seçerek ana pencereyi ekleyin. Board, tüm diğer bileşenlerin parent'ı olacaktır.

#### 4. Adım: Boyut ve Pozisyon Ayarlama

> PropertyView panelinden:
> - Position X, Y ayarları
> - Size Width, Height ayarları

#### 5. Adım: Bileşen Ekleme

> Insert menüsünden ihtiyacınız olan bileşenleri ekleyin. Her bileşeni Board'ın içine sürükleyerek yerleştirin.

#### 6. Adım: Özellik Düzenleme

> Her bileşeni seçip PropertyView'dan özelliklerini düzenleyin:
> - Position (X, Y)
> - Size (Width, Height)
> - Color (RGBA)
> - Font ayarları
> - Text Alignment

#### 7. Adım: Kaydetme

> **File > Save** veya **Ctrl+S** ile projenizi kaydedin. Dosya .uif uzantısıyla kaydedilecektir.

> **İpuçları:** Grid özelliğini açmak **Ctrl+G** tuşuyla kolaylaştırır. Bileşenleri grid noktalarına yaslayarak düzenli görünüm sağlayabilirsiniz.

---

## 9. Mevcut UIF Düzenleme

### 9.1 Dosya Açma

1. **Ctrl+O** ile dosya aç dialogunu açın
2. Açmak istediğiniz .uif dosyasını seçin
3. Dosya HierarchyView'da yüklenecektir

### 9.2 Bileşen Seçme ve Düzenleme

- **Tek seçim:** Bileşene tıklayın
- **Çoklu seçim:** Ctrl tuşu basılıyken tıklayın
- **Alan seçimi:** Fare ile sürükleme yapın

### 9.3 Özellik Düzenleme

> PropertyView paneli şu özellikleri düzenlemenizi sağlar:

| Özellik | Açıklama |
|---------|----------|
| Position X/Y | Bileşenin ekrandaki konumu |
| Width/Height | Bileşenin boyutları |
| Color | RGBA renk değeri |
| Opacity | Saydamlık oranı (0-100) |
| Font | Yazı tipi, boyutu, stili |
| Text Alignment | Metin hizalama |
| Event/Mesaj | Olay bağlama |

### 9.4 Toplu Değişiklik

> DlgReplace dialogu ile toplu bul-değiştir işlemi yapabilirsiniz. Bu, büyük projelerde zaman tasarrufu sağlar.

1. DlgReplace penceresini açın
2. Değiştirmek istediğiniz değeri girin
3. Yeni değeri belirleyin
4. Uygula butonuna tıklayın

### 9.5 Kopyalama ve Yapıştırma

> Bileşenleri **Ctrl+C** ile kopyalayıp **Ctrl+V** ile yapıştırabilirsiniz. Bu, benzer bileşenleri hızlıca oluşturmanızı sağlar.

---

## 10. Animasyon Sistemi

### 10.1 DlgAnimate Dialogu

DlgAnimate, frame bazlı animasyonlar oluşturmanızı ve düzenlemenizi sağlayan dialog penceresidir.

#### Animasyon Özellikleri

- Frame bazlı kontrol
- Frame rate ayarı
- Loop desteği
- Önizleme

### 10.2 Animasyon Oluşturma

1. **Adım 1:** Animasyon uygulamak istediğiniz bileşeni seçin
2. **Adım 2:** DlgAnimate dialogunu açın
3. **Adım 3:** Frame'leri sırayla ekleyin
4. **Adım 4:** Her frame için texture/görsel belirleyin
5. **Adım 5:** Frame rate'i ayarlayın (FPS)
6. **Adım 6:** Loop seçeneğini işaretleyin (gerekirse)

### 10.3 Animasyon Kontrolleri

| Kontrol | Açıklama |
|---------|----------|
| Play | Animasyonu oynat |
| Pause | Animasyonu duraklat |
| Stop | Animasyonu durdur |
| Previous Frame | Önceki frame |
| Next Frame | Sonraki frame |

> Animasyon FPS değeri düşük olursa akıcılık azalır. Genellikle 24-60 FPS arası değerler idealdir.

---

## 11. Texture/Doku Yönetimi

### 11.1 Doku Ekleme

- **Yöntem 1:** Drag & Drop ile dosya sürükleme
- **Yöntem 2:** DlgTexture dialogunu kullanma
- **Yöntem 3:** DlgChangeImage ile mevcut doku değiştirme

### 11.2 DlgTexture Dialogu

> DlgTexture, projeye yeni doku eklemek, mevcut dokuları yönetmek ve texture ayarlarını değiştirmek için kullanılır.

### 11.3 Doku Formatları

| Format | Uzantı | Açıklama |
|--------|--------|----------|
| DirectX Texture | .dxt | Sıkıştırılmış texture formatı |

### 11.4 Kullanılmayan Dosyalar

> DlgUnusedFileList, projede kullanılmayan texture dosyalarını listeler. Bu dosyaları kaldırarak proje boyutunu optimize edebilirsiniz.

> **Optimizasyon İpuçları:** Kullanılmayan texture'ları düzenli olarak temizleyin. Bu, hem dosya boyutunu küçültür hem de yükleme sürelerini iyileştirir.

---

## 12. Klavye Kısayolları

### 12.1 Dosya İşlemleri

| Kısayol | İşlev |
|---------|-------|
| Ctrl+N | Yeni proje |
| Ctrl+O | Dosya aç |
| Ctrl+S | Kaydet |
| Ctrl+Shift+S | Farklı kaydet |

### 12.2 Düzenleme İşlemleri

| Kısayol | İşlev |
|---------|-------|
| Ctrl+Z | Geri al |
| Ctrl+X | Kes |
| Ctrl+C | Kopyala |
| Ctrl+V | Yapıştır |
| Delete | Sil |
| Ctrl+A | Tümünü seç |

### 12.3 Görünüm İşlemleri

| Kısayol | İşlev |
|---------|-------|
| Ctrl++ | Yakınlaştır |
| Ctrl+- | Uzaklaştır |
| Ctrl+G | Grid aç/kapa |

### 12.4 Taşıma İşlemleri

| Tuş | İşlev |
|-----|-------|
| Sol Ok | Sola taşı |
| Sağ Ok | Sağa taşı |
| Yukarı Ok | Yukarı taşı |
| Aşağı Ok | Aşağı taşı |

> **Not:** Ok tuşlarıyla taşıma miktarı, Option menüsündeki Grid Size ayarına bağlıdır.

---

## 13. İpuçları ve Püf Noktaları

### 13.1 Verimlilik İpuçları

- **Grid Kullanımı:** Grid'i açarak bileşenlerinizi düzenli yerleştirin
- **Kopyalama:** Benzer bileşenleri Ctrl+C/V ile hızlıca çoğaltın
- **Çoklu Seçim:** Ctrl tuşuyla birden fazla bileşen seçin
- **Undo:** Hata yaparsanız Ctrl+Z ile geri alın

### 13.2 Profesyonel Kullanım

- **Hiyerarşi Yönetimi:** Bileşenleri mantıklı gruplar halinde organize edin
- **İsimlendirme:** Bileşenlere açıklayıcı isimler verin
- **Şablon Kullanımı:** Sık kullandığınız yapıları şablon olarak kaydedin
- **Versiyon Kontrolü:** Önemli değişikliklerden önce yedek alın

### 13.3 Performans İpuçları

- **Texture Optimizasyonu:** Gereksiz texture'ları kaldırın
- **Bileşen Sayısı:** Mümkün olduğunca az bileşen kullanın
- **Animasyon Optimizasyonu:** Frame sayısını minimumda tutun
- **DXT Formatı:** Texture'ları DXT formatında sıkıştırın

> **Altın Kural:** Her zaman önce küçük değişiklikler yapın ve test edin. Büyük değişiklikleri adım adım gerçekleştirin.

### 13.4 Hata Önleme

- Her zaman düzenli kayıt yapın
- Değişikliklerden önce yedek alın
- Farklı versiyonları test edin
- Kullanılmayan dosyaları temizleyin

---

## 14. Sıkça Sorulan Sorular (FAQ)

### S1: UIE neden çalışmıyor?

> DirectX 9 Runtime'ın yüklü olduğundan emin olun. Windows Update veya Microsoft'un web sitesinden indirebilirsiniz. Ayrıca ekran kartı sürücülerinizin güncel olduğunu kontrol edin.

### S2: .uif dosyasını nasıl açabilirim?

> Ctrl+O tuşlarına basın veya File > Open menüsünü kullanın. Dosya türü olarak .uif seçeneğini işaretleyin.

### S3: Animasyon nasıl eklerim?

> Animasyon uygulamak istediğiniz bileşeni seçin, ardından DlgAnimate dialogunu açın (menü veya toolbar'dan). Frame'leri ekleyerek animasyon oluşturabilirsiniz.

### S4: Texture eklerken hangi formatı kullanmalıyım?

> UIE .dxt (DirectX Texture) formatını destekler. Diğer formatları kullanmak için önce DXT'ye dönüştürmeniz gerekebilir.

### S5: Bileşenleri nasıl hizalarım?

> Grid açıkken bileşenler otomatik olarak grid noktalarına yaslanır. Ayrıca PropertyView'dan exact koordinat değerleri girebilirsiniz.

### S6: Birden fazla bileşeni aynı anda seçebilir miyim?

> Evet, Ctrl tuşu basılıyken tıklayarak birden fazla bileşen seçebilirsiniz. Veya fare ile sürükleme yaparak alan seçimi yapabilirsiniz.

### S7: Projeyi farklı versiyona nasıl kaydederim?

> File > Save As seçeneği ile farklı versiyonda kaydedebilirsiniz. Ancak versiyonlar arası uyumsuzluk olabileceğini unutmayın.

### S8: Kullanılmayan texture'ları nasıl bulurum?

> Batch Tool menüsündeki DlgUnusedFileList seçeneğini kullanın. Bu, proje içinde kullanılmayan tüm dosyaları listeler.

### S9: Değişikliklerimi nasıl geri alabilirim?

> Ctrl+Z tuşlarıyla son işlemi geri alabilirsiniz. Birden fazla geri alma işlemi desteklenmektedir.

### S10: UIE'yi taşınabilir (portable) kullanabilir miyim?

> Evet, [`build/x64-Release/UIE.exe`](build/x64-Release/UIE.exe) dosyasını herhangi bir dizine kopyalayarak portable olarak kullanabilirsiniz. Kurulum gerektirmez.

---

*Dokümantasyon Sonu*

---

> Bu dokümantasyon Kirasoftware tarafından geliştirilen Knight Online UI Editor (UIE) v2.3.26.400 için hazırlanmıştır.

**© 2016-2026 Kirasoftware | Tüm hakları saklıdır**
