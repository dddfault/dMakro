```
                              __                __
                         ____/ /___ ___  ____ _/ /___________
                        / __  / __ `__ \/ __ `/ //_/ ___/ __ \
                       / /_/ / / / / / / /_/ / ,< / /  / /_/ /
                       \__,_/_/ /_/ /_/\__,_/_/|_/_/   \____/

                      fungsi makro untuk user interface ReShade
                              dibuat ama mbah.primbon

                              disponsori oleh UnFamouS
    ////////////////////////////////////////////////////////////////////////////

    LU MUSTI TAU :
    ==============
    Sebelum ke panduan penggunaan nya, pertama gua mau bilang bodo amat ama orang
    luar brow, kaga peduli mau dibilang apa ama mereka, ini file gua suka-suka gua.
    fakyeu mennn maderpaker.

    Oke sekarang kita ke tutorialnya.


    Cara menggunakan makro ini :
    ============================
    Pertama, tambahin 2 line untuk mengaktifkan definisi version untuk dMakro dan ReShade
    dan kemudian tambahin file ini kedalam shader lu dengan cara #include file ini.
    Pastiin ini ada di bagian atas, lebih bagus ada dibawah ReShade.fxh

    contoh nih,
    #define DMAKRO_VERSION_REQUIREMENT      1023
    #define RESHADE_VERSION_REQUIREMENT     40901

    #include "ReShade.fxh"
    #include "dMakro.fxh"
    #include "AseDeKon.h"
    #include ....

    Bisa dilihat diatas kalau dMakro.fxh ditambahin dibawah ReShade.fxh.
    sisanya dibawah suka-suka lu misalkan lu pake banyak hal. Untuk versi dMakro saat
    ini adalah 1023 dan versi reshade minimum yang diperlukan adalah 4.9.1 (40901)

    "Kenapa kudu gitu bang ?, kenapa ga dipaling atas aja biar estetik ?"
    Ya biar ga error lah, makro lu perlu variabel parameter yang ada di ReShade.fxh.
    Jadi ReShade.fxh itu harus duluan yang musti dipanggil ama shader lu.

    Ada beberapa tipe variabel yang didukung ama ini makro. Lebih
    lengkapnya lu bisa liat daftar dibawah ini :

      Tipe / Jenis Variabel :
      -----------------------
      MP_BOOL    = Boolean

      MP_INT     = Integer
      MP_INT2    = Integer (2 komponen)
      MP_INT3    = Integer (3 komponen)
      MP_INT4    = Integer (4 komponen)

      MP_FLOAT   = Floating Point
      MP_FLOAT2  = Floating Point (2 komponen)
      MP_FLOAT3  = Floating Point (3 komponen)
      MP_FLOAT4  = Floating Point (4 komponen)

      MP_COMBO   = Kombinasi Item
      MP_RADIO   = Opsi Item
      MP_LIST    = Daftar Item

      MP_COLOR   = Warna
      MP_TEXT    = Teks

    Nah setelah itu ada juga beberapa jenis Widget yang dimiliki ama UI nya ReShade
    diantaranya adalah sebagai berikut :

      Jenis - jenis widget UI ReShade :
      ---------------------------------
      S          = Slider (bisa dipake di jenis variabel float dan integer)
      I          = Input  (bisa dipake di jenis variabel float dan integer)
      D          = Drag   (bisa dipake di jenis variabel float dan integer)

      R          = Radio  (cuma bisa dipake di jenis variabel integer)
      C          = Combo  (cuma bisa dipake di jenis variabel integer)
      L          = List   (cuma bisa dipake di jenis variabel integer)

    Kalau kalian liat untuk widget S (Slider), I (Input) dan D (Drag) itu bisa
    dipakai di kedua jenis variabel float dan int. Sedangkan untuk R (Radio),
    C (Combo), L (List) itu hanya bisa digunakan pada jenis variabel integer.

    Jujur aja, jenis widget I (Input) itu widget yang jarang dipake, kuno banget bro,
    sekarang UI sudah gampang dan lebih nyaman dipake bro tinggal ser-geser
    set sat set aja buat edit. Kaga musti lu input angka spesifik. Kalo lu mau
    override rentang value yang ada di dalam variabel itu, gua lebih menyarankan elu
    untuk menggunakan widget D (Drag), why ? karena lu bisa ser-geser buat ngubah
    valuenya, dan lu bisa input dengan cara double click di variabel parameternya.

    Okehh.. mungkin lu sekarang agak bingung, kenapa ini namanya dipersingkat
    MP_INT, MP_FLOAT dll untuk jenis variabel nya, dan satu huruf S, I, D, R, C, L untuk
    jenis widgetnya. Misal lu butuh makro dengan jenis float dan widget slider,
    tinggal pake MP_FLOAT_S(), atau lu perlu float3 dengan widget drag, jadinya
    MP_FLOAT3_D() kalo mau diubah dari drag ke slider tinggal ubah aja D ke S,
    seperti itu. Ini kan makro ya bro, fungsi nya makro itu adalah menyederhanakan
    sesuatu yang belibet banget bro.

    Jadi setelah lu mengerti apa jenis variabel makro nya sekarang gua akan contohin
    gimana misalkan lu perlu makro ini untuk variabel parameter shader elu.

    (File shader tutorialnya ada di paket penjualan, kalian bisa cek sendiri.)

    Fitur kategorisasi, kalau lu mau parameterlu punya kategori, tinggal panggil
    definisi KATEGORISASI. Caranya tinggal tulis aja di bagian atas sebelum include
    dengan nambahin line #define KATEGORISASI. ini berfungsi untuk mengaktifkan
    kategorinya.

    Setelah itu di setiap kelompok parameter, lu kasih #define KATEGORI "x" dan
    #define TERTUTUP y. x itu mewakili nama kategori yang bakal lu pakai, dan y
    itu untuk fungsi buka tutup kategori (buka / tutup / true / false). setelah
    itu kasih #undef di bagian bawah setiap kategorinya.

    Untuk kemudahan, tersedia snippet yang sudah termasuk paket penjualan repository
    ini. Kalian bisa tambahkan snippet ini di bahasa HLSL.

    Selamat mencoba,

    mbah.primbon 
