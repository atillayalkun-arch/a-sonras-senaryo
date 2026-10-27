# Senaryo Pipeline'ı (Versiyon 1, 6 Katman)

Girdi: açı kartı + anlatıcı DNA. Çıktı: bitmiş senaryo.

İki tür malzeme var:

| | **Kanıt malzemesi** | **Anlatı malzemesi** |
|---|---|---|
| İşlevi | Söylediğini doğrular | Söylediğini hissettirir, akılda tutar |
| Örnek | Akademik çalışma, resmi veri, belge | Güncel olay, insan hikâyesi, benzetme, sahne/mekân detayı |
| Nasıl bulunur | Derin araştırmayla | Bir kısmı aranır, bir kısmı üretilir |
| Nasıl kontrol edilir | Kaynak doğru mu? | Gerçekse kaynak; benzetmeyse eşleşme doğru mu? |

---

## Katman 1: Araştırma planı *(girdi: açı kartı)*

- **Görev A:** Açı kartından iki liste çıkar:
  - **Kanıt soruları (6–10 adet):** Ne doğrulanmalı? Her soru bir kaynak türüne bağlanır: akademik, resmi veri, birincil belge, çelişki/tartışma.
  - **Anlatı ihtiyaçları:** Hook adayı, güncel bağlantı ("bu neden şimdi önemli?"), insan hikâyesi/anekdot, bölgeye özel detay.
- **Görev B:** İki listeden en güçlü 3–5 maddeyi seç ve her biri için bir **araştırma brifi** (hazır prompt) yaz.
- **Çıktı:** 1 sayfa: iki liste, seçilenler ve briflerin kendisi.
- **Bitti kriteri:** Seçilen maddeler karşılandığında videonun ana vaadi hem kanıtlanmış hem anlatılabilir oluyor.
- **Not:** Benzetmeler bu katmanda toplanmaz. Onlar 5. katmanda üretilir.

## Katman 2: Hedefli araştırma

- Her brif için ayrı bir araştırma çalıştırması yapılır. Yöntem malzeme türüne göre seçilir:
  - **Kanıt:** Gemini/ChatGPT Deep Research.
  - **Güncel olay/veri:** Tarih filtreli normal arama. Derin araştırma modları en güncel olaylarda zayıf kalabiliyor.
  - **İnsan hikâyesi / yerel detay:** Japonca kaynaklara yönelik hedefli derin araştırma. Brife kaynakları adıyla yaz: J-STAGE, CiNii Research, Ulusal Diyet Kütüphanesi Dijital Koleksiyonu (国立国会図書館デジタルコレクション), yerel tarih kaynakları (郷土資料), belediye ve yerel haber siteleri. Japonca sorguyla aratılmasını da iste.
- Her brif, raporun **sabit formatta** dönmesini ister: iddia/olay, kaynak linki, tarih, doğrudan alıntı, şaşırtıcı detay, çelişkiler.
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
