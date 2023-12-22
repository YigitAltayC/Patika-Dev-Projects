# BST Aşamaları

- Eklenen: 7 (root)

```java
    7
```    

- Eklenen: 5 (5 < 7, sol)

```java
    7
   /
  5
```

- Eklenen: 1 (1 < 7, sol)

```java
    7
   /
  5
 /
1
```

- Eklenen: 8 (8 > 7, sağ)

```java
    7
   / \
  5   8
 / 
1  

```
- Eklenen: 3 (3 < 7, sol, 3 > 1, sağ)

```java
    7
   / \
  5   8
 / \
1   3
```

- Eklenen: 6 (6 < 7, sol, 6 > 5, sağ)

```java
    7
   / \
  5   8
 / \ /
1  3 6

```
- Eklenen: 0 (0 < 7, sol, 0 < 5, sol)

```java
    7
   / \
  5   8
 / \ /
1  3 6
 /
0
```

- Eklenen: 9 (9 > 7, sağ, 9 > 8, sağ)

```java
    7
   / \
  5   8
 / \ / \
1  3 6  9
 /
0
```

- Eklenen: 4 (4 < 7, sol, 4 > 5, sağ, 4 < 3, sol)

```java
    7
   / \
  5   8
 / \ / \
1  3 6  9
 / \
0   4
```
- Eklenen: 2 (2 < 7, sol, 2 > 5, sağ, 2 < 3, sol, 2 > 1, sağ)

```java

    7
   / \
  5   8
 / \ / \
1  3 6  9
 / \
0   4
    /
   2
```
