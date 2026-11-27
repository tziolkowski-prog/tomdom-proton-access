# TOMDOM Mail

PWA firmy TOMDOM z bezpośrednią integracją Gmail API przez Google Identity Services.

## Funkcje
- Logowanie Google przez OAuth.
- Odczyt 20 najnowszych wiadomości ze skrzynki odbiorczej.
- Wyświetlanie nadawcy, tematu, daty i fragmentu wiadomości.
- Wysyłanie wiadomości przez Gmail API z dodatkowym potwierdzeniem odbiorcy i treści.

## Konfiguracja Google Cloud wymagana przed pierwszym połączeniem
1. Otwórz Google Cloud Console i utwórz lub wybierz projekt.
2. Włącz **Gmail API**.
3. Skonfiguruj Google Auth Platform / ekran zgody OAuth. Dodaj konto Google jako użytkownika testowego, jeśli aplikacja jest w trybie testowym.
4. Utwórz OAuth Client ID typu **Web application**.
5. W polu Authorized JavaScript origins dodaj dokładny origin aplikacji GitHub Pages, np. `https://tziolkowski-prog.github.io`.
6. Wklej Client ID w aplikacji TOMDOM Mail.

## Uprawnienia
Aplikacja prosi o `gmail.readonly` oraz `gmail.send`. Nie żąda dostępu do usuwania ani modyfikowania wiadomości.

## Bezpieczeństwo i ograniczenia
- Nie ma hasła Google ani client secret w repozytorium.
- Token dostępu pozostaje w pamięci bieżącej karty i nie jest zapisywany w localStorage ani wysyłany na własny serwer.
- Po wygaśnięciu tokenu użytkownik musi ponownie autoryzować połączenie.
- Wysyłka wymaga zaznaczenia potwierdzenia i dodatkowego okna potwierdzającego.
- GitHub Pages jest statycznym hostingiem. Ta implementacja używa publicznego klienta OAuth i tokenów krótkotrwałych w przeglądarce; nie przechowuje refresh tokenów.

## Publikacja
GitHub Actions publikuje zawartość repozytorium na GitHub Pages. Po zmianach odśwież aplikację; jeśli stara wersja jest buforowana, zamknij ją całkowicie i uruchom ponownie.
