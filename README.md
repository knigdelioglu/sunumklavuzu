# Sunum Kılavuzu

Öğrenci kitap sunumlarında **esere gerçek hâkimiyeti** ölçmek için kullanılan öğretmen odaklı bir çalışma deposudur.

Amaç, öğrencinin yapay zekâ kullanıp kullanmadığını tahmin etmek değildir. Amaç; öğrencinin yalnızca kısa bir özet bilip bilmediğini, eserin yapısını ve ayrıntılarını gerçekten takip edip etmediğini, yorumunu somut metinsel dayanaklarla destekleyip destekleyemediğini anlamaktır.

## Temel yaklaşım

1. Eserin kendisi NotebookLM'e kaynak olarak yüklenir.
2. NotebookLM'e uzun tek bir prompt verilmez; `prompts/` altındaki kısa görevler sırayla çalıştırılır.
3. Önce ortak analiz görevleri uygulanır.
4. Eser türüne göre uygun tür modülü eklenir.
5. NotebookLM çıktıları tek dosyada toplanır.
6. Bu ham analizlerden öğretmen için kısa, kullanılabilir bir **Sunum Kontrol Dosyası** hazırlanır.
7. Sunum sırasında genel özet sorularından çok; sahne, yapı, ayrıntı, bağlantı, gerekçe ve takip soruları kullanılır.

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
├── prompts/
│   ├── README.md
│   ├── core/
│   │   ├── 00-kaynak-ve-tur-kontrolu.md
│   │   ├── 01-yapi-ve-icerik-haritasi.md
│   │   ├── 02-ayirt-edici-ayrintilar.md
│   │   ├── 03-baglanti-ve-kronoloji.md
│   │   ├── 04-sunum-sorulari.md
│   │   └── 05-oz-denetim.md
│   └── types/
│       ├── roman-hikaye.md
│       ├── tiyatro.md
│       ├── siir.md
│       ├── deneme-dusunce.md
│       └── ani-biyografi-kurmaca-disi.md
└── examples/
    └── osmancik/
        └── README.md
```

## Hızlı kullanım

NotebookLM'de önce `prompts/core/00-kaynak-ve-tur-kontrolu.md` çalıştırılır. Ardından ortak çekirdek promptlar sırayla uygulanır. Eserin türüne göre `prompts/types/` içinden **yalnız ilgili modül** kullanılır.

NotebookLM çıktıları mümkünse kaynak atıflarıyla dışa aktarılır. Son sentezde yalnız metnin desteklediği bilgiler kullanılmalı; belirsiz noktalar kesinleştirilmemelidir.

## Değerlendirme ilkesi

Öğrencinin bir cevabı şu dört düzeyde düşünülür:

- **Özet bilgisi:** Genel konu/tema düzeyinde kalır.
- **Temel metin bilgisi:** Doğru kişi, bölüm, olay veya düşünceyi tanır.
- **Somut metin hâkimiyeti:** Belirli sahne, pasaj, şiir, bölüm veya gerekçeyi açıklayabilir.
- **Derin metin hâkimiyeti:** Eserin farklı kısımlarını ilişkilendirir ve yorumunu metne dayandırır.

Tek bir sorudan kesin sonuç çıkarılmaz. Farklı bölümlerden ve farklı soru türlerinden kanıt toplanır.
