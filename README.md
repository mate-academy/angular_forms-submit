# Moonbase Control: Zapisywanie danych formularza

Zadanie z modułu Angular. Repozytorium zawiera kod startowy aplikacji Moonbase Control dla tej lekcji.

## Zadanie

Rozbuduj formularz zgłaszania incydentu tak, aby poprawnie wprowadzone dane mogły zostać zapisane w backendzie.

#### 1. Przygotuj formularz do wysłania
W pliku `report-incident.html`:

- połącz element `<form>` z `incidentForm` za pomocą `[formRoot]`,
- dodaj przycisk Angular Material typu `submit`,
- użyj etykiety `Report incident`.

#### 2. Dodaj obsługę wysłania formularza
W pliku `report-incident.ts`:

- rozszerz konfigurację `form()` o `submission`,
- wewnątrz `submission` zdefiniuj `action`,
- pobierz aktualną wartość formularza za pomocą `field().value()`,
- na podstawie danych formularza utwórz obiekt zgodny z interfejsem `Incident`,
- pamiętaj o poprawnym typie `severity`.

#### 3. Dodaj zapis incydentu
W pliku `incidents.service.ts`:

- wstrzyknij `HttpClient`,
- utwórz metodę `createIncident()`,
- jako argument metody przyjmij obiekt `Incident`,
- wykonaj request POST wysyłający dane do endpointu `/incidents`,
- poczekaj na zakończenie requestu.

#### 4. Odśwież dane po zapisie
- Po poprawnym zakończeniu requestu wywołaj `reload()` istniejącego `incidentsState`.
- Dzięki temu `httpResource` powinien ponownie pobrać aktualną listę incydentów.

#### 5. Połącz formularz z serwisem
W komponencie `ReportIncident`:

- pobierz instancję `IncidentsService` za pomocą `inject()`,
- w `submission.action` wywołaj `createIncident()`,
- przekaż do metody przygotowany obiekt `Incident`.

#### 6. Sprawdź działanie
- Wprowadź poprawne dane incydentu.
- Wyślij formularz.
- Sprawdź, czy nowy incydent został zapisany w backendzie.
- Sprawdź, czy dane incydentów w aplikacji zostały odświeżone.
💡 `FormRoot` łączy formularz w template z Signal Form, `submission.action` obsługuje poprawne wysłanie danych, a `IncidentsService` odpowiada za ich zapis w backendzie.

## Jak zacząć

1. Zrób fork tego repozytorium na swoje konto GitHub.
2. Sklonuj swój fork na komputer.
3. Zainstaluj zależności: `npm install`.
4. Uruchom aplikację: `npm start`.
5. Jeśli zadanie korzysta z danych z API, uruchom w drugim terminalu mock API: `npm run api`.

## Jak oddać zadanie

1. Zapisz zmiany w commicie i wypchnij je do swojego forka.
2. Otwórz Pull Request z forka do repozytorium `mate-academy/angular_forms-submit`, do brancha `main`.
3. Platforma uruchomi review Twojego Pull Requesta.
