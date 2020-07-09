# Standar teknis dan data API (v2 - 2019)

Pedoman standar antarmuka pemrograman aplikasi (API) berbasis web berikut akan membantu organisasi Anda memberikan layanan sebaik mungkin kepada pengguna.

Harap diperhatikan - bahwa dokumen ini diterjemahkan dari pedoman yang digunakan untuk membuat API di UK. Dokumen ini berisi tautan ke dokumen lain dalam bahasa Inggris. Jika Anda tertarik dengan versi terjemahan dari dokumen ini, silakan hubungi Delivery Manager Senior GDMP Anda:

Henny.Bird@digital.cabinet-office.gov.uk

Publikasikan API Anda di internet secara default (tanpa pilihan lain).

## Mengikuti Kode Praktik Teknologi

Pastikan API Anda memenuhi persyaratan Kode Praktik Teknologi [Technology Code of Practice](https://www.gov.uk/government/publications/technology-code-of-practice/technology-code-of-practice) (TCoP) dengan memastikan API Anda:

-   mengikuti prinsip Open Standards ([Open Standards Principles](https://www.gov.uk/government/publications/open-standards-principles)) dari proses akses terbuka, berdasarkan konsensus, serta lisensi bebas royalti;
    
-   adaptif sesuai skala sehingga API tetap mempertahankan tujuan dan perjanjian tingkat layanan saat permintaan meningkat;
    
-   stabil sehingga API mempertahankan tujuan dan perjanjian tingkat layanan saat diubah atau menghadapi peristiwa tak terduga;
    
-   dapat digunakan kembali jika memungkinkan, sehingga pemerintah tidak menduplikasi pekerjaan.
    

## Menggunakan RESTful

Ikuti standar industri dan jika sesuai, buat API yang mengikuti prinsip [RESTful](https://restfulapi.net/), yang menggunakan permintaan verba HTTP untuk memanipulasi data.

Ketika menangani permintaan, Anda harus menggunakan verba HTTP untuk tujuannya yang ditentukan.

Salah satu keunggulan REST yaitu REST memberikan Anda kerangka kerja untuk mengomunikasikan keadaan kesalahan.

Dalam beberapa kasus, membuat REST API mungkin tidak berlaku, misalnya, ketika Anda membuat API untuk streaming data.

## Menggunakan HTTPS

Anda harus menggunakan [HTTPS](https://www.ncsc.gov.uk/guidance/tls-external-facing-services) saat membuat API.

Menambahkan HTTPS akan mengamankan koneksi ke API Anda, menjaga privasi pengguna, memastikan integritas data, dan mengautentikasi server yang memberikan API. [Service Manual provides more guidance on HTTPS](https://www.gov.uk/service-manual/technology/using-https) .

Amankan API menggunakan Transport Layer Security (TLS) v1.2. Jangan gunakan Secure Sockets Layer (SSL) atau TLS v1.0.

Walaupun ada beberapa vendor gratis dan murah yang menawarkan sertifikat TLS,pastikan calon pengguna API percaya kepada sertifikat Anda. Pastikan Anda memiliki proses yang kuat untuk [certificate renewal and revocation](https://www.ncsc.gov.uk/guidance/provisioning-and-securing-security-certificates) yang tepat waktu.

## Pertimbangkan untuk menautkan data (hipermedia)

API Anda dapat menautkan data Anda. Anda dapat membuat API lebih dapat diakses secara terprogram dengan mengembalikan URI, dan dengan menggunakan standar dan spesifikasi yang sudah ada.

Gunakan Pengidentifikasi Sumber Seragam (URI) untuk mengidentifikasi data tertentu:


```
{  
"name": "Bob Person",  
"company": "https://your.api/company/bobscompany";  
}

```

  

Ketika API mengembalikan data dalam menanggapi panggilan HTTP, Anda harus [use URIs](https://en.wikipedia.org/wiki/Uniform_Resource_Identifier) di dalam payload untuk mengidentifikasi data tertentu. Jika memungkinkan, Anda harus menggunakan spesifikasi yang menggunakan hipermedia, seperti [CURIES](https://www.w3.org/TR/curie/), [JSON-LD](https://json-ld.org/) atau [HAL](https://en.wikipedia.org/wiki/Hypertext_Application_Language).

Hal ini mempermudah penemuan sumber daya tersebut. Misalnya, Anda dapat mengembalikan objek “person” yang tertaut ke sumber daya yang menunjukkan perusahaanya dengan cara berikut:

## Menggunakan JSON

Pilihan pertama Anda untuk semua API web harus JSON jika memungkinkan.

Hanya gunakan penunjukkan lainnya untuk membuat sesuatu dalam kasus pengecualian, seperti saat Anda:

-   harus terhubung ke sistem warisan, misalnya, sistem yang hanya menggunakan XML,
    
-   akan menerima keunggulan yang jelas yang didapat dari mematuhi standar yang diadopsi secara luas (misalnya, [SAML.](http://saml.xml.org/))
    

Kami merekomendasikan Anda untuk:

-   membuat tanggapan sebagai objek JSON dan bukan sebuah larik (objek JSON dapat berisi larik JSON) - larik dapat membatasi kemampuan untuk menyertakan metadata mengenai hasil dan membatasi kemampuan API untuk menambahkan kunci tingkat atas tambahan di masa mendatang;
    
-   mendokumentasikan objek JSON Anda untuk memastikannya dijelaskan dengan baik sehingga objek tersebut tidak dianggap sebagai larik berurutan;
    
-   menghindari kunci objek yang tidak dapat diperkirakan seperti kunci objek yang diturunkan dari data karena hal ini menambah gesekan untuk klien;
    
-   menggunakan kasus tata bahasa yang konsisten untuk kunci objek - pilih garis_bawah atau KapitalAwal dan teruslah konsisten.
    

## Menunjukkan waktu dan tanggal

Menggunakan [ISO 8601 standard](https://www.gov.uk/government/publications/open-standards-for-government/date-times-and-time-stamps-standard) bermanfaat untuk menunjukkan tanggal dan waktu di tanggapan payload Anda. Standar ini membantu orang membaca waktu dengan benar.

Gunakan format tanggal yang konsisten. Untuk tanggal, akan tampak seperti ini `2017-08-09`. Untuk tanggal dan waktu, gunakan bentuk`2017-08-09T13:58:07Z`.

## Menunjukkan suatu lokasi fisik

Uni Eropa mengamanatkan menggunakan [ETRS89 standard](https://www.gov.uk/government/publications/open-standards-for-government/exchange-of-location-point) untuk cakupan geografis Eropa. Anda juga dapat menggunakan WGS 84 atau sistem koordinat CRS lainnya untuk data lokasi Eropa selain ini.

Gunakan standar [World Geodetic System 1984](https://www.nga.mil/ProductsServices/GeodesyandGeophysics/Pages/WorldGeodeticSystem.aspx) (WGS 84) untuk seluruh dunia. Anda juga dapat menggunakan sistem koordinat CRS lainnya untuk seluruh dunia selain ini.

Anda harus menggunakan [GeoJSON](http://geojson.org/) untuk pertukaran informasi lokasi.

## Menggunakan Unicode untuk penyandian

Standar [Unicode Transformation Format (UTF-8)](https://en.wikipedia.org/wiki/UTF-8)  [used by many governments when](https://www.gov.uk/government/publications/open-standards-for-government/cross-platform-character-encoding-profile) menyandikan teks atau penunjukan data tekstual lainnya.

## Cara menanggapi permintaan data

Konfigurasikan API untuk menanggapi ‘permintaan’ data dan bukan ‘mengirim’ atau ‘mendorong’ data. Hal ini memastikan pengguna API hanya menerima informasi yang mereka butuhkan.

Ketika menanggapi, API Anda harus menjawab permintaan sepenuhnya dan secara khusus. Misalnya, suatu API harus menanggapi permintaan “apakah pengguna ini telah menikah?” dengan suatu boolean. Jawaban tidak boleh mengembalikan detail selain daripada yang diperlukan dan harus bergantung pada penggunaan klien untuk menafsirkannya dengan benar.

Misalnya:

```
{ "married":"false" }
```

Daripada:


```
person": {  
"name": "Alice Betterland",  
"dob": "1999-01-01",  
"married": false,

"validFrom":"2011-04-03",

"validTo":""  
}  
  
} 
```

  

## Merancang bidang data dengan mempertimbangkan kebutuhan pengguna

Ketika merancang bidang data , Anda harus mempertimbangkan bagaimana bidang tersebut memenuhi kebutuhan pengguna. Memiliki [technical writer](https://www.gov.uk/government/publications/technical-writer-role-description/technical-writer-role-description) di tim Anda dapat membantu Anda melakukan hal ini. Anda juga dapat menguji dokumentasi Anda secara rutin.

Misalnya, jika Anda harus mengumpulkan informasi pribadi sebagai bagian dari dataset, sebelum memutuskan tanggapan payload, Anda mungkin harus mempertimbangkan apakah:

-   rancangan dapat mengatasi nama-nama dari budaya yang tidak memiliki nama depan dan nama belakang;
    
-   singkatan DOB berterima atau lebih baik menguraikannya menjadi bidang tanggal kelahiran;
    
-   DOB dapat berterima saat digabungkan dengan DOD (tanggal kematian) atau DOJ (tanggal bergabung).
    

Anda harus memastikan Anda memberikan semua opsi yang relevan. Misalnya, bidang “status pernikahan” cenderung memiliki lebih dari 2 status yang ingin Anda catat: menikah, belum menikah, cerai, janda, pisah rumah, dibatalkan, dan seterusnya.

Tergantung pada apa yang Anda putuskan, Anda dapat memilih payload berikut sebagai tanggapan:

```
{  
person": {  
"name": "Alice Wonderland",  
"dob": "1999-01-01",  
"married": true,

"validFrom":"2010-03-12",

"validTo":"2011-04-03"  
},

person": {  
"name": "Alice Betterland",  
"dob": "1999-01-01",  
"married": false,

"validFrom":"2011-04-03",

"validTo":""  
}  
  
} 

```

  

## Memungkinkan pengguna mengunduh seluruh dataset secara massal

Saat menyediakan API Data Terbuka, Anda harus memungkinkan pengguna mengunduh seluruh dataset kecuali dataset tersebut berisi informasi rahasia. Hal ini memberikan pengguna:

-   kemampuan untuk menganalisis dataset secara lokal;
    
-   dukungan saat melakukan tugas yang membutuhkan akses ke seluruh dataset (misalnya, merencanakan grafik di area tangkapan sekolah di Inggris).
    

Pengguna harus dapat mengindeks salinan data lokal menggunakan teknologi basis data pilihan mereka kemudian melakukan kueri untuk memenuhi kebutuhan mereka. Hal ini berarti bahwa waktu henti API di masa mendatang tidak akan berdampak bagi mereka, karena mereka telah memiliki semua data yang mereka butuhkan.

Menggunakan API data catatan-per-catatan untuk melakukan tindakan yang sama tidak optimal, baik bagi pengguna maupun bagi API. Hal ini dikarenakan:

-   batas laju akan memperlambat akses, atau bahkan dapat menghentikan pengunduhan seluruh dataset;
    
-   jika dataset sedang diperbarui bersamaan dengan unduhan catatan-per-catatan, pengguna mungkin memperoleh catatan yang inkonsisten;
    

jika Anda mengizinkan pengguna untuk mengunduh seluruh dataset, Anda harus mempertimbangkan untuk memberikan cara bagi mereka untuk memiliki catatan yang terkini. Misalnya, Anda dapat melakukan streaming langsung data Anda atau memberi tahukan kepada mereka bahwa data baru sudah tersedia, sehingga konsumen API mengetahui kapan harus mengunduh data API Anda secara berkala.

## Mendorong pengguna untuk menyimpan salinan dataset lokal terbaru

Jangan mendorong pengguna untuk menyimpan dataset terkini yang besar dengan cara mengunduh ulang dataset, karena pendekatan ini dianggap boros dan tidak praktis. Alih-alih, izinkan pengguna mengunduh daftar penambahan perubahan untuk suatu dataset. Hal ini memungkinkan pengguna menyimpan salinan lokal paling mutakhirdan menyelamatkan mereka dari keharusan untuk mengunduh ulang seluruh dataset berulang kali.

Tidak terdapat standar yang disarankan untuk pola ini, sehingga pengguna dapat mencoba pendekatan lainnya seperti:

-   penyandian data di umpanan [Atom/RSS,](https://en.wikipedia.org/wiki/Atom_(standard))
    
-   menggunakan pola yang muncul, seperti alir peristiwa yang digunakan oleh produk seperti [Apache Kafka,](https://kafka.apache.org/)
    
-   memanfaatkan register data terbuka.
    

## Ketika memublikasikan data massal

Sediakan data dalam format CSV serta JSON, ketika Anda ingin memublikasikan data massal. Hal ini memastikan pengguna untuk dapat menggunakan berbagai alat, meliputi perangkat lunak yang tersedia, mengimpor, dan menganalisis data ini.

Publikasikan data massal di situs web publik dan pastikan terdapat tautan yang jelas menuju situs tersebut.

## Menyimpan log permintaan untuk data pribadi

Jika [API serves personal or sensitive data](https://ico.org.uk/media/for-organisations/documents/1042221/protecting-personal-data-in-online-services-learning-from-the-mistakes-of-others.pdf), Anda harus melakukan log kapan data tersebut diberikan dan kepada siapa. Hal ini akan membantu Anda memastikan ‘keutamaan privasi’ dalam penyampaian layanan Anda. .

## Kapan menggunakan akses terbuka

Gunakan akses terbuka (tanpa kontrol) jika Anda ingin memberikan akses tanpa batas kepada API dan Anda tidak perlu mengidentifikasi pengguna Anda, misalnya ketika memberikan data terbuka. Namun, selalu ingat risiko [denial-of-service attacks](https://www.ncsc.gov.uk/collection/denial-service-dos-guidance-collection) .

Akses terbuka bukan berarti Anda tidak dapat mengendalikan API Anda.

Pertimbangkan opsi publikasi data terbuka di situs web publik daripada melalui suatu API. Ketika menggunakan data terbuka, jangan gunakan autentikasi sehingga Anda dapat memaksimalkan penggunaan API Anda.

## Kapan saatnya mengautentikasi API Anda

Autentikasi diperlukan ketika Anda ingin mengidentifikasi klien dengan tujuan:

-   pembatasan/pengendalian nilai
    
-   audit
    
-   penagihan
    
-   otorisasi
    

Tujuan Anda akan menentukan persyaratan keamanan untuk solusi autentikasi Anda.

Misalnya, jika Anda harus mengidentifikasi pengguna murni untuk pembatasan laju, Anda mungkin tidak perlu seringkali menyegarkan token pengguna karena jika token berada di tangan yang salah, akan cenderung mengancam layanan Anda.

Pastikan Anda mempertimbangkan API Anda yang mungkin memerlukan lebih dari sekadar mengautentikasi suatu token organisasi, misalnya, ketika berhadapan dengan informasi sensitif seperti data medis.

## Memberikan otorisasi tingkat aplikasi

Gunakan otorisasi tingkat aplikasi, jika Anda ingin mengendalikan aplikasi mana yang dapat mengakses API Anda, tetapi tidak dapat diakses oleh pengguna akhir tertentu. Hal ini sangat sesuai jika Anda ingin menggunakan fungsipembatasan laju, audit, atau penagihan. Otorisasi tingkat aplikasi mungkin tidak sesuai bagi API yang menyimpan data pribadi atau sensitif, kecuali Anda benar-benar memercayai konsumen Anda, misalnya, departemen pemerintahan lainnya.

Jika organisasi Anda mengelola API, Anda akan diharuskan untuk mengelola server otorisasi.

Kami menyarankan untuk menggunakan [OAuth 2.0](https://oauth.net/), kerangka kerja otorisasi terbuka (khususnya untuk jenis pemberian dengan Client Credential). Dengan layanan ini, setiap aplikasi yang terdaftar akan mendapat OAuth2 Bearer Token, yang dapat digunakan untuk membuat permintaan API atas nama aplikasi itu sendiri.

## Memberikan otorisasi tingkat pengguna

Gunakan otorisasi tingkat pengguna, jika Anda ingin mengendalikan pengguna akhir mana yang dapat mengakses API Anda. Hal ini sesuai bagi yang berhadapan dengan data pribadi atau sensitif.

Misalnya, [OAuth 2.0](https://oauth.net/) adalah metode otorisasi yang populer di pemerintahan, khususnya dengan jenis pemberian yang menggunakan Kode Otorisasi. Gunakan Cakupan OAuth 2.0 untuk kontrol akses yang lebih terperinci.

[OpenID Connect](http://openid.net/connect/) (OIDC), yang dibuat sebagai tambahan OAuth2, untuk digunakan bersama [Token Web JSON (JWT)](https://tools.ietf.org/html/rfc7519), mungkin cocok dalam beberapa kasus, misalnya sistem gabungan.

## Untuk privasi dan whitelisting

Gunakan whitelisting jika Anda ingin API Anda menjadi privat secara permanen atau sementara, misalnya untuk menjalankan [private beta](https://www.gov.uk/service-manual/agile-delivery/how-the-beta-phase-works) . Anda dapat melakukan whitelisting tiap aplikasi atau tiap pengguna.

Anda tidak boleh melakukan whitelisting alamat IP dari API yang Anda gunakan. Hal ini dikarenakan API mungkin diberikan menggunakan [Content Delivery Networks](https://en.wikipedia.org/wiki/Content_delivery_network) (CDN) dan penyeimbang beban yang terukur, yang bergantung pada alokasi dan pembagian alamat IP yang fleksibel dan cepat. Alih-alih melakukan whitelisting, Anda harus menggunakan [HTTPS egress proxy](https://en.wikipedia.org/wiki/Egress_filtering) .

## Mengikuti praktik baik untuk token dan izin

Anda harus:

-   memilih frekuensi dan periode kedaluwarsa penyegaran yang sesuai untuk token akses pengguna Anda - gagal menyegarkan token akses secara rutin dapat menimbulkan kerentanan;
    
-   memungkinkan pengguna Anda untuk mencabut otoritas;
    
-   membatalkan validasi token akses Anda sendiri dan memaksa penerbitan ulang, jika terdapat alasan untuk mencurigai token telah membahayakan;
    
-   menggunakan kata sandi sekali pakai berbasis waktu (TOTP) untuk keamanan tambahan pada API dengan otorisasi tingkat aplikasi;
    
-   menggunakan autentikasi multi-faktor (MFA) dan verifikasi identitas (IV) untuk keamanan tambahan di API dengan otorisasi tingkat pengguna;
    
-   memastikan token yang Anda berikan memiliki izin sesempit mungkin (menyempitkan izin berarti terdapat jauh lebih rendah risiko pada API Anda, jika token hilang oleh pengguna atau dalam bahaya).
    

## Memantau aktivitas API mencurigakan

Proses keamanan API hampir sama dengan proses keamanan sehari-hari Anda.

Pantau perilaku tidak biasa API sama seperti Anda memantau dengan ketat situs web apa pun. Perhatikan perubahan alamat IP atau pengguna yang menggunakan API pada waktu-waktu dalam sehari yang tidak biasa. UK memiliki pedoman Pusat Keamanan Siber Nasional (NCSC) mengenai [implement a monitoring strategy](https://www.ncsc.gov.uk/collection/10-steps-to-cyber-security?curPage=/collection/10-steps-to-cyber-security/the-10-steps) dan secara khusus tentang [how to monitor the security status of networks and systems](https://www.ncsc.gov.uk/collection/nis-directive?curPage=/collection/nis-directive/nis-objective-c/c1-security-monitoring).

## Ketika menamai dan meng-hosting-kan API Anda

Semua penamaan API dalam URL (termasuk nama dari ruang nama dan sumber daya) harus:

-   menggunakan kata benda dibandingkan kata kerja;
    
-   singkat, padat, dan dapat dipahami dengan jelas;
    
-   dapat ditebak oleh manusia, menghindari istilah teknis atau spesialis jika memungkinkan;
    
-   menggunakan tanda hubung dibandingkan garis bawah sebagai pemisah kata untuk nama beberapa kata.
    

Misalnya: `[api-name].api.gov.uk`.

## Menghindari penggunaan ruang nama

Secara umum, setiap API Anda harus memiliki domainnya sendiri, sama seperti setiap layanan yang memiliki domainnya sendiri. Hal ini juga akan menghindari perpencaran API dan menyederhanakan versi Anda.

## Kapan Anda harus memberikan beberapa API domain yang sama

Jika Anda memberikan beberapa API dan Anda memiliki kasus bisnis yang mengharuskan Anda menerapkan layanan yang sama untuk API tersebut, seperti manajemen dan pendekatan autentikasi serta keamanan yang sama, Anda mungkin harus mempertimbangkan:

-   memberikan semua API tersebut dari domain yang sama;
    
-   membedakannya melalui penggunaan ruang nama.
    

Ruang nama harus mencerminkan fungsi pemerintahan yang ditawarkan oleh API ini. Ruang nama boleh dalam bentuk tunggal atau jamak, tergantung situasi.

## Ketika menggunakan sub sumber daya

Sub sumber daya harus tampil di sumber daya yang berhubungan dengannya, tetapi tidak boleh lebih dari tiga kedalaman, misalnya:  `/resource/id/sub-resource/id/sub-sub-resource`.

Jika Anda mencapai tingkat ke tiga dari keterperincian (sub-sub-sumber), Anda harus meninjau kembali konstruksi sumber daya Anda untuk melihat apakah sebenarnya konstruksi tersebut merupakan gabungan dari beberapa sumber daya tingkat pertama atau kedua.

## Ketika menggunakan argumen kueri

Anda harus menggunakan parameter jalur untuk mengidentifikasi sumber daya khusus atau sumber daya. Misalnya, `/users/1`.

Anda harus hanya mengizinkan string kueri digunakan dalam permintaan GET guna memfilter nilai yang dikembalikan dari sumber daya individu, misalnya `/users?state=active or /users?page=2`.

Anda tidak boleh menggunakan string kueri di permintaan GET untuk tujuan identifikasi, misalnya, hindari menggunakan string kueri`/users?id=1`.

String kueri tidak boleh digunakan untuk menetapkan perilaku API Anda, misalnya `/users?action=getUser&id=1`.

## Ketika melakukan iterasi API Anda

Ketika melakukan iterasi API Anda untuk menambahkan atau membenahi fungsi baru, Anda harus meminimalkan gangguan untuk pengguna Anda, sehingga pengguna tidak dikenakan biaya yang tidak perlu.

Untuk meminimalkan gangguan untuk pengguna, Anda harus:

-   melakukan perubahan ¬backwards compatible jika memungkinkan - tentukan pengurai, abaikan properti yang tidak mereka harapkan atau pahami untuk memastikan perubahan mundur yang kompatibel (hal ini memungkinkan Anda untuk menambah bidang untuk memperbarui fungsi tanpa memerlukan perubahan ke aplikasi klien);
    
-   membuat titik akhir baru yang tersedia untuk perubahan yang signifikan,
    
-   berikan pemberitahuan untuk titik akhir yang menyusut.
    

Titik akhir baru tidak selalu harus menyertai fungsi baru jika titik akhir tersebut masih mempertahankan kompatibilitas mundur

## Ketika melakukan perubahan backwards yang tidak kompatibel

Ketika Anda harus melakukan perubahan backwards yang tidak kompatibel, Anda harus mempertimbangkan:

-   menaikkan angka versi di URL atau header HTTP (mulai dengan /v1/ dan kenaikan dengan angka keseluruhan)
    
-   mendukung baik titik akhir lama maupun baru secara paralel selama periode waktu yang sesuai sebelum menghentikan penggunaan titik akhir yang lama
    
-   memberi tahu pengguna API Anda cara memvalidasi data, misalnya, memberi tahu mereka kapan suatu bidang tidak akan ada, sehingga mereka dapat memastikan aturan validasi mereka akan memperlakukan bidang tersebut sebagai opsional
    

Terkadang, Anda harus melakukan perubahan yang lebih besar dan menyederhanakan struktur objek yang kompleks dengan melipat data dari beberapa objek secara bersamaan. Dalam kasus ini, buatlah objek baru tersedia di titik akhir baru, misalnya:

Gabungkan data tentang pengguna dan akun dari:

`/v1/users/123` and `/v1/accounts/123`

Untuk menghasilkan:

`/v1/consolidated-account/123`

## Mengatur kebijakan penyusutan yang jelas

Mengatur kebijakan penyusutan sehingga Anda tidak mendukung aplikasi klien lama selamanya.

Nyatakan berapa lama pengguna harus meningkatkan, dan bagaimana Anda akan memberi tahu mereka perihal tenggat waktu ini. Misalnya, di GDS, kami biasanya menghubungi pengembang secara langsung, tetapi kami juga mengumumkan penyusutan di tanggapan HTTP menggunakan header ‘Peringatan’.

## Memberikan pengguna layanan uji

Konsumen API Anda akan ingin menguji aplikasinya terhadap API Anda sebelum diluncurkan. Jika Anda memiliki API hanya baca, maka Anda tidak perlu memberikan layanan uji.

Memberikan pengguna layanan uji (terkadang disebut sebagai sandbox).

Jika API Anda memiliki perilaku yang kompleks atau rumit, pertimbangkan untuk memberikan layanan uji yang menyerupai layanan sebenarnya sesering mungkin, tetapi selalu ingat biaya untuk melakukan hal ini.

Jika API Anda memerlukan otorisasi, misalnya, menggunakan OAuth 2.0, Anda perlu menyertakan ini di layanan uji atau memberikan beberapa tingkat layanan uji.

Untuk membantu Anda memutuskan apa saja yang harus diberikan, lakukan penelitian pengguna - tanyakan kepada konsumen API Anda seperti apa menurut mereka layanan uji yang memadai itu.

## Menguji kepatuhan API Anda

Anda harus memberikan tim pengembang Anda kemampuan untuk menguji API Anda menggunakan data uji sampel, jika memungkinkan. Menguji API seharusnya tidak melibatkan penggunaan sistem produksi dan data produksi.

## Menguji kinerja dan skalabilitas API Anda

Untuk API akses data terbuka yang sangat dapat disinggahkan, Jejaring Penyampaian Konten (CDN) yang dikonfigurasi dengan baik dapat memberikan skalabilitas yang memadai.

Untuk API yang tidak memiliki karakteristik tersebut, Anda harus mengatur kuota harapan untuk pengguna Anda dalam hal kapasitas dan nilai yang tersedia. Mulai dari yang kecil, berdasarkan kebutuhan pengguna, dan tanggapi permintaan untuk meningkatkan kapasitas dengan memastikan API Anda dapat memenuhi kuota yang telah Anda atur.

Pastikan pengguna dapat menguji API penuh Anda hingga kuota yang telah Anda atur.

Melaksanakan kuota yang telah Anda atur, bahkan jika Anda telah melebihi kapasitas. Hal ini memastikan pengguna Anda akan mendapatkan pengalaman yang konsisten ketika Anda belum melebihi kapasitas, dan akan dirancang dan dibuat untuk menangani kuota API Anda.

Seperti halnya layanan yang bertatap langsung dengan pengguna, Anda harus menguji kapasitas API Anda di lingkungan yang mewakili untuk membantu memastikan Anda dapat memenuhi permintaan.

Jika API memberikan informasi pribadi atau privat, Anda sebagai pengontrol data, harus memberikan batas waktu yang cukup pada setiap informasi yang disinggahkan dalam jaringan pengiriman Anda.

## Mendokumentasikan API Anda

Untuk mendokumentasikan pemulaan API Anda, Anda harus:

-   menggunakan [OpenAPI 3 Specification](https://www.openapis.org/) jika memungkinkan, untuk menghasilkan dokumentasi (disarankan oleh Dewan Standar Terbuka)
    
-   ikuti pedoman di [how to document APIs](https://www.gov.uk/guidance/how-to-document-apis) dan [how to write API reference documentation](https://www.gov.uk/guidance/writing-api-reference-documentation)
    
-   berikan kode sampel untuk menggambarkan cara memanggil API dan untuk memberi tahu pengguna tanggapan apa yang dapat mereka harapkan
    

Dalam dokumentasi Anda, Anda harus menyertakan:

-   informasi kontekstual/ikhtisar - apa yang dapat dilakukan oleh API, siapa yang mungkin akan menggunakannya, dan dalam keadaan apa API digunakan;
    
-   aturan bisnis dan data - dalam keadaan apa data tersedia/tidak tersedia;
    
-   skenario kesalahan - prasyarat dan hasil - termasuk kode dan pesan kesalahan;
    
-   detail pada layanan uji - cara menggunakannya dan cara menyimulasikan berbagai skenario berhasil dan kesalahan;
    
-   detail lengkap parameter permintaan dan tanggapan, termasuk makna, jenis data, dan hambatan apa pun lainnya. Berikan contoh nilai yang valid.
    
-   aturan tentang [information handling](https://www.gov.uk/government/publications/information-asset-owner-role-guidance) , [incident management](https://www.ncsc.gov.uk/incident-management) dan [risk management](https://www.ncsc.gov.uk/incident-management)
    
-   metode [authentication](https://www.ncsc.gov.uk/guidance/user-authentication-systems-implementation-guide-3) (dan bagaimana metode tersebut memengaruhi interoperabilitas layanan, single sign-on, dan pembatasan nilai)
    
-   aturan otorisasi apa pun, misalnya, penggunaan OAuth 2.0 dan secara khusus yang cakupannya diperlukan untuk API ini
    
-   perubahan rancangan (saat ini dan terencana) dan informasi versi
    
-   ketersediaan, latensi, kepemilikan, kebijakan penyusutan dan kemampuan status
    
-   pendekatan terhadap [backwards compatibility](https://gdstechnology.blog.gov.uk/2016/07/26/considering-our-approach-to-api-iteration/)
    
-   pedoman tentang konfigurasi API untuk memastikan kerangka kerja tata kelola apa pun yang relevan
    
-   informasi keamanan
    
-   biaya penggunaan, jika berlaku
    

Anda harus selalu memastikan dokumentasi Anda jelas, dan [communicate when changes are made](https://gdstechnology.blog.gov.uk/2016/07/26/considering-our-approach-to-api-iteration/).
