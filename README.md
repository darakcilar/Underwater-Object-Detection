# Underwater Object Detection: CNN vs Transformer Comparison

Bu proje, su altı ortamındaki zorlu nesne tespiti görevlerinde geleneksel CNN mimarileri (YOLOv8, YOLO11) ile Transformer tabanlı (RT-DETR) mimarilerin performansını karşılaştırmaktadır. Çalışma, su altı kamuflajı ve fiziksel zorlukların oluşturduğu "Veri Tavanı" (Data Ceiling) kavramını akademik bir perspektifle ele almaktadır.

## 📊 Proje Özeti
Su altı ortamı; ışık kırılması, bulanıklık ve canlıların doğal kamuflaj yetenekleri nedeniyle bilgisayarlı görü için en zorlu alanlardan biridir. Projemizde Kaggle üzerindeki Aquarium Data COTS veri seti kullanılarak modellerin farklı mimari yaklaşımları test edilmiştir.

## 🔬 Karşılaştırılan Mimariler
- **YOLOv8-Nano (Baseline):** Referans noktası olarak kullanılan hafif CNN modeli.
- **YOLO11-Large (CNN):** Bölgesel (lokal) özellik çıkarmada optimize edilmiş modern CNN.
- **RT-DETR-Large (Transformer):** Öz-dikkat (self-attention) mekanizması ile global bağlamı kavrayan yeni nesil model.

## 📈 Temel Bulgular
- RT-DETR mimarisi, özellikle vatoz (stingray) gibi kamuflajlı canlılarda CNN mimarilerine göre %15'in üzerinde duyarlılık (Recall) artışı sağlamıştır.
- Tüm gelişmiş mimarilere rağmen genel başarının %78 bandında asılı kalması, su altı nesne tespitinde aşılamayan bir "Veri Tavanı" (Data Ceiling) olduğunu göstermektedir.

## 🛠 Kullanılan Teknolojiler
- Python
- Ultralytics (YOLOv8, YOLO11, RT-DETR)
- PyTorch
- Matplotlib (Veri görselleştirme)

## 📁 Sonuçlar
Confusion Matrix ve Karşılaştırmalı Grafik sonuçları `/results` klasöründe mevcuttur.

---# Underwater-Object-Detection

Bu akademik çalışma Furkan Darakçılar ve Mehmet Yağlı tarafından ortaklaşa geliştirilmiştir.
