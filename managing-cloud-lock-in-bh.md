---
permalink: /managing-cloud-lock-in-bh
---

# Mengelola technical lock-in (ketergantungan teknis) di cloud

Pedoman ini menguraikan cara untuk membuat pilihan berbasis informasi tentang ketergantungan organisasi Anda pada teknologi cloud.

Harap diperhatikan - bahwa dokumen ini diterjemahkan dari pedoman yang digunakan untuk organisasi sektor publik yang mempertimbangkan untuk menggunakan cloud hosting di Inggris. Dokumen ini berisi tautan ke dokumen lain dalam bahasa Inggris. Jika Anda tertarik dengan versi terjemahan dari dokumen ini, silakan hubungi Delivery Manager Senior GDMP Anda:

Henny.Bird@digital.cabinet-office.gov.uk

Diterbitkan tanggal 17 Desember 2019

Dari:

[Government Digital Service](https://www.gov.uk/government/organisations/government-digital-service)

Saat menggunakan public cloud, Anda hanya membayar apa yang Anda gunakan dan menghindari biaya infrastruktur di muka. Ini dapat memberikan penghematan dan efisiensi yang signifikan bagi organisasi Anda dibandingkan dengan model pusat data tradisional.

Tetapi meskipun tersedia lebih banyak fleksibilitas di cloud, ada risiko Anda menjadi tergantung pada produk dan layanan dari penyedia tertentu. Ini disebut lock-in, di mana beralih dari satu teknologi atau penyedia ke yang lain itu sulit, menghabiskan banyak waktu dan biaya mahal yang tidak proporsional.

Biasanya, lock-in dianggap sebagai sesuatu yang harus dihindari organisasi. Namun, di cloud keuntungan dari lock-in seringkali lebih besar daripada kerugiannya. Misalnya, menggunakan penyedia cloud untuk mengelola siklus hidup penyimpanan Anda dapat mengarah pada lock-in, tetapi akan mengurangi pekerjaan yang dibutuhkan untuk mengelola layanan Anda. Menerima beberapa lock-in akan memungkinkan pengembang untuk:

-   menulis lebih sedikit kode
    
-   menghabiskan lebih sedikit waktu pada konfigurasi
    
-   membangun lebih sedikit layanan yang kompleks
    

Anda harus menyeimbangkan antara manfaat dan risiko potensial dari lock-in cloud ini, sehingga Anda bisa mendapatkan nilai terbaik dan [reduce the burden of future legacy technology](https://www.gov.uk/guidance/managing-legacy-technology).

## Berbagai jenis lock-in

Umumnya ada 2 jenis lock-in. Banyak organisasi memiliki pengalaman dengan lock-in komersial di mana kontrak yang panjang dan tidak fleksibel dengan penyedia dapat mencegah organisasi dari mengubah strategi teknologi mereka saat situasi berubah. Untuk menghindari lock-in, Anda harus memastikan Anda:

-   [agree contracts of appropriate length](https://www.gov.uk/guidance/g-cloud-buyers-guide)
    
-   mempertahankan kepemilikan kekayaan intelektual produk dan layanan Anda
    
-   mempertahankan akses ke semua data yang disimpan oleh pihak ketiga
    

Pemerintah Inggris memiliki [Crown Commercial Services’ contract management standards](https://www.gov.uk/government/publications/commercial-capability-contract-management-standards) untuk membantu hal ini

Dengan penyedia public cloud, biasanya penyedia memiliki kontrak bergulir, bayar sesuai penggunaan. Secara teori ini berarti Anda dapat berhenti menggunakan layanan kapan pun, tetapi pada praktiknya ini dapat menyulitkan. Ini adalah technical lock-in (ketergantungan teknis), dan dapat disebabkan oleh:

-   penyedia lain tidak menawarkan layanan yang setara
    
-   arsitektur teknis yang bergantung pada melakukan berbagai hal dengan cara tertentu
    
-   terlalu banyak integrasi yang erat dengan penyedia layanan/produk khusus
    
-   kurangnya keterampilan arsitektur teknis dalam organisasi Anda
    

Tidak mungkin untuk menghindari technical lock-in sepenuhnya. Bahkan layanan yang paling sederhana membutuhkan beberapa integrasi teknis dengan arsitektur yang ada. Tetapi keputusan yang Anda buat sebelumnya yang mungkin membuat pengembangan lebih mudah dapat mengarah kepada tingkat lock-in yang lebih besar yang lebih nyaman bagi Anda.

Misalnya, menggunakan layanan orkestrasi yang dikelola sepenuhnya untuk menggunakan aplikasi Anda sehingga Anda dapat menjadikannya lebih mudah bagi tim pengembangan untuk bersiap dan bekerja. Ini juga dapat menghilangkan risiko yang berasal dari pengembangan sesuai pesanan. Namun, ini dapat berarti peningkatan ketergantungan pada penyedia, yang menjadi kendala bagi pengembangan dengan meningkatnya kompleksitas layanan.

Setiap organisasi akan memiliki pandangan berbeda tentang peluang dan risiko seputar public cloud. Peluang dan risiko ini dapat bervariasi, jadi Anda membutuhkan kerja sama tim komersial dan teknis untuk memahami dan mengurangi risikonya. Ini juga layak untuk mempertimbangkan biaya alternatif atau manfaat membangun dan mengelola lingkungan jika Anda tidak menggunakan komponen public cloud yang dikelola.

## Memantau portofolio cloud Anda

Anda harus memantau portofolio cloud Anda untuk mengidentifikasi situasi lebih awal di mana biaya penghentian atau peralihan dapat meningkat tidak proporsional ketika pengembangan berlanjut. Pemantauan harus dilakukan oleh orang atau dewan tata kelola yang bertanggung jawab atas strategi cloud organisasi

Dewan tata kelola atau orang yang bertanggung jawab atas strategi cloud Anda harus memiliki gambaran umum tentang semua layanan cloud organisasi. Ini dapat membantu untuk mencegah duplikasi kontrak dengan penyedia dan memastikan interoperabilitas layanan di seluruh organisasi.

Dewan tata kelola atau orang yang bertanggung jawab untuk memantau strategi cloud Anda juga dapat menetapkan ekspektasi dasar tentang berapa besar biaya pengalihan yang tidak proporsional untuk organisasi atau layanan Anda. Misalnya, Anda mungkin senang mengetahui bahwa Anda perlu menginvestasikan lebih banyak waktu dan biaya peralihan untuk layanan yang mendapat lebih banyak manfaat dari penggunaan cloud daripada dengan komoditas atau layanan bermanfaat rendah.

[User research has shown a centrally coordinated approach to cloud can provide consistency](https://technology.blog.gov.uk/2019/08/30/finding-out-what-government-organisations-need-to-consider-when-using-cloud/)  di seluruh organisasi. Selain itu, dewan tata kelola atau orang yang bertanggung jawab atas strategi cloud Anda dapat mendorong penggunaan ulang pola. Proses audit internal dapat memastikan proyek sesuai dengan pendekatan strategis yang disepakati. Ini mirip dengan [how the UK spend controls pipelines work](https://www.gov.uk/guidance/set-up-a-commercial-or-digital-and-technology-spend-controls-pipeline).

Meskipun akan selalu ada beberapa tingkatan technical lock-in, ini akan membantu Anda memahami ada dampaknya terhadap organisasi Anda dan untuk meminimalkan dampaknya jika diperlukan.

## Memahami technical lock-in (ketergantungan teknis)

Technical lock-in memengaruhi berbagai organisasi dengan cara yang berbeda-beda. Anda dapat menjadi tergantung pada penyedia apakah Anda memiliki strategi cloud tunggal atau memanfaatkan beberapa teknologi cloud.

Untuk beberapa organisasi mungkin ada beberapa keuntungan untuk mengadopsi secara luas layanan dari penyedia tertentu. Ini termasuk:

-   integrasi erat dari layanan yang menyediakan pengalaman pengguna yang lebih baik
    
-   kemampuan untuk menggunakan ulang pola dan komponen umum di seluruh layanan
    
-   pendekatan keamanan dan pemantauan bersama yang didukung oleh alat manajemen yang matang
    
-   penagihan atau manajemen terkonsolidasi di seluruh aktivitas organisasi
    

Bagi organisasi lain, ini dapat menyebabkan tingkat ketergantungan pada satu penyedia yang tidak dapat diterima. Organisasi-organisasi ini dapat mengambil langkah untuk membatasi ketergantungan teknis mereka pada penyedia tertentu. Tetapi melindungi diri Anda dari provider lock-in (ketergantungan terhadap penyedia) membutuhkan biaya mahal, dan mungkin melibatkan sejumlah kompromi dalam pilihan teknologi Anda.

Misalnya, memastikan Anda dapat memindahkan infrastruktur Anda dari satu penyedia ke penyedia lainnya dapat menimbulkan tantangan teknis dan biaya yang signifikan. Mencoba untuk menghindari layanan khusus pada penyedia tertentu itu sulit dan dapat mengakibatkan pengurangan fungsionalitas pada platform tertentu.

Menghindari layanan yang sangat terkustomisasi ini seringkali dapat menyebabkan organisasi hanya dapat menggunakan solusi Layanan yang Menyediakan Infrastruktur (Iaas) dasar karena mereka melihat layanan cloud native membutuhkan terlalu banyak lock-in (ketergantungan). Anda akan kehilangan manfaat lain dari penggunaan layanan cloud native ini, seperti nilai tambah yang signifikan yang dapat ditawarkan manajemen atau pemantauan kunci.

Pusat Keamanan Siber Nasional Inggris/The UK’s National Cyber Security Centre (NCSC) menemukan sejumlah [benefits when using serverless technology](https://www.ncsc.gov.uk/blog-post/cloud-security-made-easier-with-serverless).. Misalnya, teknologi tanpa server:

-   dapat memudahkan patching
    
-   dapat mencegah serangan umum
    
-   mengintegrasikan banyak kemampuan pemantauan dan yang ditawarkan platform cloud modern secara lebih baik
    

## Menyeimbangkan risiko dan peluang di cloud

Jika ragu, timbang nilai layanan cloud yang ditawarkan kepada organisasi Anda terhadap kemungkinan beralih penyedia. Mempertimbangkan kriteria-kriteria tersebut pada grafik mungkin bermanfaat.

Layanan cloud biasanya memberikan nilai dengan menawarkan kemampuan yang tidak dapat Anda beri pada diri sendiri dengan biaya yang lebih rendah dari yang bisa Anda dapatkan secara internal. Misalnya, pemantauan keamanan terintegrasi atau penyeimbangan muatan otomatis. Ini berarti staf Anda bebas untuk berfokus pada tugas yang spesifik untuk tujuan bisnis Anda.

Dengan menempatkan layanan Anda pada grafik yang membandingkan nilai dan portabilitas, akan lebih mudah untuk segera menentukan seberapa banyak risiko lock-in yang menurut Anda dapat diterima. Anda harus berupaya memaksimalkan baik nilai dan portabilitas layanan jika memungkinkan. Anda dapat memilih untuk menerima tingkat portabilitas yang lebih rendah jika layanan menawarkan value for money yang baik.

![](https://lh4.googleusercontent.com/jCz3_A6EoptLH1YKQKexPteOFuyG4iyaQscb7sHFOamxI8irtfRQCaDHmnC11ULReLLorC8UBr49qqoeaxmx4HNrdAHlb64SHMiKpvYEfgXGxZW45zVYnvj_buvByQpJEJ1c2EgU-JuKHum0bQ)

Grafik 4 menampilkan 4 contoh nilai akhir yang berlawanan dan spektrum portabilitas, menunjukkan seberapa besar lock-in dapat diterima serta jenis layanan apa yang dapat Anda temukan di berbagai spektrum akhir.

Grafik menampilkan:

-   Anda harus menghindari layanan pada kuadran nilai rendah dan portabilitas rendah
    
-   di mana layanan memberikan nilai tinggi tetapi portabilitas rendah, tingkatan lock-in mungkin dapat diterima
    
-   banyak layanan umum dan non-kompleks akan ditemukan pada portabilitas tinggi, kuadran nilai rendah
    
-   sulit untuk menemukan layanan dengan portabilitas tinggi dan nilai tinggi tetapi layanan ini memang ada, ini dapat menjadi nilai yang baik dan menawarkan risiko lock-in yang rendah
    

Misalnya, [serverless technology](https://en.wikipedia.org/wiki/Serverless_computing) dapat memiliki portabilitas rendah, tetapi nilai tinggi yang diberikan, seperti patching dan penyebaran otomatis, menjadikannya layak untuk dipertimbangkan. Saat portabilitas sangat rendah, Anda harus mempertimbangkan bagaimana Anda akan mengganti penyedia di masa mendatang

Contoh lainnya dapat berupa algoritma pembelajaran mesin yang kompleks, yang sudah dibuat sebelumnya. Nilai bagi organisasi Anda dengan tidak harus membuat dan melatih algoritma Anda sendiri dapat lebih besar dari risiko bahwa ini tidak begitu portabel.

Di sisi lain, memilih layanan penyimpanan objek yang relatif tidak jelas karena fitur yang berguna adalah contoh sesuatu yang harus dihindari, jika ini tidak menggunakan standar umum. Kurangnya portabilitas tidak layak dipertukarkan dengan fitur tambahan, karena ini tidak memberikan nilai lebih dibandingkan alternatif populer.

Pada tingkat strategis, organisasi Anda harus menetapkan ekspektasi bagaimana tim penyediaan harus [evaluate different hosting options](https://www.gov.uk/service-manual/technology/deciding-how-to-host-your-service)  dan di mana Anda harus memprioritaskan nilai dibandingkan portabilitas. Anda juga harus memastikan Anda memahami tingkat kesiapan tim untuk beralih penyedia hosting.

Untuk menilai kemampuan tim Anda untuk beralih penyedia, sejumlah organisasi secara berkala mengevaluasi ulang estimasi biaya peralihan dengan membangun ulang atau menguji komponen penting pada berbagai lingkungan penyedia cloud. Penilaian ulang yang berkelanjutan ini dapat membantu Anda untuk memastikan keakuratan penilaian risiko.

Pada tingkat produk dan layanan individu, rencana hosting dan [business cases](https://www.gov.uk/guidance/how-to-assess-a-hosting-business-case) harus menyertakan estimasi biaya (setelah semua diskon atau manfaat yang dinegosiasikan telah lewat) dan waktu untuk keluar dari pengaturan hosting.

## Mengelola technical lock-in (ketergantungan teknis)

Jika Anda memutuskan ingin mengambil langkah-langkah teknis untuk mengurangi provider lock-in (ketergantungan terhadap penyedia), pendekatan Anda akan berubah tergantung pada jenis penyebaran yang Anda miliki.

Pada tingkat strategis, organisasi yang menggunakan penyedia cloud tunggal harus mengembangkan rencana darurat jika terjadi perubahan strategi, seperti mengalihkan layanan ke penyedia lain. Organisasi yang memiliki strategi multi cloud perlu merencanakan bagaimana mereka dapat memindahkan komponen atau layanan individu ke pengaturan hosting lainnya, dan mungkin mengujinya secara berkala.

Tim penyedia yang bekerja pada produk dan layanan individu juga harus membuat keputusan dengan pandangan bahwa mereka mungkin perlu untuk beralih penyedia di masa mendatang.

Strategi penghentian harus seimbang antara dampak peralihan penyedia dan manfaat mempertahankan penyedia. Misalnya, Anda mungkin mengizinkan lebih lama untuk memindahkan layanan karena jumlah integrasi menyediakan banyak nilai bagi organisasi Anda.

Untuk Software as a Service (SaaS), yang berarti memilih produk yang menggunakan standar dan format terbuka, jadi Anda memiliki kendali atas data Anda. Ini berarti Anda memiliki opsi untuk mengekspor data Anda ke lingkungan yang baru. Untuk Platform as a Service/Layanan yang Menyediakan Platform (PaaS) dan IaaS, ini dapat berarti [using open source](https://www.gov.uk/guidance/be-open-and-use-open-source) jika memungkinkan, menggabungkan komponen Anda secara bebas dan independen (loosely coupling) sehingga Anda dapat dengan mudah menggantikannya, ata menggunakan infrastruktur sebagai alat kode yang bekerja di berbagai platform cloud.

Penilaian terhadap penyedia cloud Anda tidak boleh berhenti setelah pengadaan barang dan jasa. Anda harus [use agile methods to continually review your hosting arrangements](https://www.gov.uk/service-manual/agile-delivery)  untuk memastikan mereka memberikan value for money yang terbaik. Mengoptimalkan pengeluaran Anda di cloud akan membantu Anda untuk memastikan Anda menggunakan layanan secara efisien, tetapi Anda harus melengkapinya dengan mengevaluasi teknologi baru saat tersedia.

## Membangun tim untuk mengelola penyedia layanan cloud Anda

Penyebab umum technical lock-in adalah ketersediaan keterampilan dan pengetahuan. Jika Anda memiliki tim dengan lebih banyak pengalaman dari satu penyedia, mungkin terasa lebih mudah dalam jangka pendek untuk melanjutkan penggunaan layanan penyedia tersebut.

Beberapa penyedia cloud menawarkan pelatihan gratis untuk menggunakan produk mereka, tetapi ini dapat menyebabkan peningkatan ketergantungan pada produk tersebut. Demikian halnya, banyak penyedia juga menawarkan dukungan perusahaan dan komunitas untuk menambah keterampilan tim internal Anda, meskipun ini bisa mahal.

Pada tingkat strategis, Anda harus menyewa orang dengan keterampilan yang tepat untuk memenuhi persyaratan teknis jangka pendek Anda. Tetapi Anda juga harus memastikan Anda dapat mengakses pengetahuan tentang berbagai solusi teknis, mungkin melalui dewan tata kelola/orang yang bertanggung jawab atas strategi cloud atau komunitas arsitektur Anda. Ini berarti Anda memiliki perspektif pasar cloud yang tepat dan dapat membuat keputusan berbasis informasi untuk masa mendatang.

Pada tingkat produk dan layanan individual, Anda harus membangun tim multidisipliner untuk menyatukan pengetahuan yang tepat untuk memilih dan menggunakan solusi cloud. Ini berarti menyatukan pengadaan barang dan jasa, keuangan, dan spesialis teknologi untuk membuat keputusan kolaboratif tentang cloud dan untuk memahami keuntungan dan kerugian berbagai jenis cloud lock-in (ketergantungan terhadap cloud).

## Pedoman terkait

Kebijakan dan pedoman yang tersedia meliputi:

-   [the UK government’s Cloud First policy](https://www.gov.uk/guidance/government-cloud-first-policy)
    
-   [the Technology Code of Practice](https://www.gov.uk/government/publications/technology-code-of-practice/technology-code-of-practice)
    
-   [the Service Manual](https://www.gov.uk/service-manual)
    
-   [how to assess a hosting business case](https://www.gov.uk/guidance/how-to-assess-a-hosting-business-case)
    

Diterbitkan pada tanggal 17 Desember 2019
