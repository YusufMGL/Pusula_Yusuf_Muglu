Proje Açıklaması

Bu proje, hasta verilerinin analizi ve temizlenmesi üzerine kuruludur. Amacı, eksik verilerin uygun şekilde doldurulması, kategorik değişkenlerin sayısal forma dönüştürülmesi ve sayısal özelliklerin görselleştirilerek
daha ileri analizlere hazır bir veri seti elde edilmesidir.

Proje kapsamında:

Veri seti incelenmiş, temel istatistikler çıkarılmıştır.

Eksik değerler uygun doldurma yöntemleriyle tamamlanmıştır.

Sayısal değişkenler için histogramlar, dağılımlar ve korelasyon ısı haritası oluşturulmuştur.

Kategorik değişkenler sayısallaştırılarak (Label Encoding) modele uygun hale getirilmiştir.

Metin formatındaki süre bilgileri (örn. “15 Seans”, “20 Dakika”) temizlenerek sayısal değerlere dönüştürülmüştür.

Kronik hastalık, alerji, tanı ve uygulama yerleri için sayısal özellikler türetilmiştir (kaç tane kayıt olduğu sayılmıştır).

Son olarak işlenmiş veri seti final_dataset.xlsx dosyası olarak kaydedilmiştir.

Bu proje, makine öğrenmesi modelleri için uygun, temiz ve analize hazır bir veri seti oluşturmayı amaçlamaktadır.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Kodun Çalışma Mantığı 

1- Kütüphanelerin yüklenmesi

pandas, numpy: veri işleme

matplotlib, seaborn: görselleştirme

sklearn kütüphaneleri: eksik değer doldurma, encoding, ölçekleme

2- Veri setinin okunması

Excel dosyası okunur ve satır-sütun bilgisi (shape) ekrana yazdırılır.

info() ve describe() ile veri tipleri ve temel istatistikler incelenir.

3- Sayısal kolonların seçilmesi ve görselleştirilmesi

Histogram grafikleri çizilerek sayısal kolonların dağılımları incelenir.

Yaş dağılımı ve kategorik kolonların (Cinsiyet, Kan Grubu) dağılımları görselleştirilir.

Korelasyon matrisi oluşturularak sayısal kolonlar arasındaki ilişkiler analiz edilir.

4- Veri temizleme

"TedaviSuresi" → “15 Seans” gibi verilerden sadece sayı kısmı alınarak TedaviSuresi_clean oluşturulur.

"UygulamaSuresi" → “20 Dakika” ifadesinden sayı kısmı alınarak UygulamaSuresi_clean oluşturulur.

Eksik değerler belirli kategorilerle doldurulur:

Cinsiyet → “Bilinmiyor”

KanGrubu → “Bilinmiyor”

KronikHastalik → “Yok”

Alerji → “Yok”

Bolum → “Bilinmiyor”

Tanilar, UygulamaYerleri → “Bilinmiyor”

5- Yeni değişkenlerin türetilmesi

Kronik hastalık, alerji, tanı ve uygulama yerleri virgülle ayrıldığı için, bunların sayısı çıkarılarak yeni sayısal kolonlar oluşturulmuştur (_Sayi).

6- Kategorik değişkenlerin sayısallaştırılması

Cinsiyet, KanGrubu, Uyruk, Bolum değişkenleri LabelEncoder ile sayısallaştırılmıştır (_enc).

7- Final veri setinin hazırlanması

Analiz ve modelleme için kullanılacak kolonlar seçilmiştir.

Bu temiz ve işlenmiş veri seti final_dataset.xlsx adıyla kaydedilmiştir.
--------------------------------------------------------------------------------------------------------------------------------------------------------------------
*Kullanılan kütüphaneler 
Pandas

Numpy

seaborn

matplotlib.pyplot

from sklearn.impute import SimpleImputer, KNNImputer

from sklearn.preprocessing import OneHotEncoder, LabelEncoder, StandardScaler


