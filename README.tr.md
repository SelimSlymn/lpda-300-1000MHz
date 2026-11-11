# 300–1000 MHz Log-Periyodik Dipol Dizisi (LPDA)

*English: [README.md](README.md)*

İki boomlu, 20 elemanlı log-periyodik dipol dizisi. CST'de tasarlanıp simüle edildi; alüminyumdan, elemanları sökülüp takılabilir şekilde üretilecek şekilde tasarlandı.

## Sonuçlar (CST, üretilen geometri)

| Büyüklük | Değer |
|---|---|
| Bant | 300–1000 MHz |
| Uyum | Bandın tamamında S11 < −10 dB (en kötü −10.1 dB @ 957 MHz), VSWR ≤ 1.91 |
| Kazanç (realized, tepe) | 9.0–9.5 dBi |
| Ön/arka oranı | 22–30 dB |
| 3 dB hüzme genişliği | E düzlemi 57–62°, H düzlemi 80–89° |

Frekansa göre tablo `performans_tablosu.csv` içinde, grafikler `grafikler/` klasöründe.

## Tasarım

| Parametre | Değer |
|---|---|
| τ / σ | 0.90 / 0.13 |
| Eleman | 20 adet, Ø10 mm alüminyum çubuk |
| En uzun / en kısa eleman (uçtan uca) | 555.2 mm / 75.0 mm |
| Boom | 15 × 15 × 1.5 mm kare alüminyum profil, ~1.41 m |
| Boomlar arası açıklık | 7.5 mm, POM (Delrin) ayırıcılarla |
| Arka kısa devre | Boomların üst yüzünde 37.5 × 15 × 3 mm alüminyum plaka (1. elemanın 138.8 mm arkası) |
| Besleme | RG-316, A boomunun içinden (sonsuz balun); örgü A'ya, iç iletken ön uçta B'ye. Simülasyonda ideal 50 Ω discrete port |

Eleman boyları, çubuk kesim boyları ve konumları: `eleman_tablosu.csv`.

İlk tasarım 22 elemanlı ve Ø8 mm çubukluydu (`sonuclar/export/`, 7 koşuluk tarama `sonuclar/sweep/`). Üretim için 20 elemana inildi (21–22. elemanlar 2.2–2.5 GHz'te rezonansa giriyor, bandın çok üstünde), çubuk çapı 10 mm'ye çıktı ve kısa devre plakası boomların üst yüzüne taşındı. Bu geometrinin simülasyonu `sonuclar/export_d10/` içinde; uyum biraz iyileşti.

## Montaj

Her çubuk, boomun karşı yüzünden giren bir M4 cıvatayla çubuğun ucuna açılan dişe vidalanarak tutturuluyor; elemanlar taşıma için sökülebiliyor. Kesim listesi, delik planı ve kablo güzergâhıyla adım adım 3D montaj rehberi: `uretim/montaj_rehberi.html` (indirip tarayıcıda aç).

## Sınırlar

- Simülasyonda ideal 50 Ω port var; boom içindeki koaksiyel, cıvata ve somunlar modellenmedi.
- Henüz ölçülmedi; VNA ve desen ölçümleri eklenecek.
