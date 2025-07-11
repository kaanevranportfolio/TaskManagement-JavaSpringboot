# Task Management API

Bu proje, modern bir görev yönetim sistemi için RESTful API sağlayan bir Spring Boot uygulamasıdır. MongoDB veritabanı kullanılarak geliştirilmiş ve Docker konteynerleştirilmiştir.

## Özellikler

- RESTful API endpoints
- MongoDB veritabanı entegrasyonu
- Docker ve Docker Compose desteği
- Kapsamlı birim testler
- Swagger API dokümantasyonu

## Teknolojiler

- Java 11
- Spring Boot 2.7.0
- MongoDB
- Docker & Docker Compose
- Maven
- JUnit 5
- Mockito
- Swagger/OpenAPI

## Proje Yapısı

```
src/
├── main/
│   ├── java/
│   │   └── com/example/taskmanagement/
│   │       ├── controller/
│   │       ├── model/
│   │       ├── repository/
│   │       └── service/
│   └── resources/
│       └── application.properties
├── test/
│   └── java/
│       └── com/example/taskmanagement/
│           ├── controller/
│           └── service/
```

## API Endpoints

- `GET /api/tasks` - Tüm görevleri listele
- `GET /api/tasks/{id}` - Belirli bir görevi getir
- `POST /api/tasks` - Yeni görev oluştur
- `PUT /api/tasks/{id}` - Görevi güncelle
- `DELETE /api/tasks/{id}` - Görevi sil

## Kurulum

### Gereksinimler

- Docker ve Docker Compose
- Java 11 (yerel geliştirme için)
- Maven (yerel geliştirme için)

### Docker ile Çalıştırma

1. Projeyi klonlayın:
```bash
git clone https://github.com/yourusername/task-management-api.git
cd task-management-api
```

2. Docker Compose ile başlatın:
```bash
docker-compose up
```

Uygulama http://localhost:8080 adresinde çalışmaya başlayacaktır.

### Yerel Geliştirme

1. MongoDB'yi başlatın:
```bash
docker-compose up mongodb
```

2. Uygulamayı derleyin ve çalıştırın:
```bash
mvn clean install
mvn spring-boot:run
```

## Testler

Proje kapsamlı test suite'i içerir:

### Test Kapsamı

- **TaskServiceTest (5 test):**
  - Görev oluşturma
  - Görev güncelleme
  - Görev silme
  - Tüm görevleri listeleme
  - Görev detayı getirme

- **TaskControllerTest (8 test):**
  - API endpoint testleri
  - Request/Response doğrulamaları
  - Hata durumu kontrolleri

### Testleri Çalıştırma

Docker ile testleri çalıştırmak için:
```bash
docker-compose up test
```

Yerel ortamda testleri çalıştırmak için:
```bash
mvn test
```

### Test Sonuçları

![Test Sonuçları](pngs/tests.png)

Tüm testler (13 test) başarıyla geçmiştir:
- TaskServiceTest: 5 test
- TaskControllerTest: 8 test

## API Dokümantasyonu

Swagger UI'a http://localhost:8080/swagger-ui.html adresinden erişebilirsiniz.

## Lisans

Bu proje MIT lisansı altında lisanslanmıştır. Detaylar için [LICENSE](LICENSE) dosyasına bakınız.
- Docker
- JUnit & Mockito
- Lombok

## Özellikler

- Görev oluşturma, güncelleme, silme ve listeleme
- Görevleri duruma ve atanan kişiye göre filtreleme
- OpenAPI/Swagger dokümantasyonu
- Unit testler
- Docker desteği
- MongoDB veritabanı entegrasyonu

## Başlangıç

### Gereksinimler

- Java 11 veya üzeri
- Maven
- MongoDB
- Docker (opsiyonel)

### Kurulum

1. Projeyi klonlayın:
```bash
git clone [repository-url]
```

2. Projeyi derleyin:
```bash
mvn clean install
```

3. Uygulamayı çalıştırın:
```bash
mvn spring-boot:run
```

### Docker ile Çalıştırma

```bash
docker-compose up
```

## API Dokümantasyonu

API dokümantasyonuna aşağıdaki URL'den erişebilirsiniz:
```
http://localhost:8080/swagger-ui.html
```

## Test

Unit testleri çalıştırmak için:
```bash
mvn test
```

## API Endpoints

- GET /api/tasks - Tüm görevleri listele
- GET /api/tasks/{id} - ID'ye göre görev getir
- POST /api/tasks - Yeni görev oluştur
- PUT /api/tasks/{id} - Görevi güncelle
- DELETE /api/tasks/{id} - Görevi sil
- GET /api/tasks/assignee/{assignee} - Atanan kişiye göre görevleri listele
- GET /api/tasks/status/{status} - Duruma göre görevleri listele
