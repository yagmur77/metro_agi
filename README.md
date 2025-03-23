# metro_agi
# Metro Ağı Rota Bulucu

Bu proje, bir metro ağı üzerinde **en az aktarma yapan** ve **en hızlı rotayı bulan** algoritmaları içermektedir.

## Kullanılan Teknolojiler ve Kütüphaneler

- **Python 3**: Programlama dili
- **collections.deque**: BFS algoritması için hızlı kuyruk işlemleri sağlar.
- **heapq**: A* algoritmasında öncelik kuyruğu için kullanılır.
- **defaultdict**: Veri yapılarını daha kolay yönetmek için kullanılmıştır.

## Algoritmaların Çalışma Mantığı

### **BFS (Genişlik Öncelikli Arama) - En Az Aktarmalı Rota**
- Metro ağı düğüm-temelli bir graf olarak ele alınır.
- BFS kullanılarak, başlangıçtan hedefe en az aktarma yapan rota bulunur.
- Kuyruk yapısı (`deque`) kullanılarak en kısa yolu bulmak hızlı hale getirilmiştir.

### **A* (A-Star) Algoritması - En Hızlı Rota**
- A* algoritması, en kısa sürede ulaşımı sağlayan rota için kullanılır.
- **heapq** ile öncelik kuyruğu uygulanmıştır.
- Her istasyon için mevcut süreye ek olarak komşulara olan mesafe hesaplanarak en hızlı yol bulunur.

## Örnek Kullanım

```python
metro = MetroAgi()
metro.istasyon_ekle("K1", "Kızılay", "Kırmızı Hat")
metro.istasyon_ekle("K2", "Ulus", "Kırmızı Hat")
metro.baglanti_ekle("K1", "K2", 4)

rota = metro.en_az_aktarma_bul("K1", "K2")
print("En az aktarmalı rota:", " -> ".join(i.ad for i in rota))
