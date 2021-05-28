# Kubernetes Component

## **Node**

Simple server bisa berupa _virtual machine_ dan dapat juga berupa _physical machine_ (_bare metal_)

## **Pod**

Pod merupakan komponen terkecil dari kubernetes. Fungsi dari pod adalah sebagai tempat / wadah untuk menjalankan sebuah _container_. Jadi Pod akan membuat sebuah _environment_ yang dapat menjalankan _container_. Biasanya dalam satu **_POD_** menjalankan satu aplikasi. Setiap **_POD_** memiliki _local IP address_ nya sendiri dan setiap **_POD_** dapat saling berkomunikasi menggunakan masing-masing IPnya sendiri. Jika **_POD_** mati dan melakukan _re-creation_, maka **_POD_** akan memiliki IP yang baru dari sebelumnya

## **Service**

Service berupa **static IP address** atau permanen **IP address** yang dapat terhubung ke **_POD_**. **_Service_** dan **_POD_** memiliki lifecycle yang berbeda dan tidak saling bergantung. Jadi ketika **_POD_** melakukan _restart / re-creation_, alamat IP nya tidak akan berubah. **_Service_**

## **Config Map**

**_Config Map_** berfungsi untuk memisahkan konfigurasi-konfigurasi pada sebuah aplikasi. Dengan menggunakan **_config map_**, kita dapat membuat aplikasi tersebut lebih _portable_ karena konfigurasinya lebih mudah untuk dirubah-rubah dan dimanage.

## **Secret**

Mirip dengan **_Config Map_** tetapi **_Secret_** digunakan untuk menyimpan data-data sensitif seperti _salt, token, apikey,_ dan lainnya

## **Volumes**

Berfungsi untuk menyimpan data / file dari dalam _container_ ke _node machine_. Tujuannya agar data lebih presisten karena _default_ nya pada saat POD melakukan _restart_, semua data yang ada didalam _container_ akan ikut terhapus juga.

## **Deployment**

Merupakan sebuah _blue print_ bagi sebuah pod. Ini berfungsi jika sebuah **_POD_** mengalami masalah dan kemudian mati, maka **_POD_** akan membangun ulang dan melakukan restart sesuai dengan kebutuhan yang sudah dideklarasikan pada **_DEPLOYMENT_**. _Scaling Pods_ juga dapat dilakukan melalui _Deployment_.

## **Stateful Set**

Mirip dengan **_DEPLOYMENT_** hanya saja jika deployment hanya menscaling aplikasi yang _stateless_, _Stateful Set_ dapat men-_scale_ aplikasi / pod yang _statefull_
