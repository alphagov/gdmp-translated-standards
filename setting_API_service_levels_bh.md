# Mengatur tingkat layanan API

Optimalkan indikator tingkat layanan API Anda berdasarkan kebutuhan pengguna Anda.

Harap diperhatikan - bahwa dokumen ini diterjemahkan dari pedoman yang digunakan untuk membuat API di UK. Dokumen ini berisi tautan ke dokumen lain dalam bahasa Inggris. Jika Anda tertarik dengan versi terjemahan dari dokumen ini, silakan hubungi Delivery Manager Senior GDMP Anda:

Henny.Bird@digital.cabinet-office.gov.uk

Saat mengelola API Anda sebagai layanan, Anda perlu memahami apa yang penting bagi pengguna Anda dan apa yang akan Anda kerjakan dalam perjanjian tingkat layanan Anda. Anda mungkin perlu mempertimbangkan:

-   latensi permintaan,
    
-   throughput sistem,
    
-   ketersediaan dan waktu henti.
    

Masing-masing aspek ini adalah indikator tingkat layanan (SLI). Panduan ini menjelaskan berbagai SLI dan bagaimana Anda dapat mengoptimalkannya berdasarkan teknik yang telah berhasil untuk beberapa tim pengembangan pemerintah. Anda harus mengoptimalkan SLI Anda berdasarkan jumlah pengguna API Anda dan kebutuhan mereka.

Tingkat layanan yang tinggi mungkin mahal untuk diberikan, jadi Anda tidak harus menetapkannya lebih tinggi dari yang diperlukan.

## Menentukan latensi permintaan terbaik untuk API Anda

Salah satu SLI yang paling penting untuk disepakati adalah berapa lama bagi permintaan API untuk mengembalikan respons.

Merancang API untuk kinerja dalam latensi permintaan yang lebih tinggi dari yang dibutuhkan pengguna dapat memakan banyak biaya, jadi Anda perlu melakukan penilaian tentang konteks di mana Anda bekerja. Misalnya, API jaringan kereta api harus dapat memberikan data tentang keberadaan kereta api dalam waktu nyata jika tidak ingin menanggung konsekuensi yang berat. Namun, API pajak mungkin tidak perlu memproses pengembalian pajak dengan cepat.

Untuk meningkatkan latensi API Anda, Anda mungkin perlu mempertimbangkan:

-   memasang jaringan pengiriman konten;
    
-   merekayasa API kueri data berat backend untuk mengambil sejumlah besar data yang jarang cocok dengan API frontend ‘chatty’ untuk mengambil data dalam jumlah kecil secara rutin;
    
-   membuat cache data API Anda - pertimbangkan untuk membuat permintaan GET dapat dijadikan cache agar tidak memaksa setiap panggilan API untuk membuat lalu lintas jaringan dan menekan basis data Anda;
    
-   menginvestasikan sumber daya di [data wrangling.](https://en.wikipedia.org/wiki/Data_wrangling)
    

Pendekatan ini dapat mengurangi biaya jaringan dan meningkatkan kinerja menggunakan perangkat keras yang sama. Namun, semua pendekatan ini akan tergantung pada seberapa segar kebutuhan data Anda. Pengguna Anda kadang-kadang mungkin memerlukan kemampuan untuk mengakses data API Anda selama gangguan jaringan ketika data tidak tersedia dari server.

Saat melakukan pembuatan cache, Anda harus:

-   membuat cache sedekat mungkin dengan pengguna - ini menghentikan permintaan yang menyebabkan aktivitas jaringan tambahan
    
-   menambahkan tajuk Cache-Control atau Vary HTTP - ini akan menyampaikan kebijakan pembuatan cache kepada pengguna, misalnya bagaimana sumber dijadikan cache, di mana sumber dijadikan cache, dan masa pakai maksimum yang bisa dicapai sebelum kedaluwarsa
    

Jika Anda memiliki API yang tidak stabil, Anda tidak boleh membuat cache secara default.

Anda tidak boleh membuat cache dari data sensitif atau pengguna tertentu apa pun.

Saat mengembangkan [data API](https://gdstechnology.blog.gov.uk/2017/02/03/providing-access-to-datasets-through-apis/) (bukan API transaksional), Anda harus mempertimbangkan apakah akan mengizinkan pengguna membuat permintaan data besar atau membatasi pengguna untuk membuat sejumlah permintaan yang lebih kecil. Jika Anda yakin permintaan data besar diperlukan untuk pengguna, Anda mungkin perlu mempertimbangkan:

-   menggunakan kompresi data seperti file GZIP - jika API Anda RESTful, izinkan pengguna mengirim tajuk yang mengatakan mereka tidak akan menerima data terkompresi;
    
-   memberi nomor halaman permintaan - memecah sumber daya API Anda menjadi potongan yang dapat dikelola memungkinkan pengguna membuat beberapa permintaan, bukan permintaan tunggal;
    
-   mengunduh set data sebagai file CSV secara berkala - mengambil snapshot data Anda secara berkala dan menyimpannya dalam cache untuk diunduh oleh pengguna lebih efektif dibanding meminta pengguna untuk membuat berkas CSV secara dinamis dari basis data aktif Anda;
    
-   menggunakan penyimpanan data operasional - ini berguna jika data Anda berada di banyak sistem yang berbeda dan Anda ingin membuat tahap data agar mudah diakses berdasarkan permintaan pengguna.
    

Dengan membuat tahap data menggunakan penyimpanan data operasional, cap waktu data Anda akan dicatat. Saat menggunakan teknik ini, Anda harus mempertimbangkan seberapa sering Anda menyinkronkan data yang dibuat menjadi tahap dengan set data utama Anda.

Penyimpanan data operasional mungkin tidak cocok untuk pengguna API yang membutuhkan tersedianya data terbaru. Menjaga agar penyimpanan data operasional selalu terbarukan secara waktu nyata tidak efektif dari segi biaya.

## Throughput sistem untuk API transaksional

Throughput sistem adalah jumlah permintaan yang dapat dibuat ke API Anda dalam periode waktu tertentu. Anda dapat memilih untuk menerapkan ‘throttling', atau ‘pembatasan laju’ untuk menetapkan batas jumlah permintaan yang dapat dibuat aplikasi ke API Anda

Anda tidak perlu memberi batas laju pada API nontransaksional yang menyediakan data terbuka.

Jika Anda memiliki API transaksional, Anda dapat memilih untuk menerapkan pembatasan laju untuk:

-   mengelola kapasitas dan biaya - API transaksional memiliki biaya per permintaan yang tinggi dibandingkan dengan API data karena setiap transaksi melewati seluruh tumpukan, dan mungkin menghasilkan setidaknya satu basis data penulisan;
    
-   mendorong konsumsi yang bertanggung jawab;
    
-   melindungi dari serangan denial-of-service (DoS);
    
-   menegakkan semantik ketat yang menentukan tajuk dan nilai yang akan digunakan.
    

Saat menerapkan pembatasan laju atau throttling, Anda tidak boleh membiarkan pengguna Anda melampaui batas yang Anda tetapkan meski jika Anda memiliki kapasitas yang kosong. Hal ini karena jika Anda perlu memakai kapasitas kosong di masa mendatang dan pengguna telah mengembangkan aplikasi mereka dengan laju yang lebih tinggi dalam pertimbangan, aplikasi mereka dapat rusak. Untuk alasan yang sama, hindari memberlakukan batas yang membatasi laju secara retroaktif.

Saat menerapkan pembatasan laju untuk API transaksional, Anda harus:

-   berkomunikasi dengan pengguna dengan jelas - misalnya, gunakan X-RateLimit_remaining di tajuk untuk memberi tahu mereka ketika mereka hampir mencapai batas Anda;
    
-   memahami keterbatasan kinerja sistem backend - sistem backend biasanya merupakan tautan terlemah dalam hal kinerja, bukan dalam hal API
    
-   memahami bahwa pengguna mungkin ingin sering menggunakan API Anda untuk jangka waktu pendek dan ini mungkin tidak dapat diprediksi - dalam kasus ini, pertimbangkan untuk menetapkan [burst limit](https://apifriends.com/api-management/api-quota/)
    

Saat menetapkan burst limit, pertimbangkan volume fasilitas ini. Misalnya, batas laju Anda bisa sebesar 10.000 permintaan per menit dengan burst limit sebesar 20.000 permintaan per menit hingga 5 menit.

Baca [government API technical and data standards](https://www.gov.uk/guidance/gds-api-technical-and-data-standards) untuk informasi selengkapnya tentang pembatasan laju.

## Mengelola ketersediaan dan downtime API Anda

Saat mempertimbangkan SLI tentang ketersediaan, Anda perlu memikirkan jenis downtime yang akan mengganggu API Anda. Misalnya, API Anda dapat drop 1 dari 20 koneksi atau tidak dapat dijangkau selama 2 jam sehari. Kedua skenario ini dapat menghasilkan persentase waktu kerja yang sama, tetapi salah satunya mungkin lebih bermasalah bagi pengguna dari yang lainnya.

Anda juga perlu memastikan bahwa Anda menyeimbangkan kebutuhan ketersediaan dengan biaya untuk mencapainya. Jika pengguna cenderung tidak menggunakan API Anda di dini hari, maka pekerjaan pemeliharaan API perlu dilakukan pada saat tersebut.

Cara Anda mengelola waktu henti API Anda akan berimplikasi pada biaya tim dukungan panggilan. Anda perlu memutuskan kapan waktu yang tepat untuk membayar uang lembur tim teknologi dalam mengurus downtime API Anda.

Untuk meningkatkan ketersediaan API Anda, Anda dapat mempertimbangkan untuk meningkatkan sistem sumber Anda atau meletakkan cache di depannya.

Saat merancang API ketersediaan rendah, pertimbangkan penggunaan respons HTTP 202. Misalnya, untuk menunjukkan bahwa API telah menerima permintaan tetapi perlu menunggu untuk mengambil tindakan lebih lanjut.

## Panduan terkait

Untuk informasi lebih lanjut, lihat panduan Manual Layanan tentang [monitoring the status of a service](https://www.gov.uk/service-manual/technology/monitoring-the-status-of-your-service) dan [testing performance](https://www.gov.uk/service-manual/technology/test-your-services-performance) .

Diterbitkan pada 16 Januari 2019
