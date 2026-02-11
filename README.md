# Dokumentacja Systemu Primus 2026

Witaj w centralnym repozytorium dokumentacji projektu **Primus Inter Pares 2026**.
Tutaj znajdziesz szczegółowe opisy architektury, instrukcje wdrożeniowe oraz specyfikacje techniczne.

## 📚 Spis Dokumentacji

### Główna Dokumentacja
- **[Opis Rozwiązania](docs/opis_rozwiazania.md)**
  Kompleksowy opis systemu, zawierający:
  - Architekturę (Hybrid Event-Driven Modular Monolith)
  - Diagramy (Komponentów, ERD)
  - Opis modułów (Backend, Frontend, Mobile, IoT, AI)
  - Model danych
  - Bezpieczeństwo
- **[Dokumentacja API (Swagger)](api/index.html)**
  Interaktywna dokumentacja endpointów i schematów danych.
- **[Raport Wydajności](docs/test_wydajności.md)**
  Wyniki testów obciążeniowych (Standard, AI) na specyfikacji i7-13700KF + RTX 3060 Ti.
- **[Instrukcja Użytkownika](instrukcja_uzytkownika.md)**
  Pełna instrukcja obsługi aplikacji mobilnej i panelu webowego.

### Dokumentacja Modułów
- **[Backend (API + Worker)](docs/backend.md)** — Logika biznesowa, FastAPI, Celery, AI/IoT.
- **[Frontend (Panel Webowy)](docs/frontend.md)** — Panel administracyjny, React + Vite.
- **[Aplikacja Mobilna](docs/mobile.md)** — Aplikacja dla magazynierów, React Native + Expo.
- **[Infrastruktura](docs/infra.md)** — Docker Compose, SSL, instrukcje uruchomienia.
- **[MQTT Listener](docs/mqtt_listener.md)** — Mikroserwis przetwarzający dane z sensorów.
- **[Mock Sensor](docs/mock_sensor.md)** — Symulator urządzeń IoT (Streamlit).
- **[Testy Wydajnościowe (Locust)](docs/testy_wydajnosciowe.md)** — Scenariusze testów obciążeniowych.
- **[Struktura Projektu](docs/struktura_projektu.md)** — Przegląd katalogów i workflow deweloperski.

### Odnośniki do repozytoriów 
- **[Repozytorium Infrastruktury](https://github.com/Primus2026/primus-infra)**: Instrukcje uruchomienia (Docker Compose).
- **[Repozytorium Backend](https://github.com/Primus2026/primus-backend)**: Kod źródłowy API i Workera.
- **[Repozytorium Frontend](https://github.com/Primus2026/primus-web-frontend)**: Panel administracyjny.
- **[Repozytorium Mobile](https://github.com/Primus2026/primus-mobile)**: Aplikacja dla magazynierów.
- **[Repozytorium MQTT Listener](https://github.com/Primus2026/primus-mqtt-listener)**: Mikroserwis przetwarzający dane z sensorów.
- **[Repozytorium Mock Sensor](https://github.com/Primus2026/primus-mock-sensor)**: Symulator urządzeń IoT.
- **[Docker Hub (Obrazy)](https://hub.docker.com/u/flyinbutter)**: Gotowe obrazy kontenerów.


### 📄 Wersje PDF
Wszystkie dokumenty są również dostępne w formacie PDF w katalogu **[pdf/](pdf/)**.

---

> *Dokumentacja jest utrzymywana w formacie Markdown i hostowana na GitHub.*
