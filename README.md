# Mattress Marketplace System Design

✅ Высокопроизводительный Highload маркетплейс матрасов с микросервисной архитектурой на Go, развернутый в AWS с использованием Kubernetes с использованием паттернов SAGA Pattern и Temporal Workflow

## Ключевые Показатели
- 80+ производителей, 16,000+ моделей, 8M+ комбинаций размеров
- 10,000+ ежедневных пользователей, 200+ одновременных запросов
- 5,000+ транзакций/мин, 3,000+ запросов к каталогу/мин
- Доступность системы: 99.99%
- Время ответа API: < 200ms

## Архитектурная документация и диаграммы
### [1. Base System Design](/docs/1_base_arch.md) <-- Документация High Level Base System Design
[![Base System Design](/diagrams/1_base_mapping_high_arch.svg)](/diagrams/1_base_mapping_high_arch.svg)
Базовая документация и диаграмма определяет основные процессы между сервисами и инструментами.

### [2. Order Architecture](/docs/2_order_arch.md) <-- Документация High Level Order with SAGA Pattern and Temporal Workflow
[![Order Flow Architecture](/diagrams/2_order_mapping_high_arch.svg)](/diagrams/2_order_mapping_high_arch.svg)
Детализирует процесс обработки заказов, включая платежи, управление инвентарем и доставку. Реализует паттерн SAGA для распределенных транзакций.

### [3. Business Architecture](/docs/3_bussines_arch.md) <-- Документация High Level Business Flow Architecture 
Определяет основные бизнес-процессы, интеграции с внешними системами и потоки данных между сервисами.

### [4. API Architecture](/docs/4_api_arch.md) <-- Документация High Level API Architecture
Описывает слои API, маршрутизацию запросов и взаимодействие между сервисами. Включает API Gateway, Service Mesh и основные микросервисы.

### [5. Deployment Architecture](/docs/5_deploy_arch.md) <-- Документация High Level Deployment Architecture
Описывает инфраструктуру AWS, конфигурацию Kubernetes и стратегии развертывания. Включает мониторинг и масштабирование.



## Технологический Стек

### Микросервисы
- **Catalog Service:** Golang, MongoDB, Redis, Elasticsearch
- **Order Service:** Golang, PostgreSQL, Stripe/PayPal
- **User Service:** Golang, PostgreSQL, Redis, JWT
- **Sync Service:** Golang, AWS S3

### Хранение Данных
- **PostgreSQL:** транзакции, пользователи, базовая информация
- **MongoDB:** характеристики матрасов, медиаконтент
- **Redis:** кэш фильтров, сессии
- **Elasticsearch:** поисковый движок, фильтрация

### Инфраструктура
- **Cloud:** AWS (ECS/EKS/RDS/S3)
- **Containers:** Kubernetes, Docker
- **CI/CD:** GitLab CI, Terraform, Ansible
- **Monitoring:** Prometheus, Grafana, ELK Stack, New Relic
- **Development:** Swagger, Postman, JIRA (SCRUM)
- **Security:** JWT, OAuth 2.0, SSL/TLS, WAF + Shield

## Детальная Документация
Подробное описание каждого компонента системы доступно в директории [docs](/docs).

## Disclaimer

Данный проект является демонстрационным и служит для иллюстрации архитектурных навыков. 

### Для продакшн-версии требуется:

1. Тестирование архитектуры с использованием:
   - Golang
   - Python

2. Реализация дополнительных архитектурных схем:
   - Monitoring Architecture
   - Backup & Recovery Strategy
   - Network Infrastructure Details
   - CI/CD Pipeline Flow
   - Detailed Infrastructure Map
   - Security Architecture
   - и другие компоненты

### Контакты
Если у вас есть вопросы или предложения по улучшению проекта, свяжитесь со мной:
- Telegram: [@sergei_x100](https://t.me/sergei_x100)

