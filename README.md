                   micro:bit – gra
                   ID gracza + wynik

                      ↓ UART (Serial)

             ESP32 – bramka komunikacyjna
                  Wi-Fi + HTTPS/REST

                      ↓Internet

              Backend – Python FastAPI
      API, walidacja wyników, generowanie rankingu
                      ↓

          PostgreSQL – baza danych
       Gracze, wyniki, historia rozgrywek

                      ↓
          Odczyt rankingu przez API
Strona WWW             Urządzenie rankingowe
Ranking online        ESP32 + micro:bit / ekran OLED


| Element | Technologia | Rola i uzasadnienie |
|---|---|---|
| Gra | **BBC micro:bit + MicroPython** | Obsługa przycisków, czujników, mechaniki gry i obliczanie wyniku; proste programowanie. |
| Łączność | **ESP32 + UART + Wi-Fi** | micro:bit nie ma natywnego Wi-Fi; ESP32 umożliwia transmisję danych przez Internet. |
| Protokół | **HTTPS + REST API (JSON)** | Standardowy, prosty sposób przesyłania wyników i pobierania rankingu. |
| Backend | **Python + FastAPI** | Obsługa API, walidacja wyników i udostępnianie rankingu; automatyczna dokumentacja API. |
| Baza danych | **PostgreSQL** | Trwałe przechowywanie graczy i historii rozgrywek; łatwe sortowanie i filtrowanie wyników. |
| Frontend | **React + Vite** | Responsywna strona z rankingiem i statystykami graczy. |
| Ranking fizyczny | **ESP32 + OLED** | Wyświetlanie TOP 10 pobieranego z API; czytelniejszy ekran niż matryca LED micro:bita. |
| Hosting | **VPS + Docker Compose** | Wspólne uruchamianie usług w kontenerach; stosunkowo tanie i proste wdrożenie. |
