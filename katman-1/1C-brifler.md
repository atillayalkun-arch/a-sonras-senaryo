# Katman 1 — 1C: Araştırma Brifleri

> Kullanım: 1B ile **aynı sohbette** devam et. 1B çıktısını kontrol et. Değiştirmek istediğin çark, hücre veya öncelik varsa en alttaki `[İNSAN KARARLARI]` alanına yaz. Yoksa "onaylandı" yaz. Sonra bu promptu gönder.

---

## Görev

Onaylanan malzeme matrisini **3 ayrı araştırma brifine** dönüştür. Brifler **malzeme türüne göre** gruplanır, çünkü her türün kaynak havuzu ve doğrulama ilkesi farklıdır:

| Brif | Kapsadığı türler | Neden birlikte |
|------|------------------|----------------|
| **Brif G** | GR (güncel ruh) + MS (mikro-sahne) | Aynı kaynak havuzu: güncel medya ve saha yazıları |
| **Brif V** | SV (somut vaka) | Belgelenmiş olaylar ve kronoloji |
| **Brif K** | SK (soğuk kanıt) + MK (mekanizma) | Akademik ve resmî kaynaklar; mekanizmanın adı ve kanıtı aynı literatürde |

Her brif, matristeki ilgili sütunların **tüm çarklara ait** hücrelerini kapsar. Her brif ayrı bir araştırma modeline (Gemini Deep Research, ChatGPT Deep Research vb.) **olduğu gibi** yapıştırılacak. O model bu sohbeti, açı kartını ve videoyu bilmeyecek.

## Brif yazma kuralları

### 1. Brif kendi başına çalışmalı
Araştırmayı yapmak için gereken her şeyi içermeli. Dışarıdaki hiçbir şeye atıf yapmamalı.

### 2. Brifte hipotez ve açı olmaz
Brife açı kartı, temel soru, çark hipotezleri veya beklenen cevap **girmez.** Her çark, 1B'deki **tarafsız araştırma sorusu** olarak girer. Bağlam olarak sadece "Bu araştırma bir belgesel video için yapılmaktadır" denebilir.

Her soru için araştırma modelinden **hem destekleyen hem çürüten bulguları** getirmesi istenir. Sebep: Araştırma modeli neyi kanıtlamak istediğini bilirse ona uygun kaynakları seçer ve aksini atlar.

### 3. Konu yasağı yok
Briflerde rahatsız edici başlıklardan kaçınılmaz. Kayırmacılık, güç ilişkileri, cinsiyet ve yaş farkları gibi konular soruda gerekiyorsa açıkça aranır.

### 4. Her bulgu etiketlenir
Araştırma modelinden her bulguyu **soru ID'si** (Ç1, Ç2, ÇS…) ve **malzeme türü** (GR, MS, SV, SK, MK) ile etiketlemesi istenir. Bu, sonraki katmanda kart çıkarmayı kolaylaştırır.

### 5. Arama terimleri
Her soru için 3–5 arama terimi ver: bölgenin dilinde (Japonya için Japonca, Radar'daki "canlı dil" terimlerini kullan) ve İngilizce. Terimler tarafsız olmalı.

### 6. Türe göre sabit ilkeler
Aşağıdaki tablo her brife ilgili satırıyla **aynen** girer. Bölge Japonya değilse kaynak havuzunu o bölgenin eşdeğerleriyle değiştir.

| Brif | Zaman penceresi | Kaynak havuzu (Japonya) | Doğrulama ilkesi |
|------|-----------------|-------------------------|------------------|
| **G** | Son 24 ay | İş ve ekonomi medyası (日本経済新聞, 東洋経済オンライン, ダイヤモンド・オンライン, PRESIDENT Online, NHK), İK araştırma kurumlarının saha yazıları ve nitel raporları (リクルートワークス研究所, パーソル総合研究所), danışman ve uzman vaka yazıları, röportajlar | Örneklem şartı **aranmaz.** Şart: **somutluk ve mekanizma.** Dedikodu veya tavsiye değil, iş akışında gerçekten yaşanan somut bir durumu anlatıyor mu? |
| **V** | Tercihen son 5 yıl. Daha eski vaka sadece "kilit vaka" gerekçesiyle ve `[eski]` etiketiyle | Araştırmacı gazetecilik dosyaları, mahkeme kararları ve hukuk haberleri, sendika kayıtları, kurum vaka analizleri, iş sosyolojisi saha mülakatları | Şart: **kronoloji ve neden-sonuç.** Olayın öncesi, kırılma anı ve sonucu belgelenmiş mi? |
| **K** | Veri dönemi tercihen son 5 yıl. Daha eski çalışma sadece "temel çalışma" gerekçesiyle ve `[temel]` etiketiyle | J-STAGE, CiNii Research, RIETI, 労働政策研究・研修機構 (JILPT), e-Stat, 人事院, 厚生労働省, İK araştırma kurumlarının nicel anketleri | En katı denetim: yöntem, örneklem, veri dönemi, orijinal alıntı. Sınırlama **tek cümle** ve sadece gerçek bir sınır varsa yazılır. |

### 7. Dürüstlük cümlesi zorunlu
Her brifte aynen yer alır:
"Güvenilir bir kaynak bulamazsan bulamadığını açıkça yaz. Tahmin etme, boşluğu doldurma. Kaynakların birbiriyle çeliştiği yerleri ayrıca belirt."

## Brif şablonu

Brifleri `=====` çizgisiyle ayır.

```
=====
BRİF [G / V / K] — [kısa başlık]
Önerilen araç: Derin araştırma
=====

Bu araştırma bir belgesel video için yapılmaktadır.

## Bölge
[...]

## Araştırma soruları
### [Ç1] [tarafsız soru]
- Aranan: [matristeki tarif, tarafsız dille]
- Öncelik: [1-3]
- Arama terimleri: [bölge dili] / [İngilizce]
### [Ç2] ...

Her soru için hem destekleyen hem çürüten bulguları getir.

## Zaman penceresi, kaynak havuzu ve doğrulama ilkesi
[tablodaki ilgili satır, aynen]

## Hariç tut
- Kişisel tavsiye blogları, kaynak göstermeyen içerik siteleri, yapay zekâ ile üretilmiş özet siteleri
- [soruya göre ek]

## Kurallar
- Güvenilir bir kaynak bulamazsan bulamadığını açıkça yaz. Tahmin etme, boşluğu doldurma. Kaynakların birbiriyle çeliştiği yerleri ayrıca belirt.
- Her bulgu için kaynağın doğrudan linkini ver.
- Alıntıları orijinal dilinde ver, yanına Türkçe çevirisini ekle.
- Her bulguyu soru ID'si ve malzeme türüyle etiketle.

## Rapor formatı
Raporu Türkçe yaz. Her bulguyu ayrı blok olarak ver:

### Bulgu [numara] — [soru ID] / [tür]
[BRİF G için]
- Durum / gelişme: [tek cümle]
- Somut detay: [sahne, ifade, örnek]
- Kaynak: [başlık, yazar/kurum, link]
- Tarih: [...]
- Doğrudan alıntı: [orijinal — Türkçe]

[BRİF V için]
- Olay: [tek cümle]
- Kronoloji: [öncesi → kırılma anı → sonuç, tarihleriyle]
- Kaynak(lar): [başlık, kurum, link]
- Belge türü: [mahkeme kararı / haber / vaka analizi / diğer]
- Doğrudan alıntı: [orijinal — Türkçe]

[BRİF K için]
- Bulgu: [tek cümle]
- Kaynak: [başlık, yazar/kurum, link]
- Yayın tarihi / veri dönemi: [...]
- Yöntem ve örneklem: [...]
- Doğrudan alıntı: [orijinal — Türkçe]
- Sınırlama: [tek cümle, sadece gerçek bir sınır varsa]
- Kavramın adı (MK ise): [literatürdeki adı, orijinal dilde]

En sonda:
### Çelişkiler
### Bulunamayanlar
```

(Her brife sadece kendi türünün rapor formatını koy.)

## Son kontrol

Brifleri vermeden önce her biri için kendine sor:

- Bu brif açı kartını, bir çark hipotezini veya beklenen bir cevabı ima ediyor mu? Ediyorsa düzelt.
- Bu sohbeti hiç görmemiş bir model bu brifi tek başına anlayıp araştırabilir mi?
- Türe göre sabit ilke satırı aynen girdi mi?
- Dürüstlük cümlesi ve rapor formatı eksiksiz mi?

---

## [İNSAN KARARLARI]

(değişiklikleri yaz veya "onaylandı" yaz)
