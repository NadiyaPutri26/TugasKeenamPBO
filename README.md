# TugasKeenamPBO
Praktikum ini dibuat untuk memenuhi tugas PBO dalam menerapkan konsep CRUD dengan dialog modal.

Dosen pengampu: Bayu Adhi Nugroho, Ph. D.
# Konsep CRUD dengan Dialog Modal
## Insert/ Create
Dalam praktikum ini untuk _button_ "Insert" akan dibuat dengan dialog modal. Dimana, untuk _code_ berikut digunakan dalam _class_ di JFrame utama yakni TokoBunga untuk menunjukkan bahwa _button_ "Insert" akan menggunakan Dialog Modal "Insert":

        private void BtnInsertActionPerformed(java.awt.event.ActionEvent evt) {                                          

        InsertDialog dialog = new InsertDialog(new java.awt.Frame(), true);
        dialog.setVisible(true);
        showTable();
    } 

Berikut adalah _constructor_ yang ada dalam _class_ "InsertDialog" untuk membuat _code_ dialog modalnya:

        public InsertDialog(java.awt.Frame parent, boolean modal) {
        
        super(parent, modal);
        
        initComponents();
         }

Sehingga dialog modal "InsertDialog" dipanggil saat tombol Insert ditekan dan digunakan untuk menambahkan data baru ke tabel. Setelah dialog ditutup, tabel utama diperbarui dengan showTable() untuk memperbarui tampilan tabel.
## Select/ Read
Untuk "Select" sendiri tidak menggunakan dialog modal, karena dia akan masuk di baris _method_ **showTable();** (tercantum dalam _code_ di class TokoBunga). 

Method **showTable();** digunakan untuk mengambil data dari _database_ tabel bunga dan menampilkannya dalam JTable di JFrame utama. Dengan cara ini, data terbaru akan selalu terlihat setelah dilakukan operasi _Insert, Update_, maupun _Delete_.
## Update
Dalam praktikum ini untuk _button_ "Update" akan dibuat dengan dialog modal. Dimana, untuk _code_ berikut digunakan dalam _class_ di JFrame utama yakni TokoBunga untuk menunjukkan bahwa _button_ "Update" akan menggunakan Dialog Modal "Update":

        private void BtnUpdateActionPerformed(java.awt.event.ActionEvent evt) {                                          
        int row = jTable1.getSelectedRow();
        if (row == -1) {
            JOptionPane.showMessageDialog(this, "Pilih data dulu dari tabel!");
            return;
        }

        String idBunga = jTable1.getValueAt(row, 0).toString();
        String namaBunga = jTable1.getValueAt(row, 1).toString();
        String kategori = jTable1.getValueAt(row, 2).toString();
        String deskripsi = jTable1.getValueAt(row, 3).toString();
        String harga = jTable1.getValueAt(row, 4).toString();
        String stok = jTable1.getValueAt(row, 5).toString();
        String ukuran = jTable1.getValueAt(row, 6).toString();

        UpdateDialog dialog = new UpdateDialog(new java.awt.Frame(), true, idBunga, namaBunga, kategori,
                deskripsi, harga, stok, ukuran);
        dialog.setVisible(true);
        showTable();
    }     

Berikut adalah _constructor_ yang ada dalam _class_ "UpdateDialog" untuk menunjukkan bahwa dialog dibuka dengan membawa data dari tabel:

        public UpdateDialog(java.awt.Frame parent, boolean modal, String idBunga, String namaBunga, String kategoriBunga,
            String deskripsi, String harga, String stok, String ukuran) {
        super(parent, modal);
        initComponents();

        TxtIdBunga.setText(idBunga);
        TxtNamaBunga.setText(namaBunga);
        TxtKategoriBunga.setText(kategoriBunga);
        TxtDeskripsiProduk.setText(deskripsi);
        TxtHarga.setText(harga);
        TxtStokBunga.setText(stok);
        TxtUkuranBuket.setText(ukuran);
    }

Sehingga dialog modal "UpdateDialog" dipanggil setelah user memilih baris data di tabel dan data yang dipilih otomatis dimasukkan ke "TextField" dalam dialog. Kemudian dapat digunakan untuk memperbarui data yang sudah ada. Setelah dialog ditutup, tabel utama diperbarui lagi tampilannya.
## Delete
Dalam praktikum ini untuk _button_ "Delete" akan dibuat dengan dialog modal. Dimana, untuk _code_ berikut digunakan dalam _class_ di JFrame utama yakni TokoBunga untuk menunjukkan bahwa _button_ "Delete" akan menggunakan Dialog Modal "Delete":

        private void BtnDeleteActionPerformed(java.awt.event.ActionEvent evt) {                                          
        int row = jTable1.getSelectedRow();
        if (row == -1) {
            JOptionPane.showMessageDialog(this, "Pilih data dulu dari tabel!");
            return;
        }

        String id = jTable1.getValueAt(row, 0).toString();
        String nama = jTable1.getValueAt(row, 1).toString();
        String kategori = jTable1.getValueAt(row, 2).toString();
        String deskripsi = jTable1.getValueAt(row, 3).toString();
        String harga = jTable1.getValueAt(row, 4).toString();
        String stok = jTable1.getValueAt(row, 5).toString();
        String ukuran = jTable1.getValueAt(row, 6).toString();

        DeleteDialog dialog = new DeleteDialog(new java.awt.Frame(), true, id, nama, kategori, deskripsi, harga, stok, ukuran);
        dialog.setVisible(true);
        showTable();
    } 

Berikut adalah _constructor_ yang ada dalam _class_ "DeleteDialog" untuk menunjukkan bahwa dialog dibuka dengan membawa data dari tabel:

        public DeleteDialog(java.awt.Frame parent, boolean modal, String id, String nama, String kategori,
            String deskripsi, String harga, String stok, String ukuran) {
        super(parent, modal);
        initComponents();

        TxtIdBunga.setText(id);
        TxtNamaBunga.setText(nama);
        TxtKategoriBunga.setText(kategori);
        TxtDeskripsiProduk.setText(deskripsi);
        TxtHarga.setText(harga);
        TxtStokBunga.setText(stok);
        TxtUkuranBuket.setText(ukuran);
    }

Sehingga dialog modal DeleteDialog dipanggil setelah user memilih baris data di tabel dan data baris tersebut ditampilkan di "TextField" dialog sebagai konfirmasi sebelum dihapus. _Code_ ini digunakan untuk menghapus data dari _database_. Setelah dialog selesai, tabel utama juga diperbarui tampilannya.

# Penutup
Sekian penjelasan singkat mengenai praktikum ini, semoga bermanfaat dan bisa menjadi ilmu untuk belajar mengenai konsep CRUD dan dialog modal. Karena dengan dialog modal pengguna lebih fokus, data lebih aman dari kesalahan input, dan program jadi lebih terstruktur.
