# Tugas Praktikum Mobile - Pertemuan 11

Nama  : Muhammad Sultan Alhakim

NIM   : H1D022105

Shift  : A

Proses CRUD (Create, Read, Update, Delete) dalam kode ini digunakan untuk mengelola data todo yang tersimpan di Firebase Firestore.

1.  Proses Read

![image](https://github.com/user-attachments/assets/1a594f49-26b1-4c13-9674-26518ed9a5cb)
![image](https://github.com/user-attachments/assets/b3fbb6d4-264e-4341-8751-bfbfc80e8393)

Pada gambar di atas menampilkan proses read yang dijalankan setiap kali aplikasi dimuat atau saat pengguna menyegarkan halaman dan menampilkan data dari Firebase. Data todo diambil dari Firestore melalui fungsi firestoreService.getTodos, yang dipanggil oleh loadTodos. Data yang diambil kemudian dibagi menjadi dua kategori menggunakan fungsi computed: activeTodos untuk daftar tugas yang belum selesai, dan completedTodos untuk daftar tugas yang sudah diselesaikan.

2. Proses Create dan Update

![image](https://github.com/user-attachments/assets/e74a2bca-9eb4-49a7-b643-8d3cfb4f2cfb)
![image](https://github.com/user-attachments/assets/8debc46b-ff64-4758-a6d7-83d4c92232e3)

Pada gambar di atas menampilkan proses create ketika pengguna menambahkan todo baru melalui tombol tambah di bagian kanan bawah aplikasi. Setelah tombol ditekan, sebuah modal input akan terbuka, memungkinkan pengguna untuk mengisi judul dan deskripsi. Data yang diinput kemudian dikirimkan ke fungsi handleSubmit, yang memanggil firestoreService.addTodo untuk menyimpan data tersebut ke Firestore. Jika berhasil, daftar todo akan diperbarui menggunakan fungsi loadTodos.

Kemudian terdapat juga untuk proses Update, pengguna dapat mengubah data atau status todo. Ketika tombol edit ditekan, fungsi handleEdit dipanggil untuk membuka modal input dengan data yang sudah ada. Setelah perubahan disimpan, fungsi handleSubmit memanggil firestoreService.updateTodo untuk memperbarui data di Firestore. Selain itu, pengguna juga dapat mengubah status tugas (aktif atau selesai) melalui tombol status, yang memanggil fungsi handleStatus untuk memperbarui status tugas di Firestore.

3. Proses Navigation Todo

![image](https://github.com/user-attachments/assets/4634807c-3dec-4af5-bd16-e17a4bebd798)
![image](https://github.com/user-attachments/assets/af89ab63-b207-4d77-840b-d8aaa7e23394)

Pada kedua gambar ini terjadi ketika kita menggeser todo secara horizontal, maka akan terlihat menu untuk menghapus, mengedit, dan menyelesaikan todo.

4. Proses Delete dan Complete Todo

![image](https://github.com/user-attachments/assets/07c17e06-e5db-4976-b9a0-a9d39bed0ad3)
![image](https://github.com/user-attachments/assets/78616948-b431-4af3-ad6a-6ca910f95d37)


Terakhir, pada gambar ini terdapat proses delete memungkinkan pengguna untuk menghapus tugas. Saat tombol hapus ditekan, fungsi handleDelete dipanggil untuk menghapus data todo yang sesuai menggunakan firestoreService.deleteTodo. Setelah berhasil, daftar tugas diperbarui dengan memanggil kembali fungsi loadTodos. Semua proses ini disertai pemberitahuan (toast) untuk memberikan umpan balik kepada pengguna, memastikan pengalaman penggunaan yang informatif dan responsif.

Kemudian terdapat juga proses bahwa proses menyelesaikan todo berhasil dilakukan, sehingga data terupdate dan langsung berpindah dari activeTodos ke completedTodos.

![image](https://github.com/user-attachments/assets/e986d7f1-7d8c-4631-b5ef-71bb4fff9d12)
