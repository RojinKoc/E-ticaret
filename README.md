# Multi-Threaded Client-Server E-Ticaret Sistemi

Bu proje, C programlama dili kullanılarak geliştirilmiş, **TCP/IP Socket** mimarisine dayalı bir E-Ticaret simülasyonudur. Sistem, çoklu istemci (multi-client) desteği sunar; yani birden fazla kullanıcı aynı anda sunucuya bağlanıp alışveriş yapabilir.

## 🚀 Proje Hakkında

Uygulama, merkezi bir sunucu (Server) ve bu sunucuya bağlanan istemcilerden (Client) oluşur. Sunucu, ürün stoklarını, fiyatlarını ve sepet işlemlerini yönetir. Veriler anlık olarak işlenir (In-memory storage).

### 🎯 Temel Özellikler

* **Socket Programlama:** `Winsock2` kütüphanesi ile TCP/IP haberleşmesi.
* **Multi-Threading (Çoklu İşlem):** `CreateThread` API'si sayesinde sunucu, her bağlanan müşteri için ayrı bir thread (iş parçacığı) oluşturur. Bu sayede donma olmadan birden fazla kişi aynı anda işlem yapabilir.
* **Stok Yönetimi:** Ürünler için Beden (S, M, L) bazlı stok takibi. Satın alma işleminde stoklar otomatik düşer.
* **Dinamik Sepet Yönetimi:** Sepete ürün ekleme, çıkarma ve sepeti temizleme.
* **Algoritmik İşlemler:**
    * **Arama:** Kelime bazlı ürün arama.
    * **Filtreleme & Sıralama:** Belirli fiyat aralığındaki ürünleri filtreler ve **Bubble Sort** algoritması kullanarak fiyata göre sıralı listeler.

## 🛠️ Kullanılan Teknolojiler

* **Dil:** C
* **Platform:** Windows (Winsock2 & Windows API)
* **Derleyici:** GCC (MinGW) veya Visual Studio
* **İletişim Protokolü:** TCP (Port: 9090)

## 💻 Kurulum ve Derleme (Windows)

Bu proje Windows kütüphanelerini kullandığı için Windows ortamında derlenmelidir.

### 1. Kodu İndirin
Projeyi bilgisayarınıza klonlayın veya indirin.

### 2. Derleme (Compile)
Terminali (CMD veya PowerShell) açın ve proje dizinine gidin.

**Sunucuyu (Server) Derlemek için:**
```bash
gcc server.c -o server -lws2_32
