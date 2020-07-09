# Cara mendokumentasikan API

## Panduan ini memberikan templat untuk menyusun dokumentasi API Anda dan menjelaskan cara merancang dan memublikasikan konten Anda.

Harap diperhatikan - bahwa dokumen ini diterjemahkan dari pedoman yang digunakan untuk membuat API di UK. Dokumen ini berisi tautan ke dokumen lain dalam bahasa Inggris. Jika Anda tertarik dengan versi terjemahan dari dokumen ini, silakan hubungi Delivery Manager Senior GDMP Anda:

Henny.Bird@digital.cabinet-office.gov.uk

Dokumentasi API membantu pengguna berintegrasi dengan API Anda dengan menjelaskan apa itu API dan bagaimana menggunakannya.

Dokumentasi API biasanya terdiri dari:

-   informasi konseptual untuk memperkenalkan pengguna ke API dan informasi;
    
-   informasi praktis untuk membantu pengguna memulai dengan API;
    
-   informasi referensi untuk memberi tahu pengguna setiap detail API Anda.
    

Jika Anda menyediakan pustaka klien untuk berinteraksi dengan API Anda, Anda mungkin perlu membuat dokumentasi terpisah untuk setiap pustaka klien. Contoh yang digunakan di UK, [GOV.UK Notify has separate documentation for each of its client libraries](https://www.notifications.service.gov.uk/documentation).

## Memahami kebutuhan pengguna untuk dokumentasi

Pengguna Anda mungkin memiliki tingkat kemampuan atau pemahaman teknis yang berbeda-beda. Memulai dengan riset pengguna dan mendefinisikan [user needs](https://www.gov.uk/guidance/content-design/user-needs) dapat membantu Anda memahami apa yang dibutuhkan pengguna dari dokumentasi Anda.

## Cara menyusun dokumentasi Anda

Dokumen Anda harus dengan longgar mengikuti garis besar di bawah ini. Anda mungkin perlu melihat dokumentasi API untuk mengetahui API yang serupa dengan milik Anda atau melihat dokumentasi dari organisasi lain seperti [HMRC](https://developer.service.hmrc.gov.uk/) (Pemerintah UK), [Companies House](https://developer.companieshouse.gov.uk/api/docs/) (Pemerintah UK), [Stripe](https://stripe.com/docs/api), atau [MailChimp](https://developer.mailchimp.com/documentation/mailchimp/) untuk melihat bagaimana mereka menyusun konten mereka.

### Memperkenalkan API Anda

Akan bermanfaat untuk memulai dokumentasi Anda dengan ikhtisar singkat tentang:

-   apa yang dilakukan API;
    
-   manfaat menggunakan API untuk membantu pengguna mengevaluasinya terhadap API lain jika berlaku;
    
-   bagaimana API dikonsumsi, misalnya apakah pengguna Anda perlu membangun atau membeli sesuatu untuk menggunakannya;
    
-   segala syarat atau ketentuan penggunaan API;
    
-   segala batasan laju, autentikasi, atau persyaratan akses;
    
-   apakah API hanya tersedia selama waktu-waktu tertentu;
    
-   versi dan perubahan yang telah terjadi di antara versi (Anda dapat menautkan ke log perubahan untuk menghindari membuat ikhtisar terlalu panjang);
    
-   apakah API itu RESTful dan bagaimana data dikembalikan, misalnya di JSON.
    

Buat pengantar yang singkat agar pengguna Anda dapat membaca dan memahaminya dengan mudah. Anda harus menulis dalam bahasa yang sederhana dan tidak rumit serta menghindari jargon atau buzzword.

### Autentikasi

Jika Anda perlu mengautentikasi pengguna sebelum mereka menggunakan API Anda, sertakan bagian yang menjelaskan cara mengajukan permohonan autentikasi. Misalnya, [Companies House API documentation](https://developer.companieshouse.gov.uk/api/docs/index/gettingStarted/apikey_authorisation.html) menyertakan bagian terpisah tentang cara mendapatkan dan mengirim kunci API.

### Otorisasi

Jika akses ke bagian API Anda memerlukan otorisasi, pastikan bagian dalam dokumentasi Anda menjelaskan cara memperoleh akses. Anda kemudian dapat menautkan ke bagian ini dari titik akhir atau sumber yang memerlukan otorisasi.

Misalnya, HMRC Developer Hub menjelaskan berbagai [levels of authorisation available for HMRC API endpoints](https://developer.service.hmrc.gov.uk/api-documentation/docs/authorisation) dan apakah pengguna memerlukan token untuk dapat mengaksesnya atau tidak.

### Batas laju

Jika API Anda menggunakan batasan laju (atau catatan), jelaskan berapa banyak permintaan yang dapat dibuat pengguna dalam periode yang ditentukan. Meski jika seorang pengguna tidak mungkin akan memenuhi jumlah permintaan maksimum, Anda harus tetap menjelaskan apa yang akan terjadi jika pengguna melampaui batas tersebut, termasuk jenis pesan kesalahan yang dapat mereka harapkan dan cara memperbaiki kesalahan itu.

Misalnya, [GOV.UK Pay API documentation](https://govukpay-docs.cloudapps.digital/#api-rate-limits) menjelaskan bahwa pengguna akan melihat kode kesalahan tertentu, tetapi mereka akan bisa membuat permintaan lain setelah satu detik berlalu.

### Informasi pembuatan versi

Beri tahu pengguna bagaimana [versioning works for your API](https://www.gov.uk/guidance/gds-api-technical-and-data-standards#iterate-your-api) dan letakkan versi dokumentasi yang Anda buat di samping API Anda.

Setiap versi dokumentasi Anda harus menyertakan pengantar yang menjelaskan apa yang membuatnya berbeda dari versi sebelumnya. Anda harus memasukkan semua riwayat revisi untuk dokumentasi API Anda dan mempermudah pengguna untuk beralih di antara dokumentasi untuk versi yang berbeda. [documentation for HMRC’s Individual Benefits API](https://developer.service.hmrc.gov.uk/api-documentation/docs/api/service/individual-benefits/1.1) menyediakan menu tarik-turun untuk memungkinkan pengguna beralih antara versi saat ini dan sebelumnya.

## Memulai

Bagian 'memulai' atau 'mulai cepat' harus menjelaskan cara termudah dan tercepat bagi pengembang untuk menggunakan API. Penjelasan tersebut memberi pengguna Anda cara cepat untuk melihat cara kerja API Anda, sehingga mereka dapat mulai bereksperimen.

Anda mungkin perlu memberikan instruksi ini dalam daftar pendek dan bernomor. Misalnya, [GOV.UK Registers API documentation](https://docs.registers.service.gov.uk/quick_start_guide/#quick-start-guide) menjelaskan 4 langkah untuk memanggil API dan menerima respons.

Bagian 'memulai' Anda dapat menyertakan kode sampel yang dapat digunakan pengembang untuk melihat respon. Misalnya, [Google Maps Javascript API documentation includes a ‘Hello World’ section](https://developers.google.com/maps/documentation/javascript/tutorial) setelah 2 paragraf pendek. Dokumentasi API GoCardless juga menggunakan bagian [‘getting started’ section to introduce important concepts](https://developer.gocardless.com/getting-started/api/introduction/) mengenai API-nya.

## Referensi API

Informasi referensi adalah apa yang banyak pengguna anggap sebagai bagian utama dari dokumentasi API. Referensi API memberikan metode, permintaan, dan respons API. Ikuti panduan tentang [writing API Reference documentation](https://www.gov.uk/guidance/writing-api-reference-documentation).

## Menguji API

Anda juga harus membantu pengguna memastikan mereka berhasil menguji API Anda, terutama jika mereka ingin menggunakannya dalam lingkungan produksi dengan data nyata.

Di bagian ini, jelaskan bagaimana cara menguji bahwa interaksinya dengan API Anda beroperasi dengan benar, termasuk:

-   mengapa mereka harus menguji;
    
-   apa yang perlu mereka uji;
    
-   cara menjalankan pengujian di lingkungan pengujian.
    

Permudah pengembang untuk bereksperimen dengan API Anda di lingkungan sandbox. Idealnya, lingkungan sandbox ini memungkinkan pengguna menggunakan data untuk menguji skenario mereka. Jika menggunakan lingkungan sandbox, Anda harus memastikan pengembang dapat:

-   menguji API Anda tanpa membahayakan data pengguna yang sebenarnya,
    
-   mengakses lingkungan tanpa memerlukan otorisasi.
    

Jelaskan batasan lingkungan sandbox Anda dibandingkan dengan lingkungan produksi Anda. Misalnya, jika lingkungan sandbox Anda hanya memungkinkan pengujian stateless, pengguna Anda harus tahu itu tidak akan menggambarkan pengujian stateful dalam produksi.

## Dukungan

Pertimbangkan cara Anda membantu pengguna yang mencoba menggunakan API Anda. Anda dapat menambahkan bagian 'dukungan' dalam dokumentasi Anda dan memasukkan:

-   cara menghubungi tim pengembang API (misalnya, melalui GitHub atau formulir kontak);
    
-   cara berkontribusi pada pengembangan jika sesuai;
    
-   tautan ke informasi atau panduan pendukung, seperti kiriman blog produk.
    

Anda juga dapat menjelaskan cara pengguna melaporkan kerentanan atau masalah keamanan apa pun dan cara Anda menanggapi laporan tersebut. Anda juga dapat meminta pengguna untuk tidak mengungkapkan masalah apa pun secara publik sampai masalah tersebut ditangani oleh tim pengembangan Anda.

## Cara memublikasikan dan memformat dokumentasi Anda

Selain menulis konten untuk dokumentasi API, Anda harus merancang konten, sehingga pengguna Anda dapat menemukan informasi yang mereka butuhkan.

### Metadata

Metadata akan membantu pengguna Anda menemukan dokumentasi Anda. Pertimbangkan untuk memasukkan nama API, apakah API itu stabil atau dalam alfa, URL dasar, nomor versi, dan informasi ketersediaan.

### Bantu pengguna menavigasi dokumentasi Anda

Dokumentasi API bisa menjadi panjang dan rumit. Pertimbangkan cara membantu pengguna Anda untuk menemukan bagian dari dokumentasi API Anda yang mereka butuhkan dengan navigasi. Misalnya, di UK [documentation template built by GDS](https://github.com/alphagov/tech-docs-template) menggunakan navigasi kiri yang tetap, sehingga pengguna dapat berpindah ke bagian yang lain, dan dapat membuat konten baik sebagai satu atau beberapa halaman. Ini adalah desain navigasi dokumentasi umum yang digunakan oleh organisasi termasuk [Stripe](https://stripe.com/docs/api) dan [Dropbox](https://www.dropbox.com/developers/documentation/http/overview).

Jika Anda memiliki banyak dokumentasi, Anda mungkin perlu memasukkan fungsi pencarian. Ketahui bahwa banyak pengembang mencari halaman dokumentasi panjang menggunakan pencarian browser bawaan (Ctrl-F). [GDS documentation template](https://github.com/alphagov/tech-docs-template) UK memiliki fungsi pencarian bawaan.

### Memformat cuplikan kode

Cuplikan kode adalah blok kecil kode yang dapat digunakan kembali. Cuplikan kode harus dapat dibedakan dengan jelas dari teks yang bukan kode, misalnya dengan me-render cuplikan dalam fon dengan lebar yang ditetapkan. Anda mungkin juga perlu memberikan warna latar belakang yang terang agar berbeda dari teks standar.

Misalnya, di UK, [GDS documentation template](https://github.com/alphagov/tech-docs-template) menggunakan latar belakang abu-abu terang untuk kode dalam baris atau blok kode apa pun.

### Memublikasikan dokumentasi Anda

Anda dapat menggunakan sejumlah alat dan format penulisan dan pemublikasian untuk mengedit dokumentasi API Anda.

Misalnya, [documentation format](https://github.com/alphagov/tech-docs-template) Government Digital Service UK memungkinkan Anda untuk menerbitkan dokumentasi dengan tema GOV.UK. Format tersebut menggunakan generator situs statis yang disebut [Middleman](https://middlemanapp.com/). Konten dapat ditulis dalam HTML atau Markdown dan disimpan sebagai kode, yang memungkinkannya disimpan dalam sistem kontrol versi seperti Git. Pendekatan industri ini dalam memperlakukan dokumentasi sebagai kode sering disebut sebagai 'docs-as-code'.

[HMRC API documentation](https://developer.service.hmrc.gov.uk/) ditulis menggunakan RAML dan kemudian di-render melalui templat ke dalam HTML.

Jika Anda memiliki API kecil dan riset pengguna Anda mengesankan mereka hanya membutuhkan dokumentasi minimal, Anda mungkin perlu menyimpan dan memublikasikan dokumentasi dalam repositori kode sumber tim Anda. Misalnya, dalam markdown, berkas README dapat diakses di GitHub.

## Memastikan dokumentasi Anda terus memenuhi kebutuhan pengguna

Publikasikan dokumentasi Anda sedini mungkin untuk mendapatkan umpan balik dari pengguna. Anda harus secara teratur menguji dokumentasi API yang aktif, terutama jika Anda menerapkan perubahan apa pun yang memengaruhi cara pengguna mengonsumsi dokumentasi atau menggunakan API Anda.

Misalnya, Anda dapat meminta mereka untuk menyelesaikan skenario umum dengan API Anda dan melihat apakah instruksi yang Anda berikan dalam dokumentasi membantu mereka menyelesaikan tugas. Dengan mengamati pengguna Anda yang mengikuti instruksi terdokumentasi Anda, Anda dapat melihat apakah dokumentasi Anda tidak lengkap, tidak jelas, atau membantu pengguna secara efektif.

Anda juga dapat menguji pemahaman pengguna Anda tentang bahasa yang telah Anda gunakan dalam dokumentasi Anda dengan pengujian pemahaman. Cara umum untuk menguji pemahaman adalah dengan meminta pengguna untuk [highlight parts of your documentation](https://userresearch.blog.gov.uk/2014/09/02/a-simple-technique-for-evaluating-content/) yang membuatnya lebih mudah atau lebih sulit untuk memahami konsep atau menggunakan API Anda.

Anda juga dapat mewawancarai pengguna untuk mengetahui seberapa nyaman mereka dengan domain di sekitar API Anda atau cara kerja API Anda. Anda bahkan dapat [run A/B tests to test variations of content](https://userresearch.blog.gov.uk/2014/09/02/a-simple-technique-for-evaluating-content/) sebelum dipublikasikan.

Tim dokumentasi API HMRC juga telah bereksperimen dengan menggunakan survei pop-up untuk mendapatkan umpan balik langsung dari pengembang menggunakan dokumentasi mereka. Tim kemudian menggunakan respons untuk mengulangi dokumentasi.

## Panduan terkait

Panduan ini mungkin juga berguna untuk Anda:

-   [Writing REST API reference documentation](https://www.gov.uk/guidance/writing-api-reference-documentation)
    
-   [API standards](https://www.gov.uk/guidance/gds-api-technical-and-data-standards)
    
-   [Tom Johnson’s guide to API documentation](http://idratherbewriting.com/learnapidoc/)
