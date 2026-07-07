# SIPPZ — CORE SEVEN ASSET NORMALIZATION SPEC v1.0

**Status:** CANON SPEC FOR ASSET NORMALIZATION
**Date:** 2026-06-07

**Purpose:**
Core Seven karakter asset'lerinin tüm büyük ve küçük uygulama yüzeylerinde tutarlı, temiz, full-body ve premium görünmesini sağlamak.

Bu aşamada kod fix durdurulmuştur.
WinAnimation structural aura alignment fix korunacaktır.
Sorunun devam eden kısmı asset composition standardizasyonu olarak ele alınacaktır.
Freeze yoktur.
Core Seven Asset Freeze ancak normalize asset'ler gerçek cihazda doğrulandıktan sonra verilecektir.

---

## 1. GENEL STANDARTLAR

Tüm asset'ler için:

- Format: PNG-24
- Background: transparent
- Color profile: sRGB
- Alpha: gerçek transparent
- Arka plan: yok
- Ground shadow: yok
- White floor: yok
- Dark oval shadow: yok
- White halo: yok
- Baked floor / baked platform: yok
- Canvas kenarına değen karakter parçası: yok
- Ayak, kuyruk, aksesuar, kulak, boynuz, pençe: tam görünür

**Yasak olanlar:**
- beyaz zemin parlaması
- koyu oval gölge
- alt platform
- yapay zemin çizgisi
- kesilmiş ayak
- kesilmiş kuyruk
- kesilmiş aksesuar
- canvas dışına taşan parça
- karakterin yere yapışık durması

---

## 2. DOSYA ADLANDIRMA

Mevcut convention korunur:

```
[slug].png
[slug]-collection.png
[slug]-unlock.png
[slug]-thumbnail.png
```

**Slug'lar değişmez:**
- waffle-ayi
- espresso-kopek
- golden-panda
- coldbrew-tavsan
- mocha-baykus
- latte-kedi
- matcha-tilki

**Canonical eşleşme:**

| Slug | Karakter |
|---|---|
| waffle-ayi | Bruno |
| espresso-kopek | Pip |
| golden-panda | Mocha |
| coldbrew-tavsan | Zest |
| mocha-baykus | Atlas |
| latte-kedi | Luma |
| matcha-tilki | Miko |

---

## 3. ÖNCELİK

Önce unlock asset'leri normalize edilecek. Çünkü WinAnimation ve büyük aktivasyon yüzeylerinde sorun en görünür şekilde burada ortaya çıkıyor.

**Öncelik sırası:**
1. `mocha-baykus-unlock.png` = Atlas
2. `latte-kedi-unlock.png` = Luma
3. `golden-panda-unlock.png` = Mocha
4. `coldbrew-tavsan-unlock.png` = Zest
5. `espresso-kopek-unlock.png` = Pip
6. `matcha-tilki-unlock.png` = Miko
7. `waffle-ayi-unlock.png` = Bruno

Unlock asset'leri PASS olduktan sonra companion, collection ve thumbnail asset'leri aynı standarda göre normalize edilecek.

---

## 4. UNLOCK PNG SPEC

**Canvas:** 1024×1024, transparent PNG

**Hedef:**
- Karakter full-body
- Üst boşluk: 7–9% (~72–92px)
- Alt boşluk: 7–9% (~72–92px)
- Sol/sağ güvenli alan: minimum 8% (~82px)
- Karakter yüksekliği: 82–86% (~840–880px)
- Karakter canvas içinde optik olarak merkezde
- Ayak/pençe/kuyruk alt noktası canvas alt kenarına yapışmayacak
- Karakterin en alt noktası ile canvas alt kenarı arasında yaklaşık 72–92px transparent boşluk olacak

**Yasak:**
- ground shadow
- white floor
- dark oval shadow
- baked floor
- alt zemin çizgisi
- karakterin altında platform
- ayakların gölge içinde kaybolması

---

## 5. COMPANION PNG SPEC

**Canvas:** 512×512, transparent PNG

**Hedef:**
- Üst boşluk: 8–10%
- Alt boşluk: 8–10%
- Sol/sağ güvenli alan: minimum 10%
- Karakter yüksekliği: 78–82%
- Küçük render'da tanınabilir siluet
- Full-body mümkünse korunur, ama HomeScreen küçük yüzeylerde optik netlik önceliklidir

**Yasak:** shadow, floor, halo, kesilmiş aksesuar, kesilmiş kuyruk, canvas kenarına yapışan parça

---

## 6. COLLECTION PNG SPEC

**Canvas:** 512×512, transparent PNG

**Hedef:**
- Collection grid 84pt render için optimize
- Üst boşluk: 6–10%
- Alt boşluk: 8–10%
- Sol/sağ güvenli alan: minimum 8%
- Karakter yüksekliği: 78–84%
- Full-body görünür
- Kart içinde karakter sıkışık durmaz

**Yasak:** shadow, floor, halo, ayak/kuyruk kırpılması

---

## 7. THUMBNAIL PNG SPEC

**Canvas:** 256×256, transparent PNG

**Hedef:**
- Üst boşluk: 8–10%
- Alt boşluk: 8–10%
- Sol/sağ güvenli alan: minimum 8%
- Karakter yüksekliği: 76–82%
- Küçük render'da yüz ve siluet okunur

**Yasak:** shadow, floor, halo, canvas kenarı kırpması

---

## 8. KARAKTER BAZLI NOTLAR

### Bruno — `waffle-ayi`
- Bardak aksesuarı korunacak
- Ayak/pençe görünür olacak
- Alt shadow varsa temizlenecek
- Gövde ağır olduğu için alt boşluk özellikle korunacak

### Pip — `espresso-kopek`
- Canlı test yok — final PASS verilmeyecek
- Ön ayaklar ve botlar görünür olacak
- Kulaklar canvas içinde kalacak
- Aksesuar ve eşarp korunacak
- Unlock asset normalize sonrası ayrıca live test istenecek

### Mocha — `golden-panda`
- Koyu ground shadow tamamen temizlenecek
- Ayak/alt gövde gölgede kaybolmayacak
- Alt bölge temiz transparent olacak
- Karakter yere yapışık durmayacak

### Zest — `coldbrew-tavsan`
- White floor tamamen temizlenecek
- Beyaz halo kaldırılacak
- Ayak/bacak çevresi temiz transparent olacak
- Cyan aksesuarlar korunacak

### Atlas — `mocha-baykus`
- Ayak/sandalet/alt robe görünür olacak
- Koyu shadow temizlenecek
- Alt gövde sahnede kaybolmayacak
- Eğer asset içinde ayaklar zaten yoksa bu açıkça raporlanacak

### Luma — `latte-kedi`
- Ayak/çizme görünür olacak
- Kuyruk tam görünür olacak
- Alt gövde safe area içinde kalacak
- Kuyruk canvas altına veya yanına yapışmayacak

### Miko — `matcha-tilki`
- Botlar görünür olacak
- Kuyruk alt kısmı safe area içinde kalacak
- Minimal shadow varsa temizlenecek
- En iyi görünenlerden biri olsa da yeniden QA yapılacak

---

## 9. TESLİM SIRASI

**Aşama 1:** Yalnızca 7 unlock PNG normalize edilir.
```
waffle-ayi-unlock.png
espresso-kopek-unlock.png
golden-panda-unlock.png
coldbrew-tavsan-unlock.png
mocha-baykus-unlock.png
latte-kedi-unlock.png
matcha-tilki-unlock.png
```

**Aşama 2:** Unlock gerçek cihaz QA yapılır.

**Aşama 3:** PASS çıkarsa companion, collection ve thumbnail setleri normalize edilir.

**Aşama 4:** Tam Core Seven QA yapılır.

---

## 10. TESLİM SONRASI CODE GÖREVİ

Normalize asset'ler kullanıcı tarafından verildiğinde:
- Aynı dosya adlarıyla mevcut asset'lerin üzerine yazılacak
- `characters.js` field'ları değişmeyecek
- `image` / `imageCollection` / `imageUnlock` wiring değişmeyecek
- WinAnimation structural aura alignment fix korunacak
- Başka kod değiştirilmeyecek
- Commit/push/deploy yapılmayacak

Sonra rapor hazırlanacak:

### CORE SEVEN NORMALIZED ASSET QA REPORT

Rapor içeriği:
- Hangi dosyalar değişti
- BBox analizi
- Shadow/floor/halo kontrolü
- Her karakter için unlock render sonucu
- Android test sonucu
- iPhone gerçek cihaz test sonucu
- Pip live durum notu
- Freeze verilebilir mi

---

## 11. FREEZE KURALI

Core Seven Asset Freeze şu an **yoktur**.

Freeze ancak şu şartlardan sonra verilebilir:
- Normalize unlock asset'leri PASS
- Gerçek cihaz iPhone QA PASS
- Android QA PASS
- Pip live test veya açık risk notu
- Hiçbir karakterde ayak/kuyruk/alt gövde kaybı yok
- Shadow/floor/halo yok
- **Kullanıcı final onayı verdi**

Freeze kararını Code vermez. Freeze kararını kullanıcı verir.
