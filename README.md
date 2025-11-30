
Breast Cancer Wisconsin Veri Seti Üzerinde Klasik Makine Öğrenmesi Modelleri, PCA–LDA Boyut İndirgeme ve SHAP Açıklanabilirlik Analizi

Bu çalışma, Breast Cancer Wisconsin veri setini kullanarak benign ve malign tümör örneklerini makine öğrenmesi yöntemleriyle sınıflandırmayı, boyut indirgeme teknikleri ile veri yapısını sadeleştirmeyi ve en iyi modelin karar mekanizmasını açıklanabilir yapay zekâ (Explainable AI) teknikleriyle değerlendirmeyi amaçlamaktadır. Çalışma, veri ön işleme aşamasından model yorumlanmasına kadar uçtan uca sistematik bir yaklaşımı kapsamaktadır.

⸻

1. Veri Seti ve Hazırlık Süreci

Breast Cancer Wisconsin veri seti, tümör hücrelerine ait 30 morfolojik özelliği içermekte olup her örnek “benign” veya “malign” olarak etiketlenmiştir. Çalışmada ilk olarak veri yapısı incelenmiş, eksik değerler kontrol edilmiş, istatistiksel dağılımlar analiz edilmiştir. Aykırı değerler IQR yöntemiyle değerlendirilmiş ve gerektiğinde işlem görmüştür. Tüm özellikler StandardScaler kullanılarak ölçeklendirilmiştir.

⸻

2. Veri Setinin Eğitim–Doğrulama–Test Olarak Bölünmesi

Model performansını doğru değerlendirebilmek için veri seti:
	•	%70 Eğitim,
	•	%10 Doğrulama,
	•	%20 Test
şeklinde stratified sampling yöntemiyle bölümlendirilmiştir. Bu sayede sınıf dağılımının dengesi korunmuştur.

⸻

3. Boyut İndirgeme: PCA ve LDA

Çalışmada iki temel boyut indirgeme yaklaşımı uygulanmıştır:
	•	PCA (Principal Component Analysis):
Veri varyansını maksimum temsil eden bileşenler elde edilmiştir. PCA, özellikle görselleştirme ve gürültü azaltma süreçlerinde kullanılmıştır.
	•	LDA (Linear Discriminant Analysis):
Sınıf ayrımını maksimize edecek doğrusal kombinasyonlar çıkarılmıştır. LDA, özellikle doğrusal sınıflandırıcılarda performans artışı sağlamıştır.

Bu iki yöntem, ham veri ile birlikte üç farklı veri temsili oluşturmuştur:
Ham Veri, PCA-Verisi, LDA-Verisi.

⸻

4. Klasik Makine Öğrenmesi Modelleri

Her bir veri temsili üzerinde aşağıdaki algoritmalar eğitilmiştir:
	•	Logistic Regression
	•	Decision Tree Classifier
	•	Random Forest Classifier
	•	XGBoost Classifier
	•	Gaussian Naive Bayes

Toplamda 15 farklı model eğitilmiş ve doğrulama seti üzerinde karşılaştırılmıştır.

⸻

5. Modellerin Değerlendirilmesi

Validation Accuracy değerleri analiz edildiğinde, en güçlü performansı gösteren model:

 Random Forest (Ham Veri) — %100 Validation Accuracy

PCA ve LDA üzerinde de yüksek başarı sergilemiş, genel olarak en stabil modeli sunmuştur.
LDA doğrusal modellerin performansını artırırken PCA bazı modellerde küçük performans kayıplarına neden olmuştur.

Test seti performansında Random Forest modeli:
	•	Yüksek doğruluk,
	•	Malign sınıf için yüksek recall,
	•	Dengeli precision–recall ilişkisi,
	•	Güçlü ROC-AUC değeri
sunmuştur.

Bu sonuçlar modelin güvenilir ve tutarlı olduğunu göstermektedir.

⸻

6. SHAP ile Açıklanabilirlik Analizi

En iyi model olan Random Forest üzerinde SHAP analizi uygulanmıştır.
Amaç, modelin hangi özellikler üzerinden nasıl karar verdiğini yorumlayabilmektir.

SHAP summary plot ve feature importance analizleri sonucunda en etkili özellikler şunlardır:
	•	Feature 21
	•	Feature 20
	•	Feature 23
	•	Feature 10
	•	Feature 27

Bu özelliklerin tümör dokusunun morfolojik bozulmalarıyla ilişkili olması, biyolojik açıdan tutarlı sonuçlar sunmaktadır.
SHAP grafikleri modelin karar mekanizmasının anlaşılır ve şeffaf bir şekilde yorumlanmasını sağlamıştır.

⸻

7. Sonuç

Bu çalışma, Breast Cancer Wisconsin veri seti üzerinde gerçekleştirilen uçtan uca bir makine öğrenmesi sürecini kapsamlı biçimde ortaya koymaktadır.
Sonuçlar, klasik makine öğrenmesi modellerinin doğru ön işleme ve uygun boyut indirgeme teknikleriyle yüksek başarı gösterebileceğini ve açıklanabilirlik yöntemlerinin model güvenilirliğini artırdığını göstermektedir.

Random Forest, hem doğruluk hem açıklanabilirlik hem de genel istikrar açısından en başarılı model olmuştur.

⸻

Yazar Bilgileri

Huma Hümeyra Ünal
İstanbul Topkapı Üniversitesi
Yapay Zekâ Tezli Yüksek Lisans Programı
Machine Learning / Image Processing Researcher
GitHub: huma-humeyra-ai-tech

⸻

