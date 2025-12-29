Proje Raporu: Raspberry Pi Destekli Yapay Zekâ Tabanlı Akıllı Soru-Cevap Sistemi (LLM + Embedding)
1. Proje Amacı

Bu projenin amacı, kullanıcıların doküman ve metinler üzerinde sorular sorabilmesini sağlayan, Raspberry Pi destekli bir yapay zekâ sisteminin geliştirilmesidir. Projede, metinler embedding yöntemiyle sayısal vektörlere dönüştürülmüş, veritabanında saklanmış ve bir LLM (Large Language Model) kullanılarak sorulara insan benzeri cevaplar üretilmiştir.
Sistem, düşük donanımlı bir cihaz (Raspberry Pi) ile bulut tabanlı GPU’nun iş birliğiyle çalışmaktadır. Bu sayede hem taşınabilirlik sağlanmış hem de yüksek performans elde edilmiştir.

2. Problem Tanımı

Günümüzde metin verileri hacim olarak çok büyük olup, anlamlı bilgi çıkarılması klasik yöntemlerle zordur. Metinlerin anlamsal olarak karşılaştırılması veya sorulara doğru yanıtların üretilmesi yüksek hesaplama gücü gerektirir.
Bu proje, metinlerin anlamını kaybetmeden sayısal hale getirilmesini ve kullanıcı sorularına doğru cevaplar üretecek bir sistem geliştirmeyi hedeflemektedir.

3. Proje Hedefleri

Dokümanların embedding yöntemiyle sayısal vektörlere dönüştürülmesi

Raspberry Pi üzerinde kullanıcı arayüzü oluşturulması

LLM ile sorulara anlamlı ve doğru cevapların üretilmesi

GPU destekli fine-tuning süreçlerinin uygulanması

Embedding vektörlerinin veritabanında saklanması

Sistem performansının nicel metrikler ile ölçülmesi (F1 skoru, doğruluk vb.)

4. Projenin Çözümü ve Kullanılan Teknolojiler

Python: NLP ve LLM kütüphanelerinin zengin desteği nedeniyle tercih edilmiştir.

Google Colab + GPU: Modelin eğitimi ve embedding işlemleri için kullanılmıştır. GPU sayesinde eğitim süresi ciddi ölçüde azaltılmıştır.

Raspberry Pi: Kullanıcı arayüzü ve hafif işlem görevleri için kullanılmıştır. Sistem mimarisi sayesinde ağır işlemler bulutta, sonuçlar Pi üzerinden görüntülenmektedir.

Veritabanı (ChromaDB / FAISS): Embedding vektörlerini hızlı ve düzenli şekilde saklamak için kullanılmıştır.

5. Odaklanılan Ana Başlık ve Kullanılan Yöntem

Projenin ana odak noktası metin embedding ve soru-cevap sistemleridir.

Dokümanlar parçalara bölünerek embedding’ler üretilmiştir.

Embedding vektörleri veritabanına kaydedilmiştir.

Kullanıcı sorusu ile veritabanındaki en benzer parça belirlenmiş ve LLM ile cevap üretilmiştir.

Yöntem:

Transformer tabanlı LLM kullanılmıştır.

Gerekli durumlarda model fine-tuning ile veri setine uyarlanmıştır.

6. Seçilen Dil Modeli ve Seçim Nedeni

Transformer tabanlı LLM seçilmiştir.

Seçim gerekçesi:

Metin bağlamını güçlü şekilde anlaması

Soru-cevap görevlerinde yüksek başarı

Akademik ve endüstriyel çalışmalarda yaygın kullanımı

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
