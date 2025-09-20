# HTTP Server Spec (C++ aşaması)

## Port
8080

## Endpointler
GET /health
  200 OK
  {"status":"ok"}  (Content-Type: application/json)

GET /hello?name=<string>
  200 OK
  text/plain: "Hello, <name>!"
  name parametresi yoksa: "Hello, World!"

## Log Formatı (tek satır)
<timestamp_iso8601> <method> <path> <status> <latency_ms>

## Kabul Kriterleri
- /health 200 ve tam olarak {"status":"ok"}
- /hello hem name ile hem namesiz çalışır
- Log satırı yukarıdaki formatta çıkar
- Sunucu başlarken “listening on :8080” benzeri bilgi log’u var

## Dışı (scope dışı)
- HTTPS, JWT, DB, Docker, otomatik test
