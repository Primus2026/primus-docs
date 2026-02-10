# Primus Mock Sensor

Symulator czujników IoT dla systemu **Primus Inter Pares 2026**.
Aplikacja webowa (Streamlit) umożliwiająca testowanie alertów i wizualizacji bez fizycznego sprzętu.

**Pełna dokumentacja projektu:** [Primus Docs](../README.md)


## Architektura

Interaktywna aplikacja webowa symulująca czujniki temperatury i wagi dla każdego slotu w magazynie.

```
Streamlit UI  ──MQTT──►  Mosquitto  ──MQTT──►  MQTT Listener
    │                     Broker
    │
    ▼
Backend API (pobiera definicje regałów)
```


## Funkcjonalności

| Funkcja | Opis |
|---------|------|
| **Symulacja Temperatury** | Slider do ustawiania temperatury per regał lub per slot |
| **Symulacja Wagi** | Input do ustawiania wagi każdego slotu (kg) |
| **Wizualizacja Siatki** | Renderowanie regału jako siatki MxN z aktualnymi wartościami |
| **MQTT Publishing** | Automatyczne wysyłanie odczytów do topiku `sensors/{rack_id}` |
| **Testy Alertów** | Możliwość symulowania anomalii (przekroczenie temperatury, nagła zmiana wagi) |


## Realizacja Wymagań Specyfikacji

### 5. Monitorowanie Środowiska

*   **Implementacja:** [`app.py`](https://github.com/Primus2026/primus-mock-sensor/blob/main/app.py)
*   **Symulacja:**
    *   **Przekroczenie temperatury**: Ustaw temperaturę slotu powyżej `temp_max` regału → MQTT Listener wygeneruje alert `TEMP`.
    *   **Nieautoryzowane pobranie**: Zmniejsz wagę slotu bez aktywnej transakcji → MQTT Listener wygeneruje alert `WEIGHT`.


## Stos Technologiczny

| Kategoria | Technologia |
|-----------|-------------|
| **Framework** | Streamlit |
| **MQTT** | Paho MQTT Client |
| **HTTP** | Requests (do backendu) |
| **TLS** | Obsługa certyfikatów dla MQTT i API |


## Uruchomienie

### Docker (Zalecane)
Serwis uruchamiany automatycznie jako część stosu [primus-infra](https://github.com/Primus2026/primus-infra):
```bash
cd ../primus-infra
docker compose up -d mock-sensor
```
Panel dostępny pod: `http://localhost:8501`

### Lokalnie

Wymagane zmienne środowiskowe:
```bash
export MQTT_BROKER=localhost
export MQTT_PORT=1883
export BACKEND_URL=http://localhost:8000/api/v1
streamlit run app.py
```
