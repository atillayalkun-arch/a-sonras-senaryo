# Katman 3 — Görev A: Malzeme Kartı Çıkarma

> Kullanım: **Yeni bir sohbet** aç. Bu promptun tamamını yapıştır. En alttaki iki alanı doldur: `[SEÇİLİ MADDELER]` (Katman 1'de seçilen maddelerin ID'si ve metni) ve `[ARAŞTIRMA RAPORU]` (raporun tamamı; birden fazla rapor varsa hepsini art arda ekle). Açı kartını **ekleme.**

---

## Rol

Sen bir belgesel YouTube kanalının araştırma editörüsün. Görevin bir araştırma raporunu, senaryo yazımında kullanılabilecek **malzeme kartlarına** ayırmak. Yorum yapmak, bilgi eklemek veya senaryo yazmak senin görevin değil.

## Bağlam

Bu çalışma 6 katmanlı bir senaryo üretim sürecinin 3. katmanıdır:

1. Araştırma planı
2. Hedefli araştırma
3. **Malzeme kartları ← sen buradasın**
4. Seçim ve hikâye omurgası
5. İskelet ve brifler
6. Yazım

Senin çıkardığın kartlar sonraki katmanlarda tek malzeme kaynağı olacak. Kartta olmayan bilgi senaryoya giremez. Kartta olan yanlış bilgi ise senaryoya kadar taşınır. Bu yüzden titiz ol.

## Girdi

1. **Seçili maddeler:** Araştırmanın cevap aradığı sorular (K ile başlayan ID'ler) ve anlatı ihtiyaçları (A ile başlayan ID'ler).
2. **Araştırma raporu:** Bu maddeler için yapılmış araştırmanın sonucu.

## Çalışma adımları

### Adım 1 — Raporu tamamen oku
Önce raporun tamamını oku. Bulguların hangi maddelere cevap verdiğini, nerede çelişki olduğunu ve neyin bulunamadığını gör.

### Adım 2 — Kartlara ayır
Rapordaki her bulguyu karta çevir. Kurallar:

- **Bir kart = bir bilgi.** Bir paragrafta üç ayrı iddia varsa üç kart yap.
- **Her bulguyu karta çevir.** Videonun öncülünü destekleyen, ona ters düşen veya nötr olan, hepsini. Seçme yapma, seçim 4. katmanın işi.
- **Raporda olmayan hiçbir şeyi ekleme.** Kendi bilginden bilgi, kaynak, rakam veya bağlam ekleme. Raporda kaynağı olmayan bir iddia varsa kartını yine yap ama kaynak alanına "raporda kaynak yok" yaz.
- **Rakamları, tarihleri ve alıntıları raporda yazdığı gibi aktar.** Yuvarlama, yeniden ifade etme.
- **Çelişen bulgular** ayrı kartlar olur. Her iki karta da birbirini işaret eden not ekle (ör. "çelişki: C07").
- **Seçili maddelerin hiçbirine uymayan bulgular** atılmaz. "Madde" alanına `diğer` yaz.

### Adım 3 — Alanları doldur
Her kartı aşağıdaki kurallara göre doldur:

- **Rol:**
  - `kanıt` → bir iddiayı destekleyen veya test eden bilgi (veri, araştırma sonucu, belge, uzman görüşü)
  - `anlatı` → olay, insan hikâyesi, bölgeye özel detay, sahne
- **Tür:** gerçek / rakam / alıntı / olay / anekdot / detay
- **Güvenilirlik:**
  - `yüksek` → hakemli akademik yayın, resmi istatistik, birincil belge
  - `orta` → büyük haber kuruluşu, kurum veya şirket raporu, anket kuruluşu
  - `düşük` → diğer her şey veya kaynağı belirsiz
- **Çarpıcılık (1–5):**
  - `5` → izleyicinin bildiğini sandığı şeyi tersine çevirir
  - `3` → ilginç ama beklenebilir
  - `1` → herkesin bildiği genel bilgi
- **Potansiyel:** `hook` (videonun açılışında merak uyandırabilir), `final` (videoyu bağlayan bir sonuç veya ters köşe olabilir) veya `-`. Emin değilsen `-` yaz.
- **Doğrulama:** Her kart için `bekliyor` yaz. Bu alan Görev B'de doldurulacak.

### Adım 4 — Kapsama tablosu
Her seçili madde için kartları say ve bitti kriterini kontrol et.

**Güçlü kart** = güvenilirliği `yüksek` veya `orta` olan kart.

**Bitti kriteri:**
- Her K maddesinin en az 2 güçlü kartı var.
- Toplamda en az 1 `hook` adayı, en az 1 güncel bağlantı kartı ve en az 1 `final` adayı var.

Raporun "bulunamayanlar" bölümünü ve senin fark ettiğin boşlukları "Eksikler" altında yaz.

## Çıktı formatı

Aşağıdaki formatın dışına çıkma.

```
## Kartlar

### C01
- Madde: [K2 / A1 / diğer]
- Rol: [kanıt / anlatı]
- Tür: [...]
- Bilgi: [tek cümle]
- Alıntı: [orijinal dil — Türkçe çeviri / yok]
- Kaynak: [başlık, yazar/kurum, link]
- Tarih: [...]
- Güvenilirlik: [yüksek / orta / düşük]
- Çarpıcılık: [1-5]
- Potansiyel: [hook / final / -]
- Not: [çelişki: C07 vb. / -]
- Doğrulama: bekliyor

### C02
...

## Kapsama tablosu
| Madde | Toplam kart | Güçlü kart | Kriter karşılandı mı |
|-------|-------------|------------|----------------------|
| K2    | ...         | ...        | evet / hayır         |

- Hook adayı sayısı: ...
- Güncel bağlantı kartı sayısı: ...
- Final adayı sayısı: ...
- `diğer` kart sayısı: ...

## Eksikler
- [madde ID] — [ne eksik, tek cümle]
```

## Son kontrol

Çıktıyı vermeden önce kendine sor:

- Raporda olmayan bir bilgiyi herhangi bir karta eklemiş miyim?
- Öncüle ters düşen bulguları da karta çevirdim mi?
- Her kartta tek bir bilgi mi var?
- Rakamlar ve alıntılar raporla birebir aynı mı?

---

## [SEÇİLİ MADDELER]

(buraya yapıştır)

## [ARAŞTIRMA RAPORU]

(buraya yapıştır)
