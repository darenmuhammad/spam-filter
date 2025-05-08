
# 🧩 JavaScript Regex & Array Methods Reference

Dokumentasi ini berisi penjelasan dasar tentang penggunaan **Regular Expressions (RegEx)** di JavaScript, serta metode terkait seperti `.match()`, `.test()`, dan `.some()`. Termasuk juga konsep penting seperti **alternate sequence**, **character class**, **capture group**, dan **non-capturing group**.

---

## 🔍 Regular Expressions (RegEx)

Regular Expression adalah pola teks yang digunakan untuk mencocokkan string. Ditulis di antara `/pattern/` atau dengan `new RegExp()`.

Contoh:
```javascript
const regex = /abc/;
regex.test("abc"); // true
```

---

## 📌 .match()

Digunakan untuk mencocokkan string terhadap regex dan mengembalikan **array hasil match** atau `null`.

```javascript
const str = "hello 123";
const result = str.match(/\d+/); // ["123"]
```

---

## 📌 .test()

Digunakan untuk menguji apakah sebuah string **mengandung pola**. Mengembalikan `true` atau `false`.

```javascript
const regex = /\d+/;
regex.test("abc123"); // true
```

---

## 🔁 Alternate Sequence (`|`)

Operator `|` digunakan untuk mencocokkan **salah satu dari beberapa pola**.

```javascript
const regex = /cat|dog/;
"i have a dog".match(regex); // ["dog"]
```

---

## ✅ .some()

Digunakan untuk menguji apakah **setidaknya satu elemen** dalam array memenuhi kondisi tertentu.

```javascript
const nums = [1, 2, 3, 4];
const hasEven = nums.some(n => n % 2 === 0); // true
```

---

## 🔣 Character Class

Character class memungkinkan pencocokan karakter tertentu:

| Class      | Artinya                        | Contoh               |
|------------|--------------------------------|----------------------|
| `\d`       | Angka 0–9                      | `/\d/` → `"3"`       |
| `\w`       | Karakter alfanumerik & `_`     | `/\w/` → `"a"`       |
| `\s`       | Spasi, tab, newline            | `/\s/` → `" "`       |
| `.`        | Semua karakter kecuali newline | `/./`  → `"a"`       |
| `[abc]`    | a, b, atau c                   | `/[abc]/`            |
| `[^abc]`   | Selain a, b, atau c            | `/[^abc]/`           |

---

## 🎯 Capture Group

Capture group menyimpan bagian dari string yang cocok dengan bagian tertentu dari regex.

```javascript
const regex = /Hello, (\w+)!/;
const result = "Hello, Alice!".match(regex);
// result[1] === "Alice"
```

- Dapat diakses lewat `result[n]` saat menggunakan `.match()`.

---

## 🚫 Non-Capturing Group

Digunakan untuk mengelompokkan tanpa menyimpan hasil match-nya.

```javascript
const regex = /(?:foo|bar)/;
"bar".match(regex); // ["bar"], tapi tidak bisa diakses dengan index
```

Gunakan `(?:...)` daripada `(...)` jika tidak perlu menyimpan hasil.

---

## 🧪 Perbandingan Cepat

| Fitur         | Tujuan                             | Hasil                         |
|---------------|------------------------------------|-------------------------------|
| `.match()`    | Mengambil hasil match              | Array atau null               |
| `.test()`     | Mengecek apakah match ada          | Boolean                       |
| `|`           | Alternatif (OR)                    | Salah satu cocok              |
| `.some()`     | Cek kondisi pada array             | Boolean                       |
| `()`          | Capture group                      | Disimpan di hasil match       |
| `(?:...)`     | Non-capturing group                | Tidak disimpan di hasil match |

---

## 📌 Kesimpulan

- RegEx sangat powerful untuk pencocokan pola string.
- `.match()` dan `.test()` adalah dua metode utama untuk regex di JavaScript.
- Gunakan `|` untuk alternatif, dan character class untuk fleksibilitas pencocokan.
- Capture group membantu mengambil bagian spesifik dari string.
- `.some()` digunakan dalam array, bukan regex, tapi berguna dalam konteks pencarian.

