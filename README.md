## Цель проекта
Цель данного проекта заключается в создании системы мониторинга, DNS-сервера и визуализации данных с использованием Grafana и Prometheus в Docker. Мы будем использовать Docker Compose, который позволяет легко управлять несколькими сервисами, определяя их конфигурацию в одном файле. В этом примере мы создадим Docker Compose файл, который будет развертывать:
- Prometheus  для сбора метрик
- Grafana  для визуализации метрик
- CoreDNS  как DNS-сервер

## Структура проекта
Внутри каталога workspace были созданы следующие файлы:
* docker-compose.yaml — основной файл конфигурации.
* prometheus/prometheus.yml — конфигурационный файл для Prometheus.
* coredns/Corefile — конфигурационный файл для CoreDNS.
* grafana/dashboards — каталог для хранения метаданных дашборда.

## Описание компонентов
Prometheus
**Образ:** используется официальный образ prom/prometheus.
**Порт:** 9090, через который доступен веб-интерфейс.

Grafana
**Образ:** используется официальный образ grafana/grafana.
**Порт:** 3000, через который доступен веб-интерфейс Grafana.
Переменные окружения: задают учетные данные администратора (по умолчанию admin/admin).

CoreDNS
**Образ:** используется официальный образ coredns/coredns.
**Порт:** 53 для обработки DNS-запросов.

Node Exporter
**Образ:** используется образ prom/node-exporter.
**Порт:** 9100, через который доступны метрики.

## Начало работы
Чтобы запустить все сервисы, выполните команду:

`docker-compose up -d`

После этого вы сможете получить доступ к интерфейсу Prometheus по адресу http://localhost:9090 и к интерфейсу Grafana по адресу http://localhost:3000. Для входа в Grafana используйте имя пользователя admin и пароль admin.

## Завершение работы
Чтобы остановить и удалить все запущенные контейнеры, выполните команду:

`docker-compose down`

##Заключение
Создание Docker Compose файла для развертывания системы мониторинга позволяет легко управлять всеми компонентами в одном месте. Это упрощает процесс настройки и запуска сервисов, необходимых для эффективного мониторинга и визуализации данных.
