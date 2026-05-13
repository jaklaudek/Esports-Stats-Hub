```markdown
# Esports-Stats-Hub 🎮

[![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-8.0-blue)](https://dotnet.microsoft.com/)
[![Entity Framework Core](https://img.shields.io/badge/EF%20Core-Relational-green)](https://docs.microsoft.com/ef/core/)

Zaawansowany system backendowy (REST API) oraz panel zarządzania (UI) stworzony w **ASP.NET Core**. Projekt służy do gromadzenia, przetwarzania i analizowania telemetrii oraz statystyk zachowań graczy z meczów e-sportowych.

Aplikacja jest przystosowana do odbierania sformatowanych danych w postaci JSON z zewnętrznych parserów (wykorzystujących np. narzędzia takie jak `demoinfocs-golang`), a następnie bezpiecznego zapisu tych danych w relacyjnej bazie.

## Zrealizowane wymagania projektowe (PDI)

Projekt zostanie zaprojektowany tak, aby zaprezentować kompleksową wiedzę z zakresu tworzenia aplikacji webowych w technologii ASP.NET:

-  **Pełen zestaw operacji REST (CRUD):** Wdrożone metody `GET`, `POST`, `PUT` oraz `DELETE` do zarządzania zasobami (np. meczami, statystykami graczy).
-  **Walidacja danych:** Restrykcyjna walidacja modeli wejściowych (Data Annotations / FluentValidation) zapobiegająca zapisowi niepoprawnych logów.
-  **Dependency Injection (DI):** Pełne wykorzystanie wbudowanego kontenera IoC do wstrzykiwania serwisów, logiki biznesowej i kontekstu bazy danych.
-  **Custom Middleware:** Autorska warstwa w potoku żądań HTTP (np. do globalnej obsługi błędów lub logowania czasu przetwarzania zapytań API).
-  **Baza Danych (Entity Framework Core):** Relacyjna struktura bazy danych obsługiwana przez system ORM z wykorzystaniem migracji (Code-First).
-  **Uwierzytelnianie i Autoryzacja:** Zabezpieczenie modyfikujących endpointów oraz widoków przed nieautoryzowanym dostępem.
-  **Interfejs Użytkownika:** Frontendowa warstwa prezentacji danych stworzona przy użyciu technologii **Razor / Blazor**, pozwalająca na graficzne przeglądanie statystyk.

## 🛠️ Technologie

* **Język:** C# 
* **Framework:** ASP.NET Core Web API / Razor Pages / Blazor
* **ORM:** Entity Framework Core
* **Baza danych:** SQLite (środowisko deweloperskie) / SQL Server (produkcja)
* **Architektura:** N-Tier / Clean Architecture (podział na modele, kontrolery i serwisy)

## 📡 Przykładowe Endpointy API

Aplikacja udostępnia zasoby pod następującymi adresami:

| Metoda | Endpoint | Opis | Autoryzacja |
|--------|----------|------|-------------|
| `GET`  | `/api/matches` | Pobiera listę rozegranych meczów | ❌ |
| `GET`  | `/api/matches/{id}` | Pobiera szczegółowe dane konkretnego meczu | ❌ |
| `POST` | `/api/matches` | Dodaje nowy mecz (przyjmuje JSON z parsera) | 🔒 Wymagana |
| `PUT`  | `/api/matches/{id}` | Aktualizuje dane/notatki o meczu | 🔒 Wymagana |
| `DELETE`| `/api/matches/{id}` | Usuwa uszkodzone lub testowe logi meczowe | 🔒 Wymagana |

## ⚙️ Uruchomienie lokalne

1. Sklonuj repozytorium:
   ```bash
   git clone [https://github.com/TwojNick/Esports-Stats-Hub.git](https://github.com/TwojNick/Esports-Stats-Hub.git)
   

```
 2. Przejdź do katalogu projektu:
   ```bash
   cd Esports-Stats-Hub
   
   
   ```
```
3. Przywróć pakiety NuGet:
   ```bash
   dotnet restore

```
 4. Zaktualizuj bazę danych (uruchomienie migracji EF Core):
   ```bash
   dotnet ef database update
   
   ```
 5. Uruchom aplikację:
   ```bash
   dotnet run
   
   
   ```
```
6. Przejdź pod adres `https://localhost:xxxx` w przeglądarce, aby otworzyć interfejs UI, lub `https://localhost:xxxx/swagger`, aby przetestować API.

```
```

```
