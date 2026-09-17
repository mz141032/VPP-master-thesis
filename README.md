# Virtual Power Plant (VPP) — model do pracy magisterskiej

Repozytorium zawiera kod źródłowy wykorzystany w pracy magisterskiej dotyczącej koncepcji wirtualnej elektrowni (Virtual Power Plant, VPP), prognozowania oraz optymalizacji kosztów bilansowania portfela źródeł wytwórczych i odbiorców energii.

## Zakres modelu

Model obejmuje:

- przygotowanie profilu odbiorcy energii elektrycznej,
- prognozowanie zapotrzebowania na ciepło,
- trening i wykonanie prognozy ceny SPOT,
- prognozę generacji OZE,
- optymalizację planu D-1,
- symulację scenariusza wykonania,
- redispatch ex-post,
- redispatch w formule rolling horizon,
- rozliczenie ekonomiczne portfela i PnL.

Główny notebook opisuje pełne „serce” modelu VPP, łącznie z optymalizacją MILP, rolling horizon i analizą ekonomiczną.

## Struktura repozytorium

```text
.
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── 01_electricity_demand.ipynb
│   ├── 02_heat_demand_forecast.ipynb
│   ├── 03_spot_price_training.ipynb
│   ├── 04_spot_day_ahead.ipynb
│   └── 05_vpp_main_model.ipynb
├── models/
│   ├── README.md
│   ├── heat_demand_forecast.pkl
│   └── spot_price_forecast_model.pkl
└── data/
    └── README.md
```

## Kolejność notebooków

1. `01_electricity_demand.ipynb` — przygotowanie profilu odbiorcy z danych UCI.
2. `02_heat_demand_forecast.ipynb` — przygotowanie danych cieplnych i modelu prognozy ciepła.
3. `03_spot_price_training.ipynb` — przygotowanie cech, porównanie modeli i trening modelu ceny SPOT.
4. `04_spot_day_ahead.ipynb` — wykonanie prognozy D+1 z wytrenowanego modelu SPOT.
5. `05_vpp_main_model.ipynb` — główny model VPP: D-1, wykonanie, redispatch i PnL.

## Instalacja

Przykładowe środowisko:

```bash
python -m venv .venv
```

Aktywacja środowiska i instalacja zależności:

```bash
pip install -r requirements.txt
```

## Dane

Surowe dane wejściowe nie są publikowane w repozytorium. Dotyczy to w szczególności danych rynku SPOT TGE, które nie są redystrybuowane wraz z kodem.

Pełny wykaz wymaganych plików i ich roli znajduje się w [`data/README.md`](data/README.md).

## Modele zapisane

W katalogu `models/` znajdują się modele zapisane w formacie `joblib/pickle`:

- model prognozy ceny SPOT,
- model prognozy zapotrzebowania na ciepło.

Dane treningowe nie są częścią repozytorium.

## Uwagi dotyczące uruchamiania

Notebooki powstały w środowisku badawczym używanym przy przygotowaniu pracy i część ścieżek do plików wejściowych pozostaje zgodna z oryginalnym kodem. Przed uruchomieniem należy:

1. pozyskać dane opisane w `data/README.md`,
2. umieścić je w katalogu roboczym lub dostosować ścieżki w odpowiednich komórkach,
3. w razie potrzeby wskazać pliki modeli z katalogu `models/`,
4. uruchamiać notebooki w kolejności wynikającej z celu analizy.

## Odtworzenie wyników pracy

Analiza w pracy została przeprowadzona dla modelu VPP obejmującego m.in. instalacje OZE, kogenerację gazową, kocioł elektrodowy oraz magazyn energii. Główny notebook zawiera zarówno wariant bez działań korygujących, jak i warianty rolling horizon oraz ex-post.

Ze względu na brak redystrybucji części danych wejściowych pełne odtworzenie wyników wymaga samodzielnego pozyskania właściwych danych rynkowych.

## Autor

Miłosz Żabik  
Praca magisterska, Szkoła Główna Handlowa w Warszawie
