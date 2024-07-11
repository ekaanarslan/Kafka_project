# Kafka_project
1.ADIM İlk olarak docker-compose.yml dosyasını indirin.

2. ADIM Daha sonra terminali açın ve aşağıdaki komutunu girin:

        docker-compose up -d
   
bu komut zookeeper ve kafkayı başlatıcaktır.

komutun çalışması için docker-compose.yml dosyasının bulunduğu dizine doğru olduğunuzdan emin olun. (örnegin masaüstünde ise 
PS C:\Users\emrea> cd OneDrive
PS C:\Users\emrea\OneDrive> cd Desktop ile masaüstü dizisine gidin)

3.ADIM docker ps komutu ile çalışan containerları kontrol edin (3 tane olmalı)

kafka containerının ID'sini kopyalayın (name alanında kafka-1 yazan kısımdaki ID)

4.ADIM Aşağıdaki koddaki YOURID kısmını 3.adımda kopyaladığınız ID ile degiştirin ve kodu çalıştırın.
(Örneğin: docker exec -it 5442874ed9e7 /bin/bash=

	docker exec -it YOURID /bin/bash

  bu işlem ile Bash kabuğunu başlatmış oluyoruz.

5.ADIM Artık bir topic oluşturabiliriz. Aşağıdaki komutu terminalde gözüken I have no name alanına sag tıklayarak yapıştırın.
	
	kafka-topics.sh --create --topic hello-topic --bootstrap-server kafka:9092 --partitions 1 --replication-factor 1

bu komut hello-topic isimli yeni bir topic oluşturacaktır.
 
6.ADIM  Bu topic üzerinden mesaj iletmek için aşağıdaki komutu terminalde gözüken I have no name alanına sag tıklayarak yapıştırın.
	
	kafka-console-producer.sh --topic hello-topic --bootstrap-server kafka:9092
	
bu komut ile beraber artık yolladıgınız mesajlar bir ileti olarak kaydedilicektir. (Çıkmak için ctrl+c tuşlarına basın)

7.ADIM Gönderilen mesajları dinlemek için ise aşağıdaki komutu çalıştırın.

	kafka-console-consumer.sh --topic hello-topic --bootstrap-server kafka:9092 --from-beginning

Son olarak exit komutu ile Bash kabuğundan çıkabilirsiniz.

NOT: Yaptıgımız işlemleri Kafdropda görmek için tarayıcınıza http://localhost:9000 yazabilirsiniz.
