# ValoriApiTests (C# · .NET 8 · Playwright · NUnit)

Dit repository bevat een complete, werkende API test automation projectstructuur voor de
VALORI-opdracht (OpenWeather + TVMaze) opgebouwd met **.NET 8**, **C#**, **Playwright** en **NUnit**.

## Wat zit erin
- ApiClients: OpenWeatherClient, TvMazeClient
- Helpers: ApiHelper (maakt Playwright APIRequestContext)
- Utils: LoggerUtil
- Tests: OpenWeatherTests (opdrachten 1-4 + creatieve test), TvMazeTests (opdracht 5)
- appsettings.json met voorbeeld API key
- README met instructies

## Vereisten
- .NET 8 SDK geïnstalleerd
- Playwright browserbinaries (eenmalig) — zie setup stap

## Setup & Run
1. Clone repo
2. Vanuit de projectfolder:
   ```
   dotnet restore
   ```
3. Voeg Playwright toe en build
```
dotnet add package Microsoft.Playwright
dotnet build
   ```
4. Installeer Playwright browsers
```
dotnet add package Microsoft.Playwright
dotnet build
```

4. Run tests:
   ```bash
   dotnet test
   ```

## Design choices & best practices (samenvatting)
- **Client layer abstraction**: API-calls in `ApiClients/` — tests blijven clean.
- **Async/await** overal voor performantie.
- **Parameterized tests** met `[TestCase]` om duplicatie te voorkomen.
- **FluentAssertions** voor leesbare asserts.
- **appsettings.json** voor configuratie (keys, base urls).

## Bestandsoverzicht
- ApiClients/OpenWeatherClient.cs
- ApiClients/TvMazeClient.cs
- Helpers/ApiHelper.cs
- Tests/OpenWeatherTests.cs
- Tests/TvMazeTests.cs
- appsettings.json
- Utils/LoggerUtil.cs
