# RedisCache


---

# RedisCache 🚀

[![Java](https://img.shields.io/badge/Java-17%2B-orange?logo=openjdk)](https://www.java.com/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.1.5-brightgreen?logo=springboot)](https://spring.io/projects/spring-boot)
[![Redis](https://img.shields.io/badge/Redis-7.0+-red?logo=redis)](https://redis.io/)
[![Maven](https://img.shields.io/badge/Maven-3.8%2B-blue?logo=apache-maven)](https://maven.apache.org/)

Высокопроизводительный и простой в использовании модуль для кэширования данных в приложениях Spring Boot с использованием Redis. Этот проект служит готовым решением для интеграции распределенного кэширования, значительно ускоряющего работу вашего приложения.

## ✨ Особенности

*   **Простая интеграция**: Легко добавляется в любой Spring Boot проект через Maven.
*   **Гибкая конфигурация**: Настраиваемое время жизни (TTL) для записей в кэше.
*   **Универсальность**: Поддерживает кэширование любых сериализуемых Java-объектов.
*   **Автоматическое управление подключением**: Использует `Lettuce` как высокопроизводительный Redis-клиент.
*   **Чистая архитектура**: Пример реализации через сервисный слой.


### Предварительные требования

*   Java 17 или выше
*   Maven 3.8+
*   Запущенный сервер Redis (локально или удаленно)

### 1. Настройка подключения к Redis

Отредактируйте файл `src/main/resources/application.yml`:

```yaml
spring:
  data:
    redis:
      host: localhost # Адрес вашего Redis-сервера
      port: 6379      # Порт Redis
      password:       # Пароль (если требуется)
cache:
  ttl-in-hours: 1     # Время жизни записей в кэше (в часах)
```

## 📖 API `CacheService`

Основной интерфейс для работы с кэшем:

| Метод | Описание | Пример |
| :--- | :--- | :--- |
| `set(String key, Object value)` | Сохраняет объект в кэш. | `cacheService.set("user_123", user);` |
| `get(String key)` | Извлекает объект из кэша по ключу. | `User user = (User) cacheService.get("user_123");` |
| `delete(String key)` | Удаляет запись из кэша по ключу. | `cacheService.delete("user_123");` |
| `clear()` | **Осторожно!** Полностью очищает весь кэш. | `cacheService.clear();` |

## 🛠 Технологии

*   **Spring Boot 3** - Основной фреймворк
*   **Spring Data Redis** - Интеграция с Redis
*   **Lettuce** - High-performance Redis client
*   **Jackson** - Сериализация/десериализация объектов


⭐ Не забудьте поставить звезду репозиторию, если он был вам полезен!

---
**Примечание:** Не забудьте создать файл `LICENSE` в корне вашего репозитория, если вы хотите использовать лицензию MIT. Вы можете легко сгенерировать его на [choosealicense.com](https://choosealicense.com/).
