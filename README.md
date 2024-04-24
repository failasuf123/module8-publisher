"# module8-publisher" 
### Excercise
1. 
2. 
3. 

### Tutorial
1. Screen Shoot Welcome Screen
    ![Example Image](/images/welcomepage.png)
2. Subcsriber Console
    ![Subscriber1 Image](/images/subscriber1.png)

    ### Proses yang terjadi
    Publisher Mengirim Event:
    - Saat saya menjalankan cargo run pada publisher, proyek tersebut mengirimkan event ke message broker menggunakan protokol AMQP.

    Event Diproses oleh Message Broker:
    - Message broker (misalnya, RabbitMQ) menerima event-event yang dikirimkan oleh publisher.
    - Broker menyimpan event-event ini dan menunggu subscriber yang tertarik untuk mengkonsumsinya.

    Subscriber Mengonsumsi Event:
    - Saat saya menjalankan subscriber akan melakukan koneksi ke message broker menggunakan protokol AMQP.
    -  Subscriber mendaftar untuk mengonsumsi event-event tertentu, dalam hal ini, event dengan topik "user_created".
    - Ketika event-event baru dengan topik "user_created" tersedia di broker, subscriber secara otomatis mengonsumsi dan memproses event tersebut.
    Pengolahan Data oleh Subscriber:

3. Page of RabbitMq when Cargo run
  ![Subscriber1 Image](/images/rabbitmq.png)

  Lonjakan (spike) dalam konteks ini merujuk pada peningkatan dalam aktivitas atau penggunaan sumber daya sistem. Dalam konteks menjalankan publisher, lonjakan bisa terjadi ketika publisher mengirimkan event-event besar atau dalam jumlah yang lebih tinggi dari biasanya ke message broker.






