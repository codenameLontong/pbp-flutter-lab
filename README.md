# Tugas 7: Elemen Dasar Flutter

Jeremy Mervin - 2106654675

## Jelaskan apa yang dimaksud dengan _stateless widget_ dan _stateful widget_ dan jelaskan perbedaan dari keduanya.

Sebuah *widget* disebut *stateless* jika tidak memiliki sebuah *state*. Artinya, tidak akan ada yang berubah dari widget tersebut (bersifat statik).

Sebuah *widget* disebut *stateful* jika memiliki sebuah *state*. Artinya, ia akan sendirinya berubah sesuai dengan *state* widget tersebut dari interaksi yang dilakukan.

## Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.

1. `Scaffold`: Struktur *layout* sederhana dengan *material design*.
2. `FloatingActionButton`: Tombol aksi yang biasanya muncul di bawah.
3. `Text`: Tulisan atau teks.
4. `AppBar`: Bar bertuliskan "Program Counter" yang berada di atas layar.
5. `Center`: Untuk mengatur posisi *widget* yang ada ke tengah.
6. `Padding`: Untuk membuat *inset*/*padding* pada sebuah widget.
7. `Column`: Membuat *widget* muncul dalam satu kolom.
8. `Row`: Membuat *widget* muncul dalam satu baris.
 

## Apa fungsi dari `setState()`? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.

`setState()` digunakan untuk memberitahu *framework* bahwa keadaan objeknya telah berubah, hal ini dikarenakan ada bagian dari interfasenya yang perlu diperbarui. Ini akan membuat *framework* mem-*build* interfacenya.

## Jelaskan perbedaan antara `const` dengan `final`.

Keduanya menandakan sebuah variabel yang konstan; tidak akan/dapat berubah. Bedanya terdapat pada isi `const` yang terdefinisi setelah program di-*compile* (*compile-time*). Sedangkan isi `final` terdefinsi saat progran dijalankan (*runtime*).

## Jelaskan bagaimana cara kamu mengimplementasikan _checklist_ di atas.

- Menambahkan tombol decrement.
  - Pada `floatingActionButton`, dibandingkan menggunakan `FloatingActionButton` secara langsung, `Column` dan `Padding` digunakan agar dua tombol dapat dimunculkan dengan elok.
  - Definisikan fungsi baru, `_decrementCounter()`, yang mengurangi counter.
- Membuat teks atas dinamis.
  - *Ternary operator* digunakan untuk mengubah tulisan dan warnanya (`_counter % 2 == 1 ? "..." : "..."`).
- Menyembunyikan tombol *decrement* saat counter bernilai.
  - *If-else* digunakan di sini (`if (_counter > 0)`).
  - Penyesuaian di *widget* `Row` perlu dilakukan lagi.
- Mengubabah judul halaman.
  - Nama judul halaman terdefinisi di *widget* pada `MyApp`.
- *Add*, *commit*, dan *push*.

# Tugas 8: Flutter Form

Jeremy Mervin - 2106654675

## Jelaskan perbedaan Navigator.push dan Navigator.pushReplacement

`Navigator.pushReplacement` akan me-replace laman yang sedang dibuka dengan dengan laman baru. Sedangkan `Navigator.push` akan menambahkan rute lain ke atas tumpukan screen (stack) yang sekarang.

```
                          RouteB
RouteA  Navigator.push()  RouteA
Route2  --------------->  Route2
Route1                    Route1

RouteA                               RouteB
Route2  Navigator.pushReplacement()  Route2
Route1  -------------------------->  Route1
```

## Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.

1. `Scaffold`: Struktur *layout* sederhana dengan *material design*. 
2. `Text`: Tulisan atau teks.
3. `AppBar`: Bar bertuliskan "Program Counter" yang berada di atas layar.
4. `Center`: Untuk mengatur posisi *widget* yang ada ke tengah.
5. `Padding`: Untuk membuat *inset*/*padding* pada sebuah widget.
6. `Column`: Membuat *widget* muncul dalam satu kolom.
7. `Row`: Membuat *widget* muncul dalam satu baris.
8. `Form` : Membuat form.
9. `Drawer` : Menu di sebelah kiri pada AppBar.
10. `TextFormField` : Tempat untuk data input bagi user (input field).
11. `ListTile` : Membuat inline widget yang berisi list.
12. `Container` : Contaniner untuk memuat widget lain.
13. `Expanded`: Untuk mengisi kekosongan space.
14. `MaterialPageRoute` : Untuk memuat ulang dan me-render laman.
15. `Spacer` : Membuat space pada flexible widget. 

## Sebutkan jenis-jenis event yang ada pada Flutter.

- `onPressed` -> Event yang terjadi ketika user telah selesai menekan
- `onTap` -> Event yang terjadi ketika sesaat setelah klik
- `onChanged` -> Event yang terjadi ketika ada perubahan

## Jelaskan bagaimana cara kerja Navigator dalam "mengganti" halaman dari aplikasi Flutter.

Navigator mengatur route dalam sebuah stack yang menyimpan berbagai laman disertai dengan animasi transisi. Hampir serupa seperti yang digunakan untuk next sama dengan Stack.push(), sedangkan untuk kembali sama dengan Stack.pop();

## Jelaskan bagaimana cara kamu mengimplementasikan _checklist_ di atas.

- Membuat drawer app pada `drawer.dart` yang berisi widget `Drawer` dengan routing ke `main.dart`, `form.dart`, `list.dart`
- Membuat budget model atau class pada `budget.dart`
- Membuat List pada `form.dart`, dan akan diterima oleh builder
- Membuat `list.dart` yang mengambil parameter dari budget model
- Render semua dengan menggunakan itemBuiler
- Styling sedikit dan merapihkan semua
- `Add`, `commit`, `push`

# Tugas 9: Integrasi Web Service pada Flutter

Jeremy Mervin - 2106654675

## Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?

Ya, bisa saja. Namun, cara tersebut sangat tidak disarankan. Hal ini disebabkan karena tipe data yang sudah dideklarasikan menjadi *useless* karena value json yang berupa *dynamic*, sehingga nantinya akan mudah terjadi error pada app yang telah dibuat. Oleh karena itu, sangat disarankan untuk menentukan model terlebih dahulu agar data yang diambil memiliki struktur yang baik dan mudah digunakan.

## Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.

1. `ListTile`: Digunakan untuk menampilkan data dalam bentuk list. 
2. `CircularProgressIndicator`: Menampilkan loading circle bar.
3. `Card`: Menampilkan data dalam bentuk kartu.
4. `FutureBuilder`: Digunakan untuk menampilkan data dari Future response API
5. `Checkbox`: Membuat sebuah checkbox yang mempunyai event onChange yang tertrigger setiap kali ada perubahan value di checkbox.

## Jelaskan mekanisme pengambilan data dari json hingga dapat ditampilkan pada Flutter.

- Menambahkan dependensi `http`
- Membuah model watchlist
- Melakukan Fetch JSON dari API
- Menyimpan JSON ke dalam model watchlist
- Menampilkan data dari model watchlist dengan memanfaatkan `FutureBuilder`

## Jelaskan bagaimana cara kamu mengimplementasikan _checklist_ di atas.

- Menambahkan routing ke `watchlist.dart` pada app drawer
- Menambahkan `*internet android permission*` pada `AndroidManifest.xml`.
- Membuat model untuk object JSON
- Membuat fungsi untuk *fetch* data 
- Render dengan menggunakan `FutureBuilder`
- Membuat `detail.dart` dan menambahkan attribut seperlunya
- Menghubungkan `detail.dart` dan `watchlist.dart`
- Styling sedikit dan merapihkan semua
- `Add`, `commit`, `push`
