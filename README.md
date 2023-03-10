# Hotel Booking Cancellation Machine Learning
### Prepared by Muhammad Naufal Rafi
### Capstone Project Modul 3 Purwadhika

**Latar Belakang:**  
Dewasa ini Seiring berkembangnya teknologi, pada industri hospitality semakin populer pemesanan dilakukan secara online, salah satunya adalah pada industri perhotelan. Online Bookings saat ini sangat memudahkan pengguna dalam memesan sebuah kamar dan juga dengan ini pengguna juga dimudahkan dalam proses pembatalan kamar, hal ini disebabkan karena perilaku pengguna yang melakukan booking secara impulsive yang merupakan dampak negatif dari adanya fitur tersebut. Selain itu adanya biaya pembatalan yang gratis juga yang menyebabkan tingkat pembatalan sering terjadi di industri perhotelan.

Target:  
`0` : Tidak Batal Booking  
`1` : Batal Booking

**Goals:**  
Maka berdasarkan permasalahan tersebut, Perusahaan ingin menganalisa karakteristik seseorang yang melakukan reservasi dengan membuat sebuah model yang mampu memprediksi apakah pelanggan yang telah melakukan reservasi / booking kamar hotel berpotensi untuk melakukan pembatalan booking atau tidak. 

Sehingga pihak hotel dapat mengantisipasi revenue loss pada operasi maupun promosi serta reputasi dari hotel tersebut yang disebabkan dari potensi pembatalan seseorang pelanggan, sehingga pihak hotel akan memfokuskan pada pelanggan yang tidak melakukan pembatalan reservasi.

**Analytical Approach:**  
Jadi pada projek ini akan membangun sebuah model klasifikasi yang mampu membedakan pelanggan yang berpotensi melakukan pembatalan dan tidak dalam reservasi sebuah kamar hotel.

**Metrics Evaluation:**  
- `False Negatives Rate` : Pelanggan yang melakukan pembatalan reservasi hotel namun di prediksi oleh model tidak melakukan pembatalan.  
    - **Konsekuensi:**
        - Pihak hotel telah menyiapkan room dan persediaan yang tidak penting serta pengerahan sumber daya manusia yang sia sia yang akan berujung kepada meningkatnya revenue loss pada pihak perusahaan.
        - Banyaknya kamar dengan status terisi namun kenyataanya kosong, hal ini akan menyebabkan berkurangnya keuntungan pada pihak perusahaan.
        - Berpotensi terjadinya overbooking serta hilangnya peluang dalam menjual kamar hotel kepada pelanggan lainnya.
    - **Solusi:**  
        - Memaksimalkan nilai recall.
- `False Positives Rate` : Pelanggan tidak melakukan pembatalan reservasi hotel namun diprediksi melakukan pembatalan reservasi hotel.
    - **Konsekuensi:**  
        - Tidak adanya persiapan dari pihak hotel dalam mendistribusikan persediaan serta pengerahan sumber daya yang berpotensi terjadinya miss management.
        - Berpotensi hilangnya reputasi baik hotel yang diakibatkan kesalahan hotel karena memberikan kamar hotel kepada pelanggan lain.
    - **Solusi:**  
        - Memaksimalkan nilai precission.

Sehingga dengan demikian sangat penting bagi hotel untuk mengurangi loss revenue serta menjaga reputasi hotel. Jadi pihak perusahaan sangat ingin membuat sebuahmodel yang dapat membedakan kelas positif dan kelas negatif dengan baik, dengan demikian metrics yang akan digunakan adalah `ROC-AUC` dan `Balanced Accuracy`.


**Data Descriptions**

1. `country`: Negara asal pelanggan.
2. `market_segment`: Segmen pasar yang dituju.
3. `previous_cancellations`: Jumlah pemesanan sebelumnya yang dibatalkan oleh pelanggan sebelum pemesanan saat ini.
4. `booking_changes`: Jumlah perubahan/amandemen yang dilakukan pada pemesanan sejak pemesanan dimasukkan ke dalam PMS hingga saat check-in atau pembatalan.
5. `deposit_type`: Indikasi apakah pelanggan melakukan deposit untuk menjamin pemesanan.
6. `days_in_waiting_list`: Jumlah hari pemesanan berada dalam daftar tunggu sebelum dikonfirmasi kepada pelanggan.
7. `customer_type`: Tipe pemesanan.
8. `reserved_room_type`: Kode jenis kamar yang dipesan. Kode ditampilkan sebagai pengganti nama untuk alasan anonimitas.
9. `required_car_parking_space`: Jumlah tempat parkir mobil yang diperlukan oleh pelanggan.
10. `total_of_special_request`: Jumlah permintaan khusus yang dibuat oleh pelanggan (misalnya tempat tidur twin atau lantai atas).
11. `is_canceled`: Nilai yang menunjukkan apakah pemesanan dibatalkan (1) atau tidak (0).
