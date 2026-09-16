# Analiz Promptları

Bu klasördeki promptlar tek tek çalıştırılmak üzere tasarlanmıştır. Hepsini tek mesaja birleştirmeyin.

## Sıra

1. `core/00-kaynak-ve-tur-kontrolu.md`
2. `core/01-yapi-ve-icerik-haritasi.md`
3. `core/02-ayirt-edici-ayrintilar.md`
4. `core/03-baglanti-ve-kronoloji.md`
5. `types/` içinden uygun tür modülü
6. `core/04-sunum-sorulari.md`
7. `core/05-oz-denetim.md`
8. Bütün sınıf aynı eseri sunacaksa 5'li paketler hâlinde:
   - `core/06a-sunum-gorevleri-5li.md`
   - `core/06b-kontrol-sorulari-5li.md`
   - `core/06c-paket-denetimi.md`

## Kural

Her promptta yalnız yüklenmiş eseri kaynak aldırın. Çalışma ortamında birden fazla kaynak varsa eser dışındaki kaynakları mümkünse devre dışı bırakın.

Tür modülü seçerken eseri zorla "roman" gibi ele almayın. Olay örgüsü olmayan bir eserde kronoloji, karakter gelişimi veya sahne soruları üretmek yerine o türün doğal yapısını ölçün.

## Sınıf sunum görevleri

Uzun tek üretim yerine sınıfı en fazla 5 öğrencilik paketlere ayırın.

Örnek 30 kişilik sınıf:

`1-5 → 6-10 → 11-15 → 16-20 → 21-25 → 26-30`

Her paket için aynı üç kısa adımı uygulayın:

1. `06a-sunum-gorevleri-5li.md` ile yalnız o paketin görevlerini üretin. `{{OGRENCI_ARALIGI}}` yerine örneğin `1-5` yazın.
2. `06b-kontrol-sorulari-5li.md` ile aynı öğrencilerin kontrol sorularını ayrı üretin.
3. `06c-paket-denetimi.md` ile yalnız o 5 kişilik paketi denetleyip son hâline getirin.

Sonraki pakete geçerken önceki görevler konuşma bağlamında kalsın. `06a` yeni görevlerin önceki paketleri tekrar etmemesini ister.

Sınıf mevcudu 5'in katı değilse son paket daha küçük olabilir; örneğin 28 kişilik sınıfta son paket `26-28` olur.

Bu yöntemin amacı öğrencilerin farklı kitaplar sunması değil; **aynı eseri farklı problemler ve bağlantılar üzerinden sunmasıdır.** Her öğrenci eserin tamamından sorumlu kalır.
