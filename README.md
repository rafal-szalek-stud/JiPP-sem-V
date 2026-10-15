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


Element	              Technologia	                                           Rola i uzasadnienie
Gra	              micro:bit + MicroPython 	      Obsługa przycisków, czujników, mechaniki gry i obliczanie wyniku. Proste programowanie.
Komunikacja	      ESP32 + UART + Wi-Fi	          micro:bit nie ma natywnego Wi-Fi. ESP32 zapewnia połączenie z Internetem.
Protokół	        HTTPS + REST API (JSON)	        Prosty, powszechnie wspierany sposób przesyłania wyników i pobierania rankingu.
Backend	          Python + FastAPI	              Przyjmuje wyniki, waliduje dane, udostępnia ranking. Lekki framework z automatyczną dokumentacją API. 

Baza danych	      PostgreSQL	 		                Trwałe przechowywanie graczy i wyników. Łatwe sortowanie, filtrowanie i generowanie rankingów.
Frontend	        React + Vite			              Responsywna strona pokazująca ranking i statystyki graczy.
Ranking fizyczn   ESP32 + OLED			              Wyświetlanie TOP 10 wyników pobieranych z API. Większa czytelność niż matryca LED micro:bita.
Hosting 	        VPS + Docker Compose		        Uruchomienie backendu, bazy i frontendu w kontenerach. Tanie i łatwe we wdrożeniu.
