# DBSCAN-ALGORTIHM
Writing of the dbscan algorithm, which makes classification based on density, without using the dbscan function from the library.
Yoğunluğa bağlı olarak sınıflandırma yapan dbscan algoritmasının sklearn kütüphanesinden dbscan kullanmadan yazımı.

DBSCAN:
Yoğunluk temelli sınıflandırmadır
Farklı büyüklükte farklı yoğunlukta ve sınıflar farklı şekillere sahip , gürültü var se db scan kullanılabilir.

Uygulanışı :
•	Seçilen bir noktanın yakınında olması istenilen sayıda komşu nokta sayısı belirlenir ve bunu sağlayan en küçük 𝜀 saptanır.
•	𝜀-çapındaki alanda komşu sayısını bul
•	Komşuları say, istenilen sayıya ulaştığında 𝜀 nu belirle.
•	Sonuç, temel mesafe (core distance) olarak isimlendirilir. 
•	Temel mesafesi küçük olan noktalar veri yoğunluğu yüksek (yüksek PDF), 
•	Temel mesafesi büyük olan noktalar ise düşük yoğunluklu boşlukları ifade eder. 
•	Minpts: çemberin içinde istenilen nokta sayısı. En az 3 seçilmeli. Veriye göre seçilir. Daha büyük değerler gürültüler ve büyük datalar için iyi sonuç verir.
•	Eps: Çember yarıçapı. K- Distance graph yöntemiyle belirlenir.
•	Parametreler (e, minpts) tamamlandıktan sonra algoritma verileri üç farklı gruba ayırır.
•	Core Points: p noktası core pointtir eğer p dahil Minpoint kadar yarıçap komşuluğu varsa

•	    Direkt Yoğunluk Erişimli (Direct density reachable, DDR): nokta ‘’A’’ nokta ‘’B’’ tarafından direkt yoğunluk erişimli (DDR) diye tanımlanır eğer nokta ‘’A’’ nokta ‘’B’’ nin ϵ komşuluk yarıçapında ise. VE nokta ‘’B’’ core point ise.
•	Yoğunluk Erişimli (Density reachable, DR): nota ‘’A nokta ‘’B’’ tarafından yoğunluk erişimli (DR) olarak tanımlanır, eğer nokta ‘’B’’ den nokta ‘’A’’ ya varan core pointler zinciri var ise. 


Algoritma rastgele bir noktadan başlar. Noktaları ziyaret eder ve core pointi belirler. DR olan başka noktayı aynı sınıfa ekler. Başka nokta kalmayınca kadar. Core point zincirinin sonundaki core point border pointtir. ve o border pointin çevresindeki bir nokta dc dir zincirdeki başka core pointe. 

Dezavantajları:
•	Yoğunlukta değişimler var ise gürültü noktaları tespit edilemez ve sınıflandırma yapamaz. 
•	Parametrelere karşı çok hassas. Doğru parametreleri belirlemek zordur.
•	Mesafe ölçümlerine göre hassasiyeti değişir. 

Avantajları
•	Sınıf sayısını önceden bilmeye gerek yok
•	Her şekilde olan sınıfı belirler, daire olmasına gerek yok.
•	Gürültü noktalarını belirler, outliers.
