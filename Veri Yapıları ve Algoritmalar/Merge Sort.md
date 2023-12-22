# Merge Sort Aşamaları



- [16, 21, 11, 8, 12, 22]
- [16, 21, 11]  [8, 12, 22] (Dizi ikiye bölündü)
- [16]  [21, 11]  [8]  [12, 22] (Her alt dizi tek elemanlı olana kadar bölündü)
- [16, 21]  [8, 11]  [12, 22] (Her alt dizi sıralandı ve birleştirildi)
- [8, 11, 16, 21]  [12, 22] (Her iki birleştirilmiş dizi sıralandı ve birleştirildi)
- [8, 11, 12, 16, 21, 22] (Son birleştirme)

### Big-O Gösterimi:
Merge Sort'un average, worst, ve best case Big-O gösterimi O(n log n)’dir. Bu, dizinin her elemanının logaritmik bir sayıda bölündüğü ve birleştirildiği anlamına gelir.