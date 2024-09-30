# Sentiment_Analysis_for_Amazon_Reviews
# Amazon Yorumları Duygu Analizi

## Proje Tanımı
Bu proje, Kozmos markası için Amazon üzerinden yapılan müşteri yorumlarının duygu analizini gerçekleştirmeyi amaçlamaktadır. Amacımız, müşteri geri bildirimlerini analiz ederek ürünlerin özelliklerini geliştirmek ve sonuçta satışları artırmaktır. Proje, doğal dil işleme teknikleri ve makine öğrenimi algoritmaları kullanılarak geliştirilecektir.

##İş Problemi
Kozmos, ev tekstili ve günlük giyim ürünleri satan bir firmadır. Müşteri yorumları, ürünlerin kalitesini ve müşteri memnuniyetini anlamak için önemli bir kaynaktır. Yorumların analiz edilmesi, alınan geri bildirimlere dayalı olarak ürün geliştirme süreçlerini destekleyecek ve satışları artırma stratejilerine katkıda bulunacaktır.

## Veri Seti
Veri seti, Amazon'da belirli bir ürün grubuna ait müşteri yorumlarını içermektedir. Aşağıdaki değişkenlerden oluşmaktadır:

-**Review**: Ürüne yönelik yapılan yorum metni.

-**Title**: Yorumun başlığı.

-**Helpful**: Yorumu faydalı bulan kullanıcı sayısı.

-**Star**: Ürüne verilen yıldız sayısı (1-5 arası).

## Kütüphaneler
Projenin başında aşağıdaki kütüphaneler kullanılmaktadır:

- **Pandas**
- **matplotlib**
- **wordcloud**
- **nltk**
- **scikit-learn** 

##############################################################
# Görevler
##############################################################

# Görev 1: Metin ön işleme işlemleri.
        # 1. amazon.xlsx datasını okutunuz.
        # 2. "Review" değişkeni üzerinde
            # a. Tüm harfleri küçük harfe çeviriniz
            # b. Noktalama işaretlerini çıkarınız
            # c. Yorumlarda bulunan sayısal ifadeleri çıkarınız
            # d. Bilgi içermeyen kelimeleri (stopwords) veriden çıkarınız
            # e. 1000'den az geçen kelimeleri veriden çıkarınız
            # f. Lemmatization işlemini uygulayınız

# Görev 2: Metin Görselleştirme
    # Adım 1: Barplot görselleştirme işlemi
                  # a. "Review" değişkeninin içerdiği kelimeleri frekanslarını hesaplayınız, tf olarak kaydediniz
                  # b. tf dataframe'inin sütunlarını yeniden adlandırınız: "words", "tf" şeklinde
                  # c. "tf" değişkeninin değeri 500'den çok olanlara göre filtreleme işlemi yaparak barplot ile görselleştirme işlemini tamamlayınız.

    # Adım 2: WordCloud görselleştirme işlemi
                 # a. "Review" değişkeninin içerdiği tüm kelimeleri "text" isminde string olarak kaydediniz
                 # b. WordCloud kullanarak şablon şeklinizi belirleyip kaydediniz
                 # c. Kaydettiğiniz wordcloud'u ilk adımda oluşturduğunuz string ile generate ediniz.
                 # d. Görselleştirme adımlarını tamamlayınız. (figure, imshow, axis, show)

# Görev 3: Duygu Analizi
    # Adım 1: Python içerisindeki NLTK paketinde tanımlanmış olan SentimentIntensityAnalyzer nesnesini oluşturunuz

    # Adım 2: SentimentIntensityAnalyzer nesnesi ile polarite puanlarının incelenmesi
                # a. "Review" değişkeninin ilk 10 gözlemi için polarity_scores() hesaplayınız
                # b. İncelenen ilk 10 gözlem için compund skorlarına göre filtrelenerek tekrar gözlemleyiniz
                # c. 10 gözlem için compound skorları 0'dan büyükse "pos" değilse "neg" şeklinde güncelleyiniz
                # d. "Review" değişkenindeki tüm gözlemler için pos-neg atamasını yaparak yeni bir değişken olarak dataframe'e ekleyiniz

### NOT: SentimentIntensityAnalyzer ile yorumları etiketleyerek, yorum sınıflandırma makine öğrenmesi modeli için bağımlı değişken oluşturulmuş oldu.


# Görev 4: Makine öğrenmesine hazırlık!
    # Adım 1: Bağımlı ve bağımsız değişkenlerimizi belirleyerek datayı train test olara ayırınız.
    # Adım 2: Makine öğrenmesi modeline verileri verebilmemiz için temsil şekillerini sayısala çevirmemiz gerekmekte.
                  # a. TfidfVectorizer kullanarak bir nesne oluşturunuz.
                  # b. Daha önce ayırmış olduğumuz train datamızı kullanarak oluşturduğumuz nesneye fit ediniz.
                  # c. Oluşturmuş olduğumuz vektörü train ve test datalarına transform işlemini uygulayıp kaydediniz.

# Görev 5: Modelleme (Lojistik Regresyon)
    # Adım 1: Lojistik regresyon modelini kurarak train dataları ile fit ediniz.
    # Adım 2: Kurmuş olduğunuz model ile tahmin işlemleri gerçekleştiriniz.
        # a. Predict fonksiyonu ile test datasını tahmin ederek kaydediniz.
        # b. classification_report ile tahmin sonuçlarınızı raporlayıp gözlemleyiniz.
        # c. cross validation fonksiyonunu kullanarak ortalama accuracy değerini hesaplayınız
    # Adım 3: Veride bulunan yorumlardan ratgele seçerek modele sorulması.
        # a. sample fonksiyonu ile "Review" değişkeni içerisinden örneklem seçierek yeni bir değere atayınız
        # b. Elde ettiğiniz örneklemi modelin tahmin edebilmesi için CountVectorizer ile vektörleştiriniz.
        # c. Vektörleştirdiğiniz örneklemi fit ve transform işlemlerini yaparak kaydediniz.
        # d. Kurmuş olduğunuz modele örneklemi vererek tahmin sonucunu kaydediniz.
        # e. Örneklemi ve tahmin sonucunu ekrana yazdırınız.

# Görev 6: Modelleme (Random Forest)
    # Adım 1: Random Forest modeliiletahminsonuçlarınıngözlenmesi;
                 # a. RandomForestClassifier modelini kurup fit ediniz.
                 # b. cross validation fonksiyonunu kullanarak ortalama accuracy değerini hesaplayınız
                 # c. Lojistik regresyon modeli ile sonuçları karşılaştırınız.


## Sonuç
Bu proje sonucunda, müşteri yorumları üzerinde yapılan duygu analizi, ürün geliştirme süreçlerine önemli katkılarda bulunmuştur. Elde edilen Random Forest modeli, test verisi üzerinde %89.88 doğruluk oranı ile etkili bir performans sergilemiştir.
