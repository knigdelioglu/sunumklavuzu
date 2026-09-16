# Sunum Kılavuzu

Öğrenci kitap sunumlarında **esere gerçek hâkimiyeti** ölçmek için kullanılan öğretmen odaklı bir çalışma deposudur.

Amaç, öğrencinin yapay zekâ kullanıp kullanmadığını tahmin etmek değildir. Amaç; öğrencinin yalnızca kısa bir özet bilip bilmediğini, eserin yapısını ve ayrıntılarını gerçekten takip edip etmediğini, yorumunu somut metinsel dayanaklarla destekleyip destekleyemediğini anlamaktır.

## Temel yaklaşım

1. Eserin tam metni kaynak olarak hazırlanır.
2. Uzun tek bir görev yerine `prompts/` altındaki kısa analiz görevleri sırayla çalıştırılır.
3. Önce ortak analiz görevleri uygulanır.
4. Eser türüne göre uygun tür modülü eklenir.
5. Analiz çıktıları tek dosyada toplanır ve kaynakla yeniden doğrulanır.
6. Bu incelemelerden öğretmen için kısa, kullanılabilir bir **Sunum Kontrol Dosyası** hazırlanır.
7. Bütün sınıf aynı eseri sunacaksa görevler en fazla 5 öğrencilik paketler hâlinde hazırlanır.
8. Paketler topluca denetlenir; tekrar eden, fazla kolay/zor veya dar/geniş görevler düzeltilir.
9. Son görevler öğrenciye verilecek sade **Sunum Görev Kartları**na dönüştürülür.
10. Sunum sonunda öğretmen, öğrencinin kendi kartının dışından bir kontrol sorusu sorar.

## Tek eser, farklı sunumlar

Aynı kitabı 25-30 öğrencinin art arda özetlemesi yerine her öğrenciye farklı bir sunum odağı verilebilir.

Her öğrenci:

- eserin tamamından sorumlu kalır,
- kendi sunumunda en az iki somut metin dayanağı kullanır,
- bu dayanaklar arasında bağlantı kurar,
- kendi sonucuna ulaşır,
- sunum sonunda kendi özel başlığının dışından bir kontrol sorusuna cevap verir.

Uzun tek üretim yerine sınıf 5'li paketlere ayrılır. Her paket için:

1. `06a-sunum-gorevleri-5li.md` — görevleri üretir.
2. `06b-kontrol-sorulari-5li.md` — kontrol sorularını ayrı üretir.
3. `06c-paket-denetimi.md` — yalnız o paketi son kez düzeltir.

30 kişilik örnek akış:

`1-5 → 6-10 → 11-15 → 16-20 → 21-25 → 26-30 → toplu denetim → öğrenci kartları`

Ayrıntılı yöntem: [`SINIF-SUNUM-SISTEMI.md`](SINIF-SUNUM-SISTEMI.md)

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
│   │   ├── 06a-sunum-gorevleri-5li.md
│   │   ├── 06b-kontrol-sorulari-5li.md
│   │   └── 06c-paket-denetimi.md
│   └── types/
│       ├── roman-hikaye.md
│       ├── tiyatro.md
│       ├── siir.md
│       ├── deneme-dusunce.md
│       └── ani-biyografi-kurmaca-disi.md
├── templates/
│   ├── ogretmen-sunum-kontrol-dosyasi.md
│   ├── sinif-sunum-dagitim-plani.md
│   └── ogrenci-sunum-gorev-karti.md
└── examples/
    └── osmancik/
        ├── README.md
        ├── kaynak-haritasi.md
        ├── ogretmen-sunum-kontrol-dosyasi.md
        ├── ogrenci-gorev-kartlari.md
        └── sunum-paketleri/
            ├── 00-genel-denetim.md
            └── paket-01 ... paket-06
```

## Hızlı kullanım

Önce `prompts/core/00-kaynak-ve-tur-kontrolu.md` çalıştırılır. Ardından ortak çekirdek promptlar sırayla uygulanır. Eserin türüne göre `prompts/types/` içinden **yalnız ilgili modül** kullanılır.

Analiz çıktıları mümkünse kaynak atıflarıyla saklanır. Son sentezde yalnız metnin desteklediği bilgiler kullanılmalı; belirsiz noktalar kesinleştirilmemelidir.

Bütün sınıf aynı eseri sunacaksa analiz ve öz-denetim tamamlandıktan sonra her 5'li öğrenci paketi için `06a → 06b → 06c` sırası uygulanır. Bütün paketler tamamlanınca görevler birlikte yeniden denetlenir ve öğrenciye dağıtılacak sürüm `templates/ogrenci-sunum-gorev-karti.md` yapısına dönüştürülür. Öğrenci kartında öğretmen kontrol sorusunun cevabı bulunmaz.

Kaynak-doğrulamalı tam örnek için: [`examples/osmancik/README.md`](examples/osmancik/README.md)

## Değerlendirme ilkesi

Öğrencinin bir cevabı şu dört düzeyde düşünülür:

- **Özet bilgisi:** Genel konu/tema düzeyinde kalır.
- **Temel metin bilgisi:** Doğru kişi, bölüm, olay veya düşünceyi tanır.
- **Somut metin hâkimiyeti:** Belirli sahne, pasaj, şiir, bölüm veya gerekçeyi açıklayabilir.
- **Derin metin hâkimiyeti:** Eserin farklı kısımlarını ilişkilendirir ve yorumunu metne dayandırır.

Tek bir sorudan kesin sonuç çıkarılmaz. Farklı bölümlerden ve farklı soru türlerinden kanıt toplanır.
