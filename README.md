# onCaprazBagYirtigi-yapayzeka

ÖZET

Bu çalışmada, diz MRI görüntülerinden elde edilen veriler kullanılarak ön çapraz bağ (ACL)
yırtığı teşhisi yapılmıştır. Farklı makine öğrenimi ve derin öğrenme algoritmaları kullanılarak
sınıflandırma modelleri eğitilmiş ve performansları kapsamlı bir şekilde karşılaştırılmıştır.
Ancak, veri kümesinin dengesiz olması nedeniyle modellerin performansı sınırlı kalmıştır.
Bu sorunu çözmek için SMOTE (Synthetic Minority Over-sampling Technique) yöntemi
kullanılarak veri dengelenmiş ve modeller yeniden eğitilmiştir. Çalışma, ACL yırtığı teşhisi
için bilgisayar destekli karar verme sistemlerinin geliştirilmesine önemli katkılar
sağlamaktadır. Gelecekteki çalışmalarda, daha büyük ve daha dengeli veri kümeleri ile daha iyi
performans ve doğruluk elde edilebileceği düşünülmektedir.

GİRİŞ

Ön çapraz bağ (ACL) yırtıkları, diz eklemindeki en yaygın yaralanmalardan biridir ve doğru
teşhis edilmesi önemlidir. Geleneksel teşhis yöntemleri, genellikle klinik değerlendirme ve
MRI görüntülemesine dayanır. Ancak, bilgisayar destekli teşhis sistemleri, teşhis sürecini
hızlandırabilir ve doğruluğunu artırabilir. Bu projede, diz MRI görüntülerinden elde edilen
özelliklerin kullanılması ve çeşitli sınıflandırma algoritmaları ile ACL yırtığı teşhisi yapılması
amaçlanmıştır.
Önceki çalışmalarda, ACL yırtığı teşhisinde makine öğrenimi algoritmalarının kullanıldığı
görülmüştür. Bu çalışmanın amacı, farklı algoritmaların performanslarını karşılaştırmak ve en
uygun modeli belirlemektir. Ayrıca, veri kümesinin dengesizliğinin modellerin performansı
üzerindeki etkisi de incelenmiştir.

MATERYAL VE YÖNTEM

Veri Kümesi
Bu çalışmada kullanılan veri kümesi, diz MRI görüntülerinden elde edilen özellikleri
içermektedir. Veri kümesi aşağıdaki bağımsız değişkenleri içermektedir: `kneeLR`, `roiX`,
`roiY`, `roiZ`, `roiHeight`, `roiWidth`, `roiDepth`. Bağımlı değişken ise `aclDiagnosis` olup, 0,
1 veya 2 değerini almaktadır.
Veri kümesi, ACL yırtığı olan ve olmayan örnekler arasında dengesizdir, bu da modellerin
performansını etkilemektedir. Veri dengesizliğini gidermek için çeşitli teknikler uygulanmıştır.
Bunlar arasında örnek dengeleme yöntemleri (örneğin, SMOTE: Synthetic Minority Oversampling Technique) kullanılarak veri kümesi dengelenmiştir. Bu işlem, veri kümesindeki
azınlık sınıf örneklerinin sayısını artırarak gerçekleştirilmiştir. Veri kümesinin ilk beş verisi bu
şekilde;

Model
Çalışmada çeşitli makine öğrenimi algoritmaları kullanılmıştır: Destek Vektör Makineleri
(SVM), Karar Ağacı, Rastgele Orman, Gradyan Artırıcı, Yapay Sinir Ağları ve K-En Yakın
Komşu (KNN). Her bir model, dengelenmiş veri kümesi üzerinde eğitilmiş ve performansları
değerlendirilmiştir.

Performans Metrikleri
Modellerin performansını değerlendirmek için doğruluk, kesinlik, hassasiyet ve F1 skoru
metrikleri kullanılmıştır. Bu metrikler, sınıflandırma modellerinin başarısını ve hata oranlarını
göstermektedir.
BULGULAR
Bu çalışmada, diz MRI görüntülerinden elde edilen veriler kullanılarak ön çapraz bağ (ACL)
yırtığı teşhisi için çeşitli makine öğrenimi ve derin öğrenme algoritmaları uygulanmıştır. Farklı
modellerin doğruluk, kesinlik, hassasiyet ve F1 skoru metriklerine göre performansları aşağıda
detaylandırılmıştır.
Destek Vektör Makineleri (SVM)
SVM modeli, doğruluk ve F1 skoru açısından orta düzeyde performans göstermiştir. Kesinlik
metriği, modelin doğru pozitif oranını iyi bir seviyede yakaladığına işaret ederken, hassasiyetin
daha düşük olması modelin bazı doğru pozitifleri kaçırdığını göstermektedir.
Bunun dışında 0 için iyi sonuçlar verirken 1 ve 2 hedefleri için iyi sonuçlar elde edemediğimizi
görüyoruz.
Confusion matrisine bakıldığında verilerin dengesiz olduğunu daha iyi görüyoruz.
Karar Ağacı
Karar Ağacı modeli, doğruluk ve F1 skoru açısından düşük performans sergilemiştir. Kesinlik
yüksek olsa da, hassasiyetin düşük olması modelin hatalı pozitif tahminlerde bulunduğunu ve
genel doğruluk oranının düşük olduğunu göstermektedir.
Confusion matrisinde 0 doğru tahmini için diğerlerine oranla kötü sonuç verdiğini görüyoruz.
Rastgele Orman
Rastgele Orman modeli, genel olarak iyi bir performans göstermiştir. Doğruluk, kesinlik,
hassasiyet ve F1 skoru metrikleri dengeli ve yüksek seviyelerdedir, bu da modelin dengeli ve
doğru tahminlerde bulunduğunu göstermektedir.
Confusion matrisinde 1 ve 2 için kötü sonuçlar verdiğini görüyoruz.
Gradyan Arttırıcı (Gradient Boosting)
Gradyan Arttırıcı modeli, doğruluk ve F1 skoru açısından orta düzeyde performans
sergilemiştir. Kesinlik ve hassasiyet metriklerinin birbirine yakın olması, modelin doğruluğu
ve hatalı tahmin oranının dengeli olduğunu göstermektedir.
Confusion matrisinde 1 çıkışı için daha doğru sonuç üretmiş.
Yapay Sinir Ağları
Yapay Sinir Ağları modeli, doğruluk ve F1 skoru açısından ortalama bir performans
göstermiştir. Kesinlik ve hassasiyet metriklerinin birbirine yakın olması, modelin tahminlerinde
tutarlılık sağladığını göstermektedir.
Confusion matrisinde 2 çıkışı içibn hiç doğru yanıtlar verilmemiş.
K-En Yakın Komşu (KNN)
KNN modeli, doğruluk ve F1 skoru açısından orta düzeyde performans göstermiştir. Kesinlik
metriği yüksek olmasına rağmen, hassasiyetin daha düşük olması modelin bazı doğru pozitifleri
kaçırdığını göstermektedir.
Confusion matrisinde 1 çıkışı için daha doğru sonuç üretmiş.
1D Convolutional Neural Network (1D CNN)
1D CNN modeli, doğruluk ve F1 skoru açısından Yapay Sinir Ağları modeliyle benzer
performans sergilemiştir. Kesinlik ve hassasiyet metriklerinin birbirine yakın olması, modelin
genel performansının dengeli olduğunu göstermektedir.
Confusion matrisinde 1 ve 2 için kötü sonuçlar verdiğini görüyoruz.
Genel olarak, Rastgele Orman modeli en yüksek doğruluk (0.597826) ve F1 skoru (0.605027)
ile en iyi performansı göstermiştir. Diğer modeller de çeşitli metriklerde benzer performanslar
sergilemiş olup, belirli uygulama alanları için uygun olabilirler.
Aynı zamanda confusion matrislerinde gördüğümüz gibi veri çok dengesiz bu durumun
performansta çok büyük ölçüde sorun yarattıyor olabilir.
Doğruluk (Accuracy)
Rastgele Orman (Random Forest) en yüksek doğruluğa (%60 civarı) sahipken, Karar Ağacı
(Decision Tree) en düşük doğruluğa (%40 civarı) sahiptir. Diğer modellerin doğrulukları %50
civarındadır.
Kesinlik (Precision)
Tüm modellerin kesinlik değerleri %55 ile %62 arasında değişmektedir. En yüksek kesinlik
değerini Rastgele Orman modeli göstermektedir.
Hassasiyet (Recall)
Rastgele Orman modeli en yüksek hassasiyete sahip (%60 civarı). Karar Ağacı modeli en düşük
hassasiyete sahiptir (%40'ın altında). Diğer modellerin hassasiyetleri %50 civarındadır.
F1 Skoru
Rastgele Orman en yüksek F1 skoruna sahipken (%60 civarı), Karar Ağacı en düşük F1 skoruna
sahiptir (%40'ın altında). Diğer modellerin F1 skorları %50 civarındadır.
Rastgele Orman (Random Forest) modeli genel olarak en iyi performansı sergilemektedir. Bu
model, hem doğruluk, hem kesinlik, hem de hassasiyet açısından diğer modellerden üstün
görünmektedir. Karar Ağacı (Decision Tree) modeli ise en düşük performansı göstermektedir.
Bu modelin düşük doğruluk, hassasiyet ve F1 skoru, modelin sınıflandırma görevinde yetersiz
kaldığını göstermektedir.
SONUÇ
Bu çalışmada, çeşitli makine öğrenimi algoritmalarının ACL yırtığı teşhisi için performansları
değerlendirilmiştir. Karar Ağacı ve Rastgele Orman modelleri en yüksek performansı
sergilemesi, gelecekteki çalışmalar için bu modelin kullanılmasının uygun olabileceğini
göstermektedir. Ancak, veri kümesinin dengesiz olması modellerin performansını etkilemiştir.
Gelecekteki çalışmalarda, daha büyük ve dengeli veri kümeleri ile farklı özelliklerin
kullanılması ile modellerin performanslarının daha da iyileştirilebileceği düşünülmektedir.
Ayrıca, veri ön işleme ve dengeleme tekniklerinin daha etkin kullanımı ile sonuçlar daha da
iyileştirilebilir.
