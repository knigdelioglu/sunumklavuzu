# Sunum Kılavuzu

Öğrenci kitap sunumlarında **esere gerçek hâkimiyeti** ölçmek için kullanılan öğretmen odaklı bir çalışma deposudur.

Amaç, öğrencinin yapay zekâ kullanıp kullanmadığını tahmin etmek değildir. Amaç; öğrencinin yalnızca kısa bir özet bilip bilmediğini, eserin yapısını ve ayrıntılarını gerçekten takip edip etmediğini, yorumunu somut metinsel dayanaklarla destekleyip destekleyemediğini anlamaktır.

## Temel yaklaşım

1. Eserin tam metni kaynak olarak hazırlanır.
2. Uzun tek bir görev yerine `prompts/` altındaki kısa analiz görevleri sırayla çalıştırılır.
3. Önce ortak analiz görevleri uygulanır.
4. Eser türüne göre uygun tür modülü eklenir.
5. Analiz çıktıları tek dosyada toplanır.
6. Bu ham incelemelerden öğretmen için kısa, kullanılabilir bir **Sunum Kontrol Dosyası** hazırlanır.
7. Sunum sırasında genel özet sorularından çok; sahne, yapı, ayrıntı, bağlantı, gerekçe ve takip soruları kullanılır.
8. Bütün sınıf aynı eseri sunacaksa `SINIF-SUNUM-SISTEMI.md` ve `prompts/core/06-sinif-sunum-gorevleri.md` kullanılarak öğrenci sayısı kadar farklı sunum görevi hazırlanır.

## Tek eser, farklı sunumlar

Aynı kitabı 25-30 öğrencinin art arda özetlemesi yerine her öğrenciye farklı bir sunum odağı verilebilir.

Her öğrenci:

- eserin tamamından sorumlu kalır,
- kendi sunumunda bir temel iddia ortaya koyar,
- en az iki somut metin dayanağı kullanır,
- eserin başka bir kısmıyla bağlantı kurar,
- sunum sonunda kendi özel başlığının dışından bir kontrol sorusuna cevap verir.

Ayrıntılı yöntem: [`SINIF-SUNUM-SISTEMI.md`](SINIF-SUNUM-SISTEMI.md)

Öğrenci sayısına göre görev üretme promptu: [`prompts/core/06-sinif-sunum-gorevleri.md`](prompts/core/06-sinif-sunum-gorevleri.md)

## Desteklenen eser türleri

- Roman / uzun hikâye
- Hikâye / öykü kitabı
- Tiyatro
- Şiir / şiir kitabı
- Deneme / düşünce yazıları
- Anı / günlük / gezi yazısı
- Biyografi / otobiyografi
- İnceleme / kurmaca dışı eser

Yeni türler `prompts/types/` altına ayrı modül olarak eklenebilir.

## Dizin yapısı

```text
sunumklavuzu/
├── README.md
├── SCOPE.md
├── WORKFLOW.md
├── SINIF-SUNUM-SISTEMI.md
├── prompts/
│   ├── README.md
│   ├── core/
│   │   ├── 00-kaynak-ve-tur-kontrolu.md
│   │   ├── 01-yapi-ve-icerik-haritasi.md
│   │   ├── 02-ayirt-edici-ayrintilar.md
│   │   ├── 03-baglanti-ve-kronoloji.md
│   │   ├── 04-sunum-sorulari.md
│   │   ├── 05-oz-denetim.md
│   │   └── 06-sinif-sunum-gorevleri.md
│   └── types/
│       ├── roman-hikaye.md
│       ├── tiyatro.md
│       ├── siir.md
│       ├── deneme-dusunce.md
│       └── ani-biyografi-kurmaca-disi.md
├── templates/
│   ├── ogretmen-sunum-kontrol-dosyasi.md
│   └── sinif-sunum-dagitim-plani.md
└── examples/
    └── osmancik/
        └── README.md
```

## Hızlı kullanım

Önce `prompts/core/00-kaynak-ve-tur-kontrolu.md` çalıştırılır. Ardından ortak çekirdek promptlar sırayla uygulanır. Eserin türüne göre `prompts/types/` içinden **yalnız ilgili modül** kullanılır.

Analiz çıktıları mümkünse kaynak atıflarıyla saklanır. Son sentezde yalnız metnin desteklediği bilgiler kullanılmalı; belirsiz noktalar kesinleştirilmemelidir.

Bütün sınıf aynı eseri sunacaksa analiz ve öz-denetim tamamlandıktan sonra `06-sinif-sunum-gorevleri.md` çalıştırılır ve `{{OGRENCI_SAYISI}}` yerine sınıf mevcudu yazılır.

## Değerlendirme ilkesi

Öğrencinin bir cevabı şu dört düzeyde düşünülür:

- **Özet bilgisi:** Genel konu/tema düzeyinde kalır.
- **Temel metin bilgisi:** Doğru kişi, bölüm, olay veya düşünceyi tanır.
- **Somut metin hâkimiyeti:** Belirli sahne, pasaj, şiir, bölüm veya gerekçeyi açıklayabilir.
- **Derin metin hâkimiyeti:** Eserin farklı kısımlarını ilişkilendirir ve yorumunu metne dayandırır.

Tek bir sorudan kesin sonuç çıkarılmaz. Farklı bölümlerden ve farklı soru türlerinden kanıt toplanır.
