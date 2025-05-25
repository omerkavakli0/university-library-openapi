# OpenAPI Tasarımı Ödevi Teslim Raporu

## 👤 Öğrenci Bilgileri
- **Ad Soyad**: Ömer Kavaklı
- **Öğrenci Numarası**: 170422034

---

### 🔗 GitHub Repo Linki
https://github.com/omerkavakli0/university-library-openapi

---

## 📝 API Açıklaması

Bu proje, üniversiteye ait çevrim içi bir kütüphane sistemini modelleyen RESTful bir API'yi tanımlar. OpenAPI 3.0.4 standardına uygun olarak hazırlanmıştır.

### 📚 Varlıklar (Entities)
- **Book**: Kütüphane kitaplarını temsil eder.
- **Student**: Sisteme kayıtlı öğrencileri temsil eder.
- **Loan**: Kitap ödünç alma işlemlerini temsil eder.

### 🔄 CRUD İşlemleri ve Endpoint’ler
Her varlık için temel CRUD işlemleri tanımlanmıştır:
- `GET /books`, `GET /books/{id}`, `POST /books`, `PUT /books/{id}`, `DELETE /books/{id}`
- `GET /students`, `GET /students/{id}`, `POST /students`, `PUT /students/{id}`, `DELETE /students/{id}`
- `GET /loans`, `GET /loans/{id}`, `POST /loans`, `PATCH /loans/{id}` (kitap iade işlemi için)

### 🧩 Kullanılan OpenAPI Bölümleri
- `components/schemas`: Book, Student ve Loan için veri modelleri detaylı olarak tanımlanmıştır. Örnek değerler ve `format`, `enum`, `pattern` gibi validasyon kuralları eklenmiştir.
- `parameters`: `page` ve `size` gibi query parametreleri ile `id` gibi path parametreleri kullanılmıştır.
- `responses`: Her endpoint için `200`, `201`, `400`, `404`, `500` yanıtları örneklerle belirtilmiştir.

### 📖 Sayfalama ve Hatalar
- Kitap listesini getirirken (`GET /books`), `page` ve `size` query parametreleriyle sayfalama yapılmaktadır.
- Geçersiz veri, hatalı ID veya sunucu hatası durumları için açıklayıcı yanıtlar dönen `400`, `404`, `500` response tanımları yer almaktadır.

---

## 🧪 Test Notları (Opsiyonel)

Swagger Editor'da yapılan testlerde aşağıdaki gözlemler yapılmıştır:

- ✅ `GET /books` çağrısında kitap listesi döner, örnek veri:  
  ```json
  [
    {
      "id": "b1e2d3f4-5678-1234-9abc-1234567890ab",
      "title": "Dune",
      "author": "Frank Herbert",
      "isbn": "978-3-16-148410-0",
      "publisher": "İthaki Yayınları",
      "pageCount": 712,
      "stock": 3
    }
  ]
  ```

- ✅ `POST /students` için örnek request body:  
  ```json
  {
    "id": "a1b2c3d4-5678-1234-9abc-1234567890ab",
    "name": "Omer Kavakli",
    "studentNumber": "123456789",
    "email": "omerkavakli@example.edu",
    "isActive": true
  }
  ```

- ⚠️ Hatalı `POST /books` isteğinde (örneğin boş `title` alanı):  
  `400 Bad Request` yanıtı alınır ve "Invalid data" açıklaması döner.

---

## 📌 Ek Açıklamalar

- Projede global `security` tanımı kullanılmıştır. Tüm endpoint'lerde `X-API-Key` header’ı zorunlu tutulmuştur.
- Her şema içinde örnek veriler (`example`) tanımlanmış, `enum`, `nullable`, `pattern` gibi gelişmiş özellikler kullanılmıştır.
- Dosya yapısı ve sıralaması OpenAPI standartlarına uygun olarak düzenlenmiştir.