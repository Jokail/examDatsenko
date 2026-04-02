# Test 23 — EMQX MQTT Broker

Event-Driven архітектура з MQTT-брокером EMQX та двома веб-клієнтами на HTML/JS.

## Запуск

```bash
docker compose up -d
```

## Сервіси

| Сервіс     | Адреса                        |
|------------|-------------------------------|
| MQTT (TCP) | `mqtt://localhost:1883`        |
| WebSocket  | `ws://localhost:8083/mqtt`     |
| Dashboard  | `http://localhost:18083`       |

> Dashboard: логін `admin`, пароль `public`

## Веб-клієнти

Відкрити у браузері:
- `src/web1/index.html`
- `src/web2/index.html`

Обидва клієнти підключаються до EMQX через WebSocket і обмінюються повідомленнями через топік `chat/room`.

## Postman (крос-протокольна взаємодія)

1. New Request → **MQTT**
2. URL: `mqtt://localhost:1883`
3. Subscribe / Publish на топік `chat/room`
4. Повідомлення надіслані через Postman з'являться у браузерних клієнтах і навпаки.
