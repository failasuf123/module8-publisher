"# module8-publisher" 
### Excercise
a. Program publisher kita akan mengirimkan 5 data (event) ke message broker setiap kali dijalankan. Hal ini terlihat dari kode publisher yang mengirimkan 5 event dengan data yang telah ditentukan ke message broker dalam satu kali eksekusi.

b. URL "amqp://guest:guest@localhost:5672" yang sama digunakan di program subscriber dan publisher memiliki arti bahwa keduanya terhubung ke message broker yang sama menggunakan protokol AMQP. URL tersebut mengandung informasi tentang koneksi ke message broker, di mana "guest:guest" adalah kredensial untuk masuk (username dan password), dan "localhost:5672" adalah alamat dan port dari message broker yang digunakan. Dengan menggunakan URL yang sama, subscriber dan publisher dapat berkomunikasi dengan message broker yang sama untuk mengirim dan menerima pesan

### Tutorial
1. Screen Shoot Welcome Screen
    ![Example Image](/images/welcomepage.png)

2. Subcsriber Console
    ![Subscriber1 Image](/images/subscriber1.png)

    ### Proses yang terjadi
    Publisher Mengirim Event:
    - Saat saya menjalankan cargo run pada publisher, proyek tersebut akan mengirimkan event ke message broker menggunakan protokol AMQP.

    Event Diproses oleh Message Broker:
    - Message broker (misalnya, RabbitMQ) menerima event-event yang dikirimkan oleh publisher.
    - Broker menyimpan event-event ini dan menunggu subscriber yang tertarik untuk mengkonsumsinya.

    Subscriber Mengonsumsi Event:
    - Saat saya menjalankan subscriber akan melakukan koneksi ke message broker menggunakan protokol AMQP.
    -  Subscriber mendaftar untuk mengonsumsi event-event tertentu, dalam hal ini, event dengan topik "user_created".
    - Ketika event-event baru dengan topik "user_created" tersedia di broker, subscriber secara otomatis mengonsumsi dan memproses event tersebut.
    Pengolahan Data oleh Subscriber:

3. Page of RabbitMq when Cargo run
    ![RabbitMq1 Image](/images/rabbitmq.png)

    Lonjakan (spike) dalam konteks ini merujuk pada peningkatan dalam aktivitas atau penggunaan sumber daya sistem. Dalam konteks menjalankan publisher, lonjakan bisa terjadi ketika publisher mengirimkan event-event besar atau dalam jumlah yang lebih tinggi dari biasanya ke message broker.

4. Simulating slow subscriber
    ![RabbitMq2 Image](/images/rabbitmq2.png)

    Pada kode di subsciber erdapat penggunaan thread dengan fungsi thread::sleep(ten_millis) di dalam metode handle() yang merupakan bagian dari implementasi MessageHandler untuk UserCreatedHandler. Fungsi thread::sleep() digunakan untuk memberikan jeda atau delay selama 1000 milidetik (1 detik) sebelum pesan berhasil diproses dan dicetak ke konsol.

    Ketika kita menjalankan aplikasi dengan kode tersebut, setiap kali listener mendapatkan pesan baru dengan topik "user_created", handler (UserCreatedHandler) akan dipanggil untuk memproses pesan tersebut. Namun, karena menambahkan jeda 1 detik menggunakan thread::sleep(ten_millis), proses pemrosesan pesan akan membutuhkan waktu lebih lama, terutama jika ada banyak pesan yang harus diproses.

5. multipler publisher
    ![RabbitMq3 Image](/images/rabbitmq3.png)

    Yaa terdapat peningkatan queue nya menjadi 2 dimana saya hanya membuka 3 buah cmd dan terminal untuk melakukan "cargo run" pada publisher"






