# TOMDOM Mail

Panel PWA firmy TOMDOM. Aktualna wersja jest interfejsem przygotowawczym i **nie ma jeszcze bezpośredniego połączenia z Gmail API**.

## Stan
- PWA działa na GitHub Pages.
- Można przygotować treść wiadomości i skopiować ją.
- Gmail otwiera się przez oficjalną stronę.
- Bezpośrednie odczytywanie skrzynki i wysyłanie przez Gmail nie są jeszcze aktywne.

## Plan integracji Gmail
1. Utworzyć projekt Google Cloud i włączyć Gmail API.
2. Skonfigurować ekran zgody OAuth oraz klienta OAuth dla aplikacji.
3. Uruchomić backend HTTPS, który obsłuży OAuth, odświeżanie tokenów i wywołania Gmail API.
4. Przechowywać tokeny wyłącznie po stronie serwera w bezpiecznym magazynie sekretów.
5. Dodać do PWA logowanie Google, listę wiadomości, podgląd załączników i tworzenie szkiców.
6. Dodać wysyłkę z kontrolą odbiorcy, tematu i treści przed zatwierdzeniem.

## Wymagania bezpieczeństwa
- Nigdy nie umieszczać client secret, access token ani refresh token w plikach PWA, JavaScript, repozytorium ani GitHub Pages.
- Nie prosić użytkownika o hasło Google ani kod 2FA.
- Używać minimalnych zakresów Gmail API niezbędnych do działania.
- Wysyłka wiadomości wymaga świadomego zatwierdzenia przez użytkownika.
- Backend musi weryfikować sesję i chronić endpointy przed nieuprawnionym dostępem.

## Ważne
Sama publikacja PWA na GitHub Pages nie daje jej dostępu do prywatnej skrzynki Gmail. Bez skonfigurowanego backendu i autoryzacji Google aplikacja nie może czytać ani wysyłać wiadomości przez Gmail API.
