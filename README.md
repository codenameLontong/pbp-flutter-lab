# Tugas 7: Elemen Dasar Flutter

Jeremy Mervin - 2106654675

## Jelaskan apa yang dimaksud dengan _stateless widget_ dan _stateful widget_ dan jelaskan perbedaan dari keduanya.

Sebuah *widget* disebut *stateless* jika tidak memiliki sebuah *state*. Artinya, tidak akan ada yang berubah dari widget tersebut (bersifat statik).

Sebuah *widget* disebut *stateful* jika memiliki sebuah *state*. Artinya, ia akan sendirinya berubah sesuai dengan *state* widget tersebut dari interaksi yang dilakukan.

## Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.

1. `Scaffold`: Struktur *layout* sederhana dengan *material design*.
2. `FloatingActionButton`: Tombol aksi melayang yang biasanya muncul di bawah (atau kanan bawah).
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
