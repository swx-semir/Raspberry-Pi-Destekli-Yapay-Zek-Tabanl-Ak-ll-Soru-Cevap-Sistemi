Proje: Raspberry Pi Destekli Yapay Zekâ Tabanlı Akıllı Soru-Cevap Sistemi (LLM + Embedding)
1. Proje Amacı

2. <img width="1280" height="720" alt="GPIO-diagram-Raspberry-Pi-4" src="https://github.com/user-attachments/assets/530636dc-f515-47b9-8345-4a77eb721393" />
![e1962cae-1679-4f05-9e7e-3fca7b3565da](https://github.com/user-attachments/assets/786c8490-f2d2-48f6-bcaa-546825d8e791)


Bu projenin amacı, kullanıcıların doküman ve metinler üzerinde sorular sorabilmesini sağlayan, Raspberry Pi destekli bir yapay zekâ sisteminin geliştirilmesidir. Projede, metinler embedding yöntemiyle sayısal vektörlere dönüştürülmüş, veritabanında saklanmış ve bir LLM (Large Language Model) kullanılarak sorulara insan benzeri cevaplar üretilmiştir.
Sistem, düşük donanımlı bir cihaz (Raspberry Pi) ile bulut tabanlı GPU’nun iş birliğiyle çalışmaktadır. Bu sayede hem taşınabilirlik sağlanmış hem de yüksek performans elde edilmiştir.
![raspberry-pi-projects](https://github.com/user-attachments/assets/29fae584-b98d-4155-8aba-c600fb542c34)
2. Problem Tanımı

Günümüzde metin verileri hacim olarak çok büyük olup, anlamlı bilgi çıkarılması klasik yöntemlerle zordur. Metinlerin anlamsal olarak karşılaştırılması veya sorulara doğru yanıtların üretilmesi yüksek hesaplama gücü gerektirir.
Bu proje, metinlerin anlamını kaybetmeden sayısal hale getirilmesini ve kullanıcı sorularına doğru cevaplar üretecek bir sistem geliştirmeyi hedeflemektedir.

3. Proje Hedefleri
![e1d58038-9fb4-4856-bff9-10e7e09a8b81](https://github.com/user-attachments/assets/58d8018b-9659-4ccd-ba9f-aa0e18c71718)

Dokümanların embedding yöntemiyle sayısal vektörlere dönüştürülmesi

Raspberry Pi üzerinde kullanıcı arayüzü oluşturulması

LLM ile sorulara anlamlı ve doğru cevapların üretilmesi

GPU destekli fine-tuning süreçlerinin uygulanması

Embedding vektörlerinin veritabanında saklanması

Sistem performansının nicel metrikler ile ölçülmesi (F1 skoru, doğruluk vb.)

4. Projenin Çözümü ve Kullanılan Teknolojiler
![a9f3d349-1808-44ee-ba86-c93a47447c17](https://github.com/user-attachments/assets/4174a31a-5526-4a87-8871-88d6bbbf3966)

Python: NLP ve LLM kütüphanelerinin zengin desteği nedeniyle tercih edilmiştir.

Google Colab + GPU: Modelin eğitimi ve embedding işlemleri için kullanılmıştır. GPU sayesinde eğitim süresi ciddi ölçüde azaltılmıştır.

Raspberry Pi: Kullanıcı arayüzü ve hafif işlem görevleri için kullanılmıştır. Sistem mimarisi sayesinde ağır işlemler bulutta, sonuçlar Pi üzerinden görüntülenmektedir.

Veritabanı (ChromaDB / FAISS): Embedding vektörlerini hızlı ve düzenli şekilde saklamak için kullanılmıştır.

5. Odaklanılan Ana Başlık ve Kullanılan Yöntem
![1ed650a4-2533-49f9-af59-3ab5cd820d6c](https://github.com/user-attachments/assets/0ad6403a-dddc-4464-bedd-b89a31bc30f4)

Projenin ana odak noktası metin embedding ve soru-cevap sistemleridir.

Dokümanlar parçalara bölünerek embedding’ler üretilmiştir.

Embedding vektörleri veritabanına kaydedilmiştir.

Kullanıcı sorusu ile veritabanındaki en benzer parça belirlenmiş ve LLM ile cevap üretilmiştir.

Yöntem:

Transformer tabanlı LLM kullanılmıştır.

Gerekli durumlarda model fine-tuning ile veri setine uyarlanmıştır.
![e1962cae-1679-4f05-9e7e-3fca7b3565da](https://github.com/user-attachments/assets/43f46c8d-24f8-4bb6-b30e-b99a19896996)

6. Seçilen Dil Modeli ve Seçim Nedeni

Transformer tabanlı LLM seçilmiştir.

Seçim gerekçesi:

Metin bağlamını güçlü şekilde anlaması

Soru-cevap görevlerinde yüksek başarı

Akademik ve endüstriyel çalışmalarda yaygın kullanımı

<img width="1280" height="720" alt="GPIO-diagram-Raspberry-Pi-4" src="https://github.com/user-attachments/assets/a2832b8f-0ed5-4f30-a99c-d2e279779717" />

7. Embedding Oluşturma Süreci

Dokümanlar parçalara bölündü (chunking)

Her parça embedding’e dönüştürüldü

Vektörler veritabanında saklandı

Neden embedding?

Metinler arası anlamsal benzerliği korur

Soru ile doküman arasındaki ilişkiyi sayısal olarak ölçer

8. Veritabanı Seçimi ve Gerekçesi

ChromaDB / FAISS kullanılmıştır.

Seçim nedeni:

Vektör tabanlı sorgulama desteği

Hızlı ve verimli benzerlik araması

Raspberry Pi + bulut mimarisi ile uyum

9. Nihai Değerlendirme (Nicel Veriler)

Top-k Retrieval Accuracy

F1 Skoru

Precision ve Recall

Testler farklı sorular ve dokümanlarla gerçekleştirilmiş, modelin doğru ve anlamlı cevaplar ürettiği gözlemlenmiştir.
