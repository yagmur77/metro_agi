Metro Rota Bulucu

Bu proje, bir şehir metrosundaki istasyonlar arasındaki en az aktarmalı ve en hızlı rotayı bulmak için geliştirilmiştir. Kullanıcılar, iki istasyon arasındaki en kısa yolu veya en az aktarma içeren güzergahı öğrenebilirler.


📌 Özellikler

✔️ İstasyon ve hat yönetimi (İstasyon ekleme, hatlar arası bağlantılar)

✔️ BFS Algoritması ile En Az Aktarma Bulma

✔️ A* Algoritması ile En Hızlı Rota Bulma

✔️ Örnek metro hattı ve test senaryoları



Kullanılan Teknolojiler ve Kütüphaneler

Kütüphane	Kullanım Amacı


collections.deque: BFS (Genişlik Öncelikli Arama) algoritması için kuyruk veri yapısı

heapq:	A* algoritmasında öncelik kuyruğu olarak kullanılır

defaultdict:	Hatları ve istasyonları kolayca gruplamak için

typing:	Tip ipuçları ile daha okunaklı kod yazımı için



🔍 Algoritmaların Çalışma Mantığı


1️⃣ BFS ile En Az Aktarma Bulma

📌 Amaç: En az sayıda aktarma ile hedefe ulaşmak

📌 Kullanılan Veri Yapısı: deque (çift taraflı kuyruk)



🔹 BFS, istasyonları seviyeler halinde ziyaret eder.

🔹 En kısa sürede hedefe ulaşan yolu döndürür.

🔹 En az aktarmaya sahip rotayı garanti eder.



BFS Örnek Adımları:

✅ Başlangıç istasyonunu kuyruk içine at

✅ Komşularını sırayla ziyaret et ve kuyruk içine ekle

✅ Hedefe ulaşıldığında rota döndür



2️⃣ A* Algoritması ile En Hızlı Rota

📌 Amaç: Toplam süresi en kısa olan rotayı bulmak

📌 Kullanılan Veri Yapısı: heapq (öncelik kuyruğu)



🔹 A* algoritması, her istasyon için toplam süreyi hesaplar ve en düşük süreliden başlayarak arama yapar.

🔹 Dijkstra algoritmasına benzer ancak önceliklendirme yaparak hızlı sonuç verir.



A* Örnek Adımları:

✅ Başlangıç istasyonunu öncelik kuyruğuna ekle

✅ Her komşuya geçerken süreyi hesapla ve kuyruğa ekle

✅ Hedef istasyona ulaşıldığında en kısa süreyi döndür




## Örnek Kullanım

```python
metro = MetroAgi()
metro.istasyon_ekle("K1", "Kızılay", "Kırmızı Hat")
metro.istasyon_ekle("K2", "Ulus", "Kırmızı Hat")
metro.baglanti_ekle("K1", "K2", 4)

rota = metro.en_az_aktarma_bul("K1", "K2")
print("En az aktarmalı rota:", " -> ".join(i.ad for i in rota))
