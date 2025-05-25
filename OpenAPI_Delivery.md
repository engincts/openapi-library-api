# OpenAPI Tasarımı Ödevi Teslim Raporu

## 👤 Öğrenci Bilgileri
- **Ad Soyad**: Engin Çetintaş
- **Öğrenci Numarası**: 170422026

---

## 📂 OpenAPI YAML Dosyası

- **openapi.yaml** dosyasını projenizin GitHub reposuna yükleyiniz.
- Swagger Editor ile test ettiğinizden emin olunuz.

### 🔗 GitHub Repo Linki
https://github.com/engincts/openapi-library-api

---

## 📝 API Açıklaması

Bu API, üniversiteye ait bir çevrim içi kütüphane sistemini temsil eder. Üç ana varlık vardır:

- **books**: Kitap ekleme, listeleme, silme, güncelleme (CRUD)
- **students**: Öğrenci yönetimi (CRUD)
- **loans**: Kitap ödünç alma ve iade işlemleri (POST + PATCH)

### Kullanılan Yapılar:
- `components/schemas`: Book, Student, Loan şemaları tanımlanmıştır.
- `parameters`: Path (`id`), Query (`page`, `size`) parametreleri bileşen olarak tanımlanıp referansla kullanılmıştır.
- `responses`: `400`, `404`, `500` gibi ortak yanıtlar bileşenlerde tanımlanmıştır.
- `example`: POST örnekleri, requestBody altında verilmiştir.
- `pagination`: `GET /books` endpoint’inde `page` ve `size` parametreleriyle sağlanmıştır.

---

## 🧪 Test Notları (Opsiyonel)

- `GET /books` çağrısında kitap listesi JSON array olarak dönmektedir.
- `POST /students` için örnek:
```json
{
  "id": "uuid",
  "name": "Ali Veli",
  "studentNumber": "20231234",
  "email": "ali.veli@example.com",
  "isActive": true
}
```
- `400` hatası örneği (örneğin eksik alanla yapılan isteklerde):
```json
{
  "message": "İstek verisi geçersiz"
}
```

---

## 📌 Ek Açıklamalar

- API Swagger Editor (https://editor.swagger.io) ortamında hatasız olarak test edilmiştir.
- OpenAPI 3.0.3 standardına tamamen uygundur.
- `UUID`, `email`, `date`, `enum` gibi `format` ve `type` tanımlamaları doğru şekilde yapılmıştır.
