---
permalink: "/writing-API-reference-documentation-bh"
redirect_from:
  - /writing_api_reference_docs_bh
---

# Menulis dokumentasi referensi API

 Panduan ini membahas alat dan proses yang Anda butuhkan untuk membantu Anda menulis dokumentasi referensi API Anda

Harap diperhatikan - bahwa dokumen ini diterjemahkan dari pedoman yang digunakan untuk membuat API di UK. Dokumen ini berisi tautan ke dokumen lain dalam bahasa Inggris. Jika Anda tertarik dengan versi terjemahan dari dokumen ini, silakan hubungi Delivery Manager Senior GDMP Anda:

Henny.Bird@digital.cabinet-office.gov.uk

Referensi API seringkali merupakan bagian yang terbesar dan paling banyak digunakan dalam dokumentasi API Anda. Referensi API kadang dipublikasikan pada halaman yang terpisah dari [conceptual or getting started information](https://www.gov.uk/guidance/how-to-document-apis). Anda harus memublikasikan semua informasi referensi.

Panduan ini mengasumsikan Anda mengikuti [government API standards](https://www.gov.uk/guidance/gds-api-technical-and-data-standards) , yang membuat API [RESTful](https://restfulapi.net/), yang menggunakan permintaan verba HTTP untuk memanipulasi data.

## Membuat referensi API dari kode

Anda dapat menulis referensi API dengan tangan atau membuat referensi secara otomatis dari komentar dalam kode API itu sendiri.

Ada banyak alat yang memungkinkan Anda membuat berkas HTML secara otomatis dari komentar kode pengembang untuk ditampilkan kepada pengguna Anda. Manfaat dari pendekatan ini adalah ketika pengembang memperbarui komentar dalam kode mereka, dokumen Anda juga akan diperbarui.

Anda masih perlu merapikan informasi referensi setelah dibuat dan memastikannya sesuai dengan panduan yang menyertainya. Idealnya, Anda akan memiliki [technical writer](https://www.gov.uk/government/publications/technical-writer-role-description/technical-writer-role-description) untuk membantu Anda melakukannya.

Anda dapat menggunakan sejumlah kriteria untuk memilih di antara berbagai alat pembuatan otomatis. Selain [standard considerations when choosing new technology](https://www.gov.uk/service-manual/technology/choosing-technology-an-introduction), Anda juga harus mempertimbangkan apakah alat tersebut:

-   mendukung bahasa pemrograman yang Anda butuhkan;

-   memberi output dalam format yang sesuai, misalnya HTML;

-   mendukung opsi format yang mungkin Anda butuhkan, misalnya sampel kode, tabel, gambar.


API terbuka (sebelumnya dikenal sebagai Swagger) umumnya digunakan di pemerintahan untuk dokumentasi referensi API RESTful. Alat alternatif meliputi:

-   RAML,

-   Dokumen I/O,

-   Cetak Biru API,

-   Skema JSON.


## Apa yang perlu dimasukkan dalam referensi API

Referensi API menjelaskan semua yang dilakukan oleh API termasuk:

-   sumber daya,

-   titik akhir dan metode,

-   Parameter,

-   contoh permintaan dan respons,

-   kode kesalahan.


### Sumber daya

Sumber daya adalah sepotong data atau sekumpulan data yang disediakan oleh API dalam menanggapi permintaan, misalnya baris dalam basis data. Berikan deskripsi singkat tentang masing-masing sumber daya API Anda, sehingga pengguna mengetahui dengan jelas untuk apa sumber daya tersebut dan mengapa mereka harus memanggil sumber daya tersebut. Anda dapat membaca selengkapnya tentang apa itu sumber daya di [Roy Fielding’s dissertation](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm%23sec_5_2_1_1) .

### Titik akhir dan metode

Di bawah masing-masing deskripsi sumber daya, sebutkan semua titik akhir yang terkait dengan sumber daya itu. Titik akhir adalah jalur yang akan digunakan pengguna (atau panggilan) untuk mengakses atau memanipulasi sumber daya. API yang Anda dokumentasikan kemungkinan dikembangkan untuk menerima metode standar dalam panggilan sumber daya, misalnya GET, PUT, POST, atau DELETE. Meskipun metode ini bersifat standar, Anda tetap harus mencantumkan metode yang berlaku untuk API yang Anda dokumentasikan dan menjelaskan fungsinya.

Misalnya, diUK, [Companies House API documentation provides a table for each endpoint with a short description and the method](https://developer.companieshouse.gov.uk/api/docs/company/company_number/registered-office-address/registered-office-address.html).

### Parameter dan argumen

Parameter adalah filter opsional yang memengaruhi apa yang akan dikembalikan oleh API. Di sebelah titik akhir yang didokumentasikan, Anda harus menyebutkan segala parameter untuk titik akhir tersebut disertai deskripsi singkat. Jika Anda memiliki jenis parameter yang berbeda-beda, misalnya, parameter tajuk dan jalur, Anda perlu mengelompokkannya berdasarkan jenis.

Argumen adalah input spesifik dari suatu parameter. Anda mungkin perlu memasukkan ini. Misalnya, di UK, [GOV.UK Notify Python library documentation includes all possible arguments for each method](https://docs.notifications.service.gov.uk/python.html#send-an-email).

Tentukan jenis dan batasan data untuk parameter dan argumen, dan berikan contoh yang relevan.

### Contoh permintaan dan respons

Salah satu hal paling berguna dalam referensi API adalah contoh kode. Untuk setiap titik akhir, Anda harus memberikan contoh permintaan, disertai contoh parameter (jika tersedia untuk titik akhir itu).

Permintaan biasanya dipublikasikan sebagai cuplikan kode menggunakan curl tetapi dapat berguna untuk menunjukkan permintaan dalam berbagai bahasa pemrograman jika tersedia.

Anda juga harus memublikasikan contoh respons sebagai cuplikan kode, dalam bahasa pemrograman yang sama dengan contoh permintaan. Contoh respons harus menampilkan respons tepat yang dapat diharapkan pengguna dari contoh permintaan.

Ketahuilah bahwa contoh Anda tidak akan memberi tahu pengguna Anda arti bidang tersebut, misalnya jika bidang tersebut bersifat opsional atau wajib, atau jika berisi kendala apa pun. Jika contoh belum menjelaskan informasi ini, pertimbangkan untuk menyertakan penjelasan di samping contoh Anda.

### Kode respons kesalahan

Anda harus memasukkan respons kesalahan spesifik yang terkait dengan titik akhir yang dekat dengan dokumentasi titik akhir atau memublikasikannya bersama di akhir referensi API Anda. Sekalipun Anda hanya memperkirakan respons standar seperti 400 atau 200, Anda harus menginterpretasikan arti spesifiknya untuk API Anda.

Misalnya, di UK [GOV.UK content API documentation](https://content-api.publishing.service.gov.uk/reference.html#responses) menyertakan tabel dengan nama titik akhir, kode kesalahan, apa artinya, dan apa penyebabnya. Ini akan membantu pengguna Anda memecahkan masalah apa pun yang mungkin mereka alami dengan API Anda sebelum menghubungi Anda untuk mendapatkan dukungan.

## Menguji dokumentasi Anda

Anda harus selalu mempratijau perubahan pada dokumentasi Anda sebelum menerbitkannya. Jika Anda mendokumentasikan API RESTful , Anda dapat menguji contoh permintaan dan respons Anda menggunakan curl atau alat seperti [Postman](https://www.getpostman.com/) (alat gratis).

## Panduan terkait

Panduan ini mungkin juga berguna untuk Anda:

-   [Documenting APIs](https://www.gov.uk/guidance/how-to-document-apis)

-   [API standards](https://www.gov.uk/guidance/gds-api-technical-and-data-standards)

-   [Tom Johnson’s guide to API documentation](http://idratherbewriting.com/learnapidoc/)


Diterbitkan pada 15 Februari 2019
