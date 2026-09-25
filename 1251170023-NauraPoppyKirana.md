 ## A. Analisis Komponen 

### 1. Variabel dan tipe data yang di gunakan

No  Variabel  Tipe Data  Keterangan
1.  is_member : Boolean (True jika member, false jika bukan)
2.  jumlah_buku : Integer (jumlah buku yang dibeli)
3.  total_awal : Real / Float (Total harga belanjaan awal)
4.  nominal_diskon : Real / Float (Jumlah potongan harga)
5.  total_bayar : Real / Float (Total harga yang harus dibayar)


   ### 2. Struktur Kontrol

  1. ### Sequence : Mulai dari urutan input (is_member, jumlah_buku, total_awal, perhitungan nominal_diskon, perhitungan total_bayar,
   dan menampilkan output.
  2. ### Selection (percabangan) 
     - mengecek is_member 
     -is_member = True : mengecek total_awal > 200000 DAN jumlah_buku >mendapat diskon 5%, jika tidak diskon 0% 3, jika terpenuhi mendapat
      diskon 15%, jika tidak diskon 10%
     -is_member = False :  mengecek total_awal > 300000, jika terpenuhi # TUGAS : Studi Kasus Sistem Transaksi & Validasi Toko Buku Modern
  3. ### Iteration (perulangan) : pada while akan mengecek total_awal < 0 ATAU jumlah_buku < 1, jika salah satu benar akan mengulang
  terus sampai total_awal > 0 DAN jumlah_buku > 1

B. PSEUDOCODE
PROGRAM KasirTokoBuku

DEKLARASI:
is_member:boolean
jumlah_buku:integer
total_awal,nominal_diskon,total_bayar : real

DESKRIPSI:
//1.Minta input
 READ(is_member,jumlah_buku,total_awal)
//2.cek apakah input salah (total minus atau buku kurang dari 1)
  WHILE (total_awal<0 OR jumlah_buku<1)DO
  WRITE("input salah! Masukkan ulang:")
  READ(jumlah_buku, total_awal)
  ENDWHILE
//3.Hitung Diskon
IF (is_member = True) THEN
  IF (total_awal>=200000 AND jumlah_buku>=3)THEN
     nominal_diskon<-total_awal*
0.15
    ELSE
      nimonal_diskon<-total_awal*
0.10
    ENDIF
  ELSE
    IF(total_awal>=300000) THEN
       nominal_diskon<-total_awal*
0.5
   ELSE
     nominal_diskon<-0
  ENDIF
ENDIF
//4.Hitung bayar akhir
total_bayar<-total_awal - nominal_diskon
//5.Tampilkan Hasil
WRITE(nominal_diskon)
WRITE(total_bayar)

C. TRACE TABLE
Kasus A
INPUT : is_member= True, total_awal=250000, jumlah_buku=4

| LANGKAH  |  Aksi |   total_awal | jumlah_buku | is_member | Kondisi diperiksa | persen_diskon | nominal diskon | total_bayar
1.   | input awal  | 250.000      |   4          |    -      |        -          |      -        |        -       |      -
2.   | Validasi loop | 250.000    |   4           |    -      | 250.000<0 OR 4<1
                                                           ->False->keluar loop  |      -        |        -       |      -
3.   |Input        | 250.000      |    4          |  True    |        -          |      -        |        -       |      -
      is_member |
4.   | cek member  | 250.000      |    4         | True     | 250.000>=200.000   |      15%      |        -       |      -

                                                              DAN 4>=3->True
5.   | Hitung diskon | 250.000    |     4        | True     |      -             |     15%       |    Rp37.000    |       -
6.   | Hitung total  | 250.000    |     4        | True     |      -             |     15%       |    Rp37.000    |   Rp 212.500
       bayar
7.   | Output        |    -       |      -       |   -      |      -             |      -        |    Rp37.000    |   Rp 212.500

  
   Kasus B 
   Input : is_member = False, total_awal= 350000, jumlah_buku= 2
| Langkah  |  Aksi  |  total_awal |  jumlah_buku | is_member | Kondisi diperiksa | persen_diskon | nominal_diskon | total_bayar
1.         | Input awal | Rp350.000 |      2     |    -      |        -          |       -       |        -       |       -
2.         |Validasi loop | 350.000 |      2     |    -      | 350.000<0 OR 2<1  |       -       |        -       |       -
                                                              False->keluar loop
3.         |Input        | 350.000  |      2     |   False   |        -          |       -       |        -       |        -
            is_member
4.         |Cek non-member| 350.000 |      2     |   False   | 350.000>=300.000  |       5%      |         -      |        -
                                                               -> True
5.         | Hitung diskon | 350.000 |     2     |   False   |        -          |       5%      |      Rp17.500  |       -
6.         | Hitung total  | 350.000 |     2     |   False   |        -          |       5%      |      Rp17.500  |  Rp 332.500
             bayar
7.         | Output        |  -      |    -      |    -      |        -          |        -      |      Rp17.500  |   Rp 332.500


   Kasus C


     


   
