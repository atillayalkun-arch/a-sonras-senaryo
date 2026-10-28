# Senaryo Pipeline'ı (Versiyon 1, 6 Katman)

Girdi: açı kartı + anlatıcı DNA. Çıktı: bitmiş senaryo.

Beş malzeme türü var:

| Kod | Tür | İşlevi |
|-----|-----|--------|
| GR | Güncel ruh | Konunun bugün yarattığı gerilim. "Neden şimdi?" |
| MS | Mikro-sahne | İzleyicinin her gün yaşadığı küçük, somut anlar. "Beni anlatıyor." |
| MK | Mekanizma | Yaşanan durumun arkasındaki sistem kuralı veya literatürdeki adı. |
| SV | Somut vaka | Mekanizmanın gerçek hayatta görüldüğü belgelenmiş olay. |
| SK | Soğuk kanıt | Akademik çalışma, resmî veri, anket. Mekanizmayı mühürler. |

**Araştırma ilkesi:** Tarafsızlık cevabı önceden varsaymamaktır, konudan kaçınmak değildir.

---

## Katman 1: Keşif ve haritalama *(girdi: açı kartı)*

Promptlar: `katman-1/`

- **1A Radar** (web erişimli model): Konunun son 2–3 yıldaki haritası. Canlı dil, güncel sürtünmeler, acı noktaları, klişeler, açık tartışmalar.
- **1B Çarklar ve matris** (yeni sohbet): Radar'dan türetilen 3–4 hipotez çark, 1 çürütme sorusu ve her çark için gereken malzeme türlerini gösteren matris.
- **İnsan onayı** (5–10 dk).
- **1C Brifler** (1B ile aynı sohbet): Malzeme türüne göre gruplanmış 3 brif (G: güncel ruh + mikro-sahne, V: somut vaka, K: soğuk kanıt + mekanizma).

## Katman 2: Hedefli araştırma

- 3 brif, 3 ayrı derin araştırma çalıştırması olarak verilir. Ek prompt gerekmez.
- Her türün zaman penceresi, kaynak havuzu ve doğrulama ilkesi brifin içinde sabittir.
- **Kural:** Brif başına tek çalıştırma yapılır. İkinci tura sadece 4. katman somut bir boşluk bulursa izin var.

## Katman 3: Malzeme kartları

- Her rapor, tek bilgiden oluşan kartlara bölünür. Kart şablonu:

  `ID | rol (kanıt/anlatı) | bilgi | tür (gerçek/rakam/alıntı/olay/anekdot/detay) | kaynak + tarih | güvenilirlik | çarpıcılık 1-5 | hangi maddeye cevap`

- En önemli kartların kaynağı açılıp kontrol edilir ve kart "doğrulandı/doğrulanmadı" diye işaretlenir. Deep research modları kaynak uydurabiliyor.
- **Bitti kriteri:** Her seçili kanıt sorusunun en az 2 güçlü kartı var. Ayrıca en az 1 hook adayı, 1 güncel bağlantı ve 1 final (payoff) adayı var.

## Katman 4: Seçim ve hikâye omurgası

- Kartlar elenir ve kalanlar **beat'lere** dizilir. Her beat tek satırdır ve kullandığı kart ID'leri yanında yazar.
- **Sıralama kuralı:** Beat'ler arası geçiş "ve sonra" değil, **"ama" / "bu yüzden"** ile kurulur. Böylece sıralama bilgi listesine değil, merak zincirine dönüşür.
- **Anlatı kartlarının tipik yerleri:**
  - Güncel olay → hook'a veya "neden önemli" beat'ine.
  - İnsan hikâyesi → açılışa veya finale.
  - Yerel detay → sahne kurulan beat'lere.
- Ayrıca belirlenir: hook kartı, açılan ve kapanan merak döngüleri (open loop), final.
- Somut bir boşluk varsa burada tespit edilir ve 2. katmana tek, hedefli bir geri dönüş yapılır.

## Katman 5: İskelet ve brifler

Her beat için kısa bir brif yazılır:

- **Amaç:** Bu bölüm neden var?
- **Kullanılacak kartlar:** Bölümde sadece bunlar kullanılır.
- **İzleyicide hedeflenen his**
- **Merak döngüsü:** Burada açılacak veya kapanacak döngü
- **Sonraki beat'e geçiş cümlesinin fikri**
- **Hedef süre/karakter:** Japonca anlatımda yaygın ölçü yaklaşık 300 karakter/dakika. Bunu kendi anlatıcı temponla kalibre etmek gerekir.
- **Anlaşılması zor mu? → benzetme gerekli mi?**
  - Gerekliyse o beat için 3–5 benzetme üretilir (arı kovanı gibi) ve insan birini seçer.
  - Seçilen benzetme tek bir soruyla kontrol edilir: *"Bu benzetme mekanizmanın hangi kısmını yanlış öğretiyor?"*
  - Seçilen benzetme brife eklenir.

Bu katmanın sonunda senaryo, stil dışında tamamen hazır olmalı.

## Katman 6: Yazım *(girdi: iskelet + anlatıcı DNA)*

- Önce 3 hook varyantı yazılır, insan birini seçer.
- Sonra metin beat beat yazılır. **Kural:** Model briflerde olmayan bilgiyi veya benzetmeyi ekleyemez.
- En sonda tek bir kontrol turu yapılır:
  - Bilgiler kartlarla uyumlu mu?
  - Ton anlatıcı DNA'sına uygun mu?
  - Sesli okununca akıyor mu?

---

## Sistemi ayakta tutan 4 kural

1. **Her katmanın çıktısı tek bir dosyadır,** şablonu sabittir. Bir sonraki katman sadece o dosyayı okur.
2. **Her katman sonunda insan onayı alınır.** İnsanın görevi seçmek ve onaylamak, üretmek değil.
3. **Geri dönüş sadece bir kez ve hedefli yapılır.** "Biraz daha araştıralım" yasak, "şu beat için şu bilgi eksik" serbest.
4. **Önce versiyon 1 çıkar.** İlk video bitmeden sisteme katman eklenmez.
