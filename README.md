Ini adalah template login page MikroTik khusus yang terintegrasi dengan NiceRadius https://niceradius.ccom
Fitur yang tersedia saat ini :
- Auto Close Session

Fitur ini dugunakan untuk mengatasi masalah random MAC address yang sering menyebabkan kegagalan login dikarenakan MAC Address perangkat pelanggan anda telah berubah setelah terhubung ke SSID yang berbeda.

- Payment Gateway Duitku

Penjualan voucher WiFi dengan metode pembayaran QRIS, OVO, DANA, LinkAja, ShopeePay dan Bank Transfer

Sebelum menggunakannya, Anda harus mendaftar terlebih dahulu untuk mendapatkan API_KEY dan RouterID anda : https://niceradius.com/auth/signup

Setelah itu, Edit file config.js, Rubah variable berikut (Sesuaikan dengan API_KEY dan RouterID yang anda miliki dari NiceRadius)

```
const apiUrl 		= 'https://niceradius.com/api';
const apiKey 		= 'API_KEY_ANDA';
const routerID		= 'ROUTER_ID';
```

Sebelum anda menggunggah file ke MikroTik anda, Pastikan anda telah menambahkan rules walled-garden-ip berikut ke MikroTik anda.

Copy script berikut ke terminal MikroTik anda :
```
/ip hotspot walled-garden ip 
add action=accept disabled=no dst-host=niceradius.com
add action=accept disabled=no dst-host=duitku.com
```
Setelah itu, Sesuaikan HTML Directory pada server profile hotspot anda.
