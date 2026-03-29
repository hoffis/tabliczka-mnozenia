# Trener Tabliczki Mnożenia 🧠⚡

👉 **[Zagraj teraz w przeglądarce!](TUTAJ_WKLEJ_SWOJ_LINK_Z_GITHUB_PAGES)**

Inteligentna, w pełni przeglądarkowa aplikacja do treningu tabliczki mnożenia. Aplikacja nie tylko losuje zadania, ale aktywnie **uczy się Twoich słabych punktów**, dostosowując częstotliwość trudnych równań i wizualizując postępy za pomocą map ciepła.

Projekt został zoptymalizowany pod kątem urządzeń mobilnych (wymusza klawiaturę numeryczną, dopasowuje interfejs do ekranu) oraz komputerów stacjonarnych (obsługa klawiatury fizycznej).

## ✨ Główne funkcje
* **Multi-User (Profile):** Możliwość stworzenia wielu profili na jednym urządzeniu. Każdy użytkownik ma własne, izolowane statystyki i historię sesji.
* **Algorytm Adaptacyjny:** System nadaje "wagi" poszczególnym działaniom. Błędne odpowiedzi drastycznie zwiększają częstotliwość występowania danego zadania w przyszłości. 
* **Rozpoznawanie Symetrii:** Algorytm rozumie, że a × b = b × a. Błąd w jednym równaniu automatycznie zwiększa priorytet jego lustrzanego odbicia.
* **Mapy Ciepła (Heatmaps):** Wizualne podsumowanie wiedzy z podziałem na:
  * ⚡ **Czas odpowiedzi:** (Zielony = automat, Żółty = zastanowienie, Czerwony = problem)
  * ❌ **Błędy:** (Biały = bezbłędnie, Pomarańczowy = sporadyczne błędy, Czerwony = krytyczne luki)
* **Dostosowanie trudności:** Wybór czasu na odpowiedź (10s, 5s, 3s) oraz długości sesji (2, 4, 10 minut).
* **Tryb Hardcore:** Opcja zablokowania możliwości poprawiania wpisanej odpowiedzi (blokada klawisza Backspace/Delete).
* **Wykrywanie bezczynności:** Automatyczna pauza po pominięciu 3 zadań z rzędu.
* **Pełna Prywatność (Offline-first):** Wszystkie dane, statystyki i historia sesji są zapisywane wyłącznie w pamięci Twojej przeglądarki (`localStorage`). Żadne dane nie są wysyłane na zewnętrzne serwery.

## 📊 Jak działa algorytm wag?
System startuje z wagą bazową `5` dla każdego działania (od 2 × 2 do 9 × 9).
* **Poprawna i szybka odpowiedź:** Waga spada (minimalnie do `1`).
* **Błędna odpowiedź:** Waga rośnie o `+6` (maksymalnie do `20`). Dodatkowo waga lustrzanego odbicia rośnie o `+3`.
* Losowanie kolejnego zadania faworyzuje te z najwyższą wagą, co wymusza częstszy trening trudnych partii materiału. System posiada wbudowaną blokadę, aby to samo zadanie nie wystąpiło dwa razy pod rząd.

## 🛠 Technologie
* **HTML5:** Semantyczna struktura i responsywność (`viewport`, `inputmode`).
* **CSS3:** Zmienne CSS, Flexbox, układ przyjazny dla smartfonów.
* **Vanilla JavaScript (ES6+):** Logika obiektowa (klasa `MultiplicationEngine`), obsługa zdarzeń (`Event Listeners`), manipulacja DOM i zapis danych (`localStorage`).
