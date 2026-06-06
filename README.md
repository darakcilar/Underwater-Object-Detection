# Underwater Object Detection: CNN vs Transformer Comparison

Bu proje, su altı ortamındaki zorlu nesne tespiti görevlerinde geleneksel Evrişimli Sinir Ağları (YOLOv8, YOLO11) ile Vision Transformer tabanlı (RT-DETR) mimarilerin performansını karşılaştırmalı olarak analiz etmektedir. Çalışma, su altı kamuflajı ve fiziksel zorlukların derin öğrenme modelleri üzerinde oluşturduğu "Veri Tavanı" (Data Ceiling) kavramını akademik bir perspektifle ele almaktadır.

📄 **[Akademik Bildirinin Tamamını (PDF) Okumak İçin Tıklayınız](docs/Su_Alti_Nesne_Tespiti_Bildirisi.pdf)**

## 📊 Proje Özeti
Su altı ortamı; kısıtlı aydınlatma, ışık kırılması, bulanıklık, düşük kontrast ve deniz canlılarının doğal kamuflaj yetenekleri nedeniyle bilgisayarlı görü için en zorlu alanlardan biridir[cite: 1]. Projemizde, Kaggle üzerindeki 7 sınıflı **Aquarium Data COTS** veri seti kullanılarak, farklı mimari felsefelere sahip modellerin bu zorlu fiziksel koşullardaki tespit yetenekleri ve sınırları test edilmiştir[cite: 1].

## 🔬 Karşılaştırılan Mimariler
- **YOLOv8-Nano (Baseline):** Su altı ortamının temel zorluğunu ölçmek için referans noktası olarak kullanılan hafif sıklet CNN modeli[cite: 1].
- **YOLO11-Large (CNN):** Bölgesel (lokal) özellik çıkarmada optimize edilmiş, Test Zamanı Artırımı (TTA) ile desteklenen ve yanlış pozitifleri minimize eden modern CNN mimarisi[cite: 1].
- **RT-DETR-Large (Transformer):** Resmin sadece belirli piksellerine değil, öz-dikkat (self-attention) mekanizması ile görselin bütününe ve ilişkisel bağlama (global context) odaklanan uçtan uca yeni nesil model[cite: 1].

## 📈 Temel Deneysel Bulgular
- **Transformer Üstünlüğü:** RT-DETR-Large modeli, %78.68 ortalama hassasiyet (mAP@50) ve %76.36 duyarlılık (Recall) oranıyla, özellikle vatoz (stingray) gibi kuma gömülen kamuflajlı canlıları tespit etmede CNN rakiplerine açık bir üstünlük sağlamıştır[cite: 1].
- **CNN Kararlılığı:** YOLO11-Large modeli, %81.48 kesinlik (Precision) oranıyla emin olmadığı nesneleri işaretlemekten kaçınarak en düşük "Yanlış Alarm" (False Positive) oranını sunmuştur[cite: 1].
- **Veri Tavanı (Data Ceiling) Kanıtı:** En gelişmiş mimarilere ve hiperparametre optimizasyonlarına rağmen, genel başarı oranının %78 bandında asimptotik bir sınıra ulaşması; su altındaki temel problemin algoritmik yetersizlikten ziyade veri hacmi ve fiziksel koşullar olduğunu bilimsel olarak kanıtlamıştır[cite: 1].

## 🧠 Önceden Eğitilmiş Model Ağırlıkları (Pre-trained Weights)
Araştırmacılar ve geliştiriciler, eğitim sürecini tekrarlamak yerine projemizde elde edilen en başarılı model ağırlıklarını (`best.pt`) indirerek doğrudan test (inference) aşamasına geçebilirler:

🔗 **[Model Ağırlıklarını (Releases) İndirmek İçin Tıklayınız](https://github.com/darakcilar/Underwater-Object-Detection/releases/tag/v1.0)**

*(İndirdiğiniz `.pt` dosyalarını projenin ana dizininde kullanarak `ultralytics` kütüphanesi ile kendi su altı görsellerinizde anında tespit yapabilirsiniz.)*

## 🛠 Kullanılan Teknolojiler
- **Programlama:** Python
- **Derin Öğrenme Altyapısı:** PyTorch, Ultralytics (YOLOv8, YOLO11, RT-DETR)
- **Veri Görselleştirme:** Matplotlib, Seaborn
- **Donanım:** NVIDIA T4 GPU

## 📁 Dosya Yapısı ve Sonuçlar
- `/notebooks`: Eğitim, test ve doğrulama süreçlerini içeren detaylı `.ipynb` dosyaları.
- `/results`: Modellere ait Karmaşıklık Matrisleri (Confusion Matrix), kayıp (loss) grafikleri ve karşılaştırmalı performans analizleri.
- `/docs`: Projenin detaylı metodolojisini içeren akademik bildiri dosyası.

---
*Bu akademik çalışma Furkan Darakçılar ve Mehmet Yağlı tarafından Cumhuriyet Üniversitesi Bilgisayar Mühendisliği Bölümü kapsamında ortaklaşa geliştirilmiştir.*
