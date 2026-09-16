# Workflow

Bu akışın temel ilkesi: **ham inceleme ayrı aşamada çıkarılır; nihai öğretmen kılavuzu daha sonra sentezlenir.**

## A. Kaynak hazırlığı

1. İncelenecek eserin tam metnini kaynak olarak hazırla.
2. Mümkünse tek baskı/sürüm kullan.
3. Yardımcı kaynaklar varsa ilk analizde devre dışı bırak.
4. `prompts/core/00-kaynak-ve-tur-kontrolu.md` ile kaynak ve tür kontrolünü yap.

## B. Ortak analiz

Sırayla çalıştır:

1. `01-yapi-ve-icerik-haritasi.md`
2. `02-ayirt-edici-ayrintilar.md`
3. `03-baglanti-ve-kronoloji.md`
4. Tür modülü (`prompts/types/`)
5. `04-sunum-sorulari.md`
6. `05-oz-denetim.md`

Her görevin çıktısını sakla. Uzun tek görevlerde ayrıntı ve tutarlılık kaybı yaşanabildiği için görevleri birleştirme.

## C. Tür modülü seçimi

- Roman veya tek uzun kurmaca: `roman-hikaye.md`
- Öykü kitabı: `roman-hikaye.md` içindeki öykü kitabı yönergelerini uygula.
- Tiyatro: `tiyatro.md`
- Şiir / şiir kitabı: `siir.md`
- Deneme / düşünce / fikir yazıları: `deneme-dusunce.md`
- Anı, günlük, gezi, biyografi, otobiyografi ve diğer kurmaca dışı anlatılar: `ani-biyografi-kurmaca-disi.md`

Bir eser melez yapıdaysa yalnız gerçekten gerekli iki modül kullanılabilir.

## D. Son sentez

Analiz çıktıları tek bir pakette toplanır. Son öğretmen kılavuzu şu sırayla hazırlanır:

1. 30 saniyelik öğretmen kartı
2. Eserin yapı/akış haritası
3. Temel kişi/kavram/konuşmacı haritası
4. Kısa özetlerde kaybolan ayırt edici ayrıntılar
5. Sunum soruları
6. Her soru için cevap, takip sorusu ve takip cevabı
7. Hazır soru grupları
8. Metne hâkimiyet rubriği
9. Kaçınılması gereken kolay sorular
10. Öz-denetimde düzeltilen/belirsiz noktalar

Nihai öğretmen dosyasında soru kategorisi, soru kodu veya teknik üretim etiketi gösterme. Öğretmenin göreceği yapı mümkün olduğunca sade olmalıdır.

## E. Bütün sınıf aynı eseri sunacaksa

Aynı eserin 25-30 kez yeniden özetlenmesini önlemek için `SINIF-SUNUM-SISTEMI.md` uygulanır.

Öz-denetim tamamlandıktan sonra:

1. `prompts/core/06-sinif-sunum-gorevleri.md` çalıştırılır.
2. `{{OGRENCI_SAYISI}}` yerine gerçek sınıf mevcudu yazılır.
3. Öğrenci sayısı kadar birbirinden farklı sunum görevi üretilir.
4. Ardından `prompts/core/07-sunum-dagitim-denetimi.md` çalıştırılır; ilk dağıtımdaki ağır başlıklar, dengesiz görevler, trivia kontrol soruları ve ifade bozuklukları düzeltilir.
5. Her görevde öğrenciden en az iki somut metin dayanağı ve eserin başka bir kısmıyla bağlantı istenir.
6. Her öğrenci için, sunum başlığının dışından en az bir kontrol sorusu hazırlanır.
7. Dağıtım `templates/sinif-sunum-dagitim-plani.md` düzeninde saklanabilir.

Özel sunum görevi öğrencinin yalnız o kısmından sorumlu olduğu anlamına gelmez. Bütün öğrenciler eserin tamamından sorumludur.

## F. Soru tasarım ilkesi

Güçlü soru şunlardan en az birini gerektirir:

- belirli bir sahne/pasaj/şiir/bölümü hatırlama,
- iki bölüm arasında bağlantı kurma,
- bir kararın veya düşüncenin gerekçesini açıklama,
- önce/sonra değişimini gösterme,
- yan kişi/kavram/örnek üzerinden eserin bütününe dönme,
- yorumu somut metinsel kanıtla destekleme.

Zayıf soru yalnızca şunları sorar:

- konu,
- ana fikir,
- başkahraman/yazar,
- genel tema,
- kitabın sonu,
- internetteki kısa bir özetten doğrudan alınabilecek bilgiler.

## G. Değerlendirme

Her öğrenciye mümkünse en az üç kontrol sorusu sor:

- 1 somut ayrıntı/sahne/yapı sorusu,
- 1 bağlantı/neden-sonuç/karşılaştırma sorusu,
- 1 yorum + metinsel dayanak sorusu.

Tek cevaba dayanarak "okudu/okumadı" sonucu verme. Amaç kanıt biriktirmektir.
