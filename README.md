# Prometheus Stack

Этот репозиторий содержит конфигурацию для развертывания комплексной системы мониторинга на базе Prometheus с использованием Docker Compose. Включает в себя Prometheus, Grafana, Alertmanager и Blackbox Exporter для всестороннего сбора метрик, визуализации данных и оповещения.

## Компоненты

*   **Prometheus**: Система мониторинга и оповещения с базой данных временных рядов.
*   **Grafana**: Платформа для аналитики и интерактивной визуализации данных, использующая Prometheus как источник данных.
*   **Alertmanager**: Обрабатывает оповещения, отправленные Prometheus, дедуплицирует, группирует и маршрутизирует их в нужные места.
*   **Blackbox Exporter**: Позволяет мониторить внешние конечные точки через HTTP, HTTPS, DNS, TCP и ICMP.
*   **Docker Compose**: Инструмент для определения и запуска многоконтейнерных Docker-приложений.

## Структура директории

*   `alertmanager/`: Конфигурационные файлы для Alertmanager.
*   `blackbox/`: Конфигурационные файлы для Blackbox Exporter.
*   `data/`: Директория для хранения данных Prometheus (и других компонентов, если настроено).
*   `grafana/`: Конфигурация и данные для Grafana.
*   `prometheus/`: Конфигурационные файлы для Prometheus (prometheus.yml, alert.rules).
*   `docker-compose.yml`: Основной файл Docker Compose для определения и запуска всех сервисов.

## Установка и запуск

Для развертывания Prometheus Stack выполните следующие шаги:

1.  **Клонируйте этот репозиторий** (если вы еще этого не сделали):
    ```bash
    git clone https://github.com/Meskaline213/Prometheus_stack.git
    cd Prometheus_stack
    ```
2.  **Запустите стек Docker Compose**:
    ```bash
    docker-compose up -d
    ```
    Это запустит все сервисы в фоновом режиме.

## Использование

После запуска стека, вы можете получить доступ к следующим интерфейсам:

*   **Prometheus UI**: `http://<ваш_ip_сервера>:9090`
*   **Grafana UI**: `http://<ваш_ip_сервера>:3000` (логин по умолчанию: `admin`/`admin`, рекомендуется изменить)
*   **Alertmanager UI**: `http://<ваш_ip_сервера>:9093`
*   **Blackbox Exporter**: `http://<ваш_ip_сервера>:9115`

## Конфигурация

Вы можете изменять конфигурационные файлы в соответствующих директориях (`prometheus/`, `alertmanager/`, `grafana/`, `blackbox/`) для настройки мониторинга под ваши нужды. После внесения изменений в конфигурацию Docker Compose или конфигурационные файлы сервисов, перезапустите контейнеры:

```bash
docker-compose down
docker-compose up -d
```
```

Вы можете скопировать этот текст и вставить его в файл `README.md` в директории `/root/Prometheus_Stack` на вашем сервере вручную.
