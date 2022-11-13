# SIG-Teori-Modul10-Working-with-Projections

## Data 

Silahkan Download data berikut :

[ne_10m_admin_0_countries.zip](https://www.qgistutorials.com/downloads/ne_10m_admin_0_countries.zip)

[minisc_gb.zip](https://www.qgistutorials.com/downloads/minisc_gb.zip) (Hanya berisi file yang diperlukan untuk tutorial ini)

## Prosedur

1. Buka QGIS. Pergi ke Layer ‣ Add Layer ‣ Add Vector Layer… .
2. Klik … di sebelah Sumber , Jelajahi ne_10m_admin_0_countries.shpfile yang diunduh dan klik Tambah .
3. Di bagian bawah jendela QGIS, Anda akan melihat label Coordinate . Saat Anda menggerakkan kursor di atas peta, koordinat X dan Y di lokasi tersebut akan ditampilkan. Di pojok kanan bawah Anda akan melihat EPSG:4326 . Ini adalah kode untuk CRS (Projection) saat ini untuk proyek - juga dikenal sebagai Project CRS .
4. Untuk menentukan proyeksi layer, kita dapat melihat ke dalam metadata. Klik kanan pada ne_10m_admin_0_countrieslayer dan pilih Properties .
5. Beralih ke tab Informasi di dialog Properti Lapisan . Luaskan bagian Informasi dari penyedia . Di bagian bawah, Anda akan melihat nama proyeksi di bawah CRS .
6. Sekarang mari kita lihat bagaimana kita bisa mengubah proyeksi layer. Operasi ini disebut Re-Projection . Daripada memproyeksikan ulang seluruh lapisan, kita juga dapat memilih subset fitur dan memproyeksikannya kembali ke lapisan baru. Gunakan alat Select features by area or single click dan klik fitur United Kingdom untuk memilihnya.
7. Cari dan temukan algoritma Vector General ‣ Proyeksi ulang layer di kotak alat Pemrosesan.
8. Pilih ne_10m_admin_0_countriessebagai lapisan Input , centang Selected features only lalu klik ikon globe di sebelah Target CRS , cari dan pilih . Di Reprojected , pilih dan klik Save to a file . Sekarang pilih direktori dan masukkan nama as dan klik Run .EPSG:27700 - OSGB 1936 / British National Grid...united_kingdom.gkpg
9. Sebuah layer baru united_kingdomakan muncul di Layer Panel . Seperti yang Anda lihat, kedua lapisan masih sejajar satu sama lain - meskipun mereka berada di CRS yang berbeda. Ini karena QGIS mendukung transformasi CRS On-The-Fly (OTF) . Artinya, setiap kali CRS lapisan tidak cocok dengan CRS Proyek, maka secara otomatis akan diubah menjadi CRS Proyek sehingga dapat ditampilkan dengan benar. Sekarang mari kita atur Project CRS agar sesuai dengan CRS united_kingdomLayer yang baru dibuat. Hapus ne_10m_admin_0_countrieslayer dan, klik kanan pada united_kingdomlayer Layer CRS Set Project CRS dari Layer .
10. Anda akan melihat Proyek CRS diperbarui ke EPSG:27700.
11. Sekarang mari kita tambahkan layer Raster. Pergi ke Layer Add Layer Add Raster Layer… .
12. Klik di ...sebelah Source , pilih layer MiniScale_(standard)_R23.tif. Klik Tambahkan .
13. Sekarang layer baru MiniScale_(standard)_R23ditambahkan ke kanvas.
14. Untuk membuat kedua lapisan terlihat, alihkan urutan lapisan dengan menyeret MiniScale_(standard)_R23ke bawah di panel Lapisan .
15. Klik kanan pada MiniScale_(standard)_R23layer dan klik Properties .
16. Di Layer Properties , pindah ke Information , CRS adalah . Ini menegaskan bahwa CRS layer raster sama dengan Project CRS.EPSG:27700 - OSBG 1935 / British National Grid - Projected.

-----------------

Catatan :

Jika Anda ingin memproyeksikan ulang lapisan raster, Anda dapat menggunakan GDAL ‣ Proyeksi raster ‣ Algoritma warp (proyeksi ulang) di kotak alat Pemrosesan.

-----------------




