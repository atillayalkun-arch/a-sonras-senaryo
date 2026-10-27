# Katman 1 — Görev B: Araştırma Brifleri

> Kullanım: Görev A ile **aynı sohbette** devam et. Bu promptu yapıştır, en alttaki `[SEÇİLEN MADDELER]` alanına seçtiğin ID'leri yaz (gerekirse maddelerde yaptığın değişiklikleri de ekle).

---

## Görev

Görev A'da hazırladığın plandan insanın seçtiği maddeler aşağıda. Her seçilen madde için **ayrı, kendi başına çalışan bir araştırma brifi** yaz. Her brif ayrı bir yapay zekâ araştırma modeline (Gemini Deep Research, ChatGPT Deep Research veya normal web araması) olduğu gibi yapıştırılacak. O model bu sohbeti, açı kartını ve videoyu bilmeyecek.

## Kurallar

### 1. Brif kendi başına çalışmalı
Araştırma modeli sadece brifi görecek. Brif, araştırmayı yapmak için gereken her şeyi içermeli, dışarıdaki hiçbir şeye atıf yapmamalı.

### 2. Brifte hipotez ve açı olmaz
Brifte şunlar **yer almaz:** açı kartı, videonun temel sorusu, beklenen cevap, videonun duruşu veya ne kanıtlanmak istendiği.

Sadece araştırma sorusu ve kapsam verilir. Sebep: Araştırma modeli neyi kanıtlamak istediğini bilirse ona uygun kaynakları seçer ve aksini gösteren kanıtları atlar (doğrulama yanlılığı). Bağlam olarak sadece "Bu araştırma bir belgesel video için yapılmaktadır" denebilir.

### 3. Araç malzeme türüne göre seçilir
- **Kanıt sorusu** → Derin araştırma (Gemini/ChatGPT Deep Research).
- **Güncel bağlantı** → Normal web araması, tarih filtreli (varsayılan: son 12 ay). Derin araştırma modları en güncel olaylarda zayıf kalabilir.
- **İnsan hikâyesi / bölgeye özel detay / hook adayı** → Derin araştırma, bölgenin dilindeki kaynaklara yönelik.

### 4. Kaynaklar adıyla yazılır
Araştırma bölgesi Japonya ise brifte uygun olanları adıyla belirt. Örnekler:
- Akademik: J-STAGE, CiNii Research, Google Scholar
- Arşiv / tarih: 国立国会図書館デジタルコレクション, 郷土資料
- Resmi veri: e-Stat, ilgili bakanlık ve kamu kurumu yayınları
- Haber: büyük ulusal gazeteler, yerel haber siteleri, belediye siteleri

Kaynak listesini sorunun türüne göre seç, hepsini her brife koyma.

### 5. Arama terimleri bölgenin dilinde de verilir
Her brife 4–8 arama terimi ekle: bölgenin dilinde (Japonya için Japonca) ve İngilizce. Terimler tarafsız olmalı, cevabı ima etmemeli.

### 6. Hariç tutulacaklar belirtilir
Varsayılan olarak hariç: kişisel bloglar, kaynak göstermeyen içerik siteleri, kariyer/kişisel gelişim tavsiye içerikleri, yapay zekâ ile üretilmiş özet siteleri. Soruya göre ekleme yap.

### 7. Dürüstlük cümlesi zorunlu
Her brifte şu kural aynen yer almalı:
"Güvenilir bir kaynak bulamazsan bulamadığını açıkça yaz. Tahmin etme, boşluğu doldurma. Kaynakların birbiriyle çeliştiği yerleri ayrıca belirt."

## Brif şablonu

Her brif için aşağıdaki şablonu kullan. Brifler birbirinden `=====` çizgisiyle ayrılsın.

```
=====
BRİF [ID] — [kısa başlık]
Önerilen araç: [Derin araştırma / Normal arama (son X ay)]
=====

Bu araştırma bir belgesel video için yapılmaktadır.

## Araştırma sorusu
[tek, net soru]

## Kapsam
- Bölge: [...]
- Zaman aralığı: [...]
- Odak: [sorunun hangi yönüne bakılacağı, 1-2 cümle]

## Öncelikli kaynaklar
- [...]

## Arama terimleri
- [bölgenin dilinde]
- [İngilizce]

## Hariç tut
- [...]

## Kurallar
- Güvenilir bir kaynak bulamazsan bulamadığını açıkça yaz. Tahmin etme, boşluğu doldurma. Kaynakların birbiriyle çeliştiği yerleri ayrıca belirt.
- Her bulgu için kaynağın doğrudan linkini ver.
- Alıntıları orijinal dilinde ver, yanına Türkçe çevirisini ekle.

## Rapor formatı
Raporu Türkçe yaz. Her bulguyu ayrı blok olarak ver:

### Bulgu [numara]
- İddia / olay: [tek cümle]
- Kaynak: [başlık, yazar/kurum, link]
- Tarih: [yayın tarihi]
- Kaynak türü: [akademik / resmi veri / belge / haber / diğer]
- Doğrudan alıntı: [orijinal dil] — [Türkçe çeviri]
- Şaşırtıcı detay: [varsa]

En sonda:
### Çelişkiler
[kaynakların ayrıştığı noktalar]
### Bulunamayanlar
[aranıp güvenilir kaynak bulunamayan konular]
```

## Son kontrol

Brifleri vermeden önce her biri için kendine sor:

- Bu brif açı kartını, temel soruyu veya beklenen bir cevabı ima ediyor mu? Ediyorsa düzelt.
- Bu sohbeti hiç görmemiş bir model bu brifi tek başına anlayıp araştırabilir mi?
- Dürüstlük cümlesi ve rapor formatı eksiksiz mi?

---

## [SEÇİLEN MADDELER]

(buraya seçtiğin ID'leri yaz, ör. K2, K5, K7, A1)
