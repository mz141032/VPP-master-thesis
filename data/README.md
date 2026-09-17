# Dane wejściowe

Dane wejściowe nie są publikowane w tym repozytorium. Część z nich pochodzi ze źródeł zewnętrznych, a dane rynku SPOT TGE podlegają warunkom licencyjnym i nie są przeznaczone do redystrybucji w tym repozytorium.

## Pliki oczekiwane przez notebooki

| Plik | Zastosowanie | Źródło / sposób pozyskania | Publikowany w repo? |
|---|---|---|---|
| `LD2011_2014.txt` | przygotowanie profilu odbiorcy energii elektrycznej | UCI Machine Learning Repository, ElectricityLoadDiagrams20112014 | Nie; pobrać ze źródła |
| `helen_2015_2024_v2.csv` | historyczny profil zapotrzebowania na ciepło | Helen Open Data | Nie; pobrać ze źródła / przygotować zgodnie z notebookiem |
| `raw_data (1) forecast SPOT.xlsx` | trening modelu cen SPOT | dane przygotowane na podstawie źródeł opisanych w pracy, w tym danych rynkowych | Nie |
| `SPOT_2026.xlsx` | wykonanie prognozy D+1 / walidacja | dane rynku SPOT | Nie |
| `Dane rynkowe.xlsx` | dane wejściowe głównego modelu VPP | dane rynkowe użyte w analizie | Nie |
| `prognoza_cen_niezbilansowania.xlsx` | prognoza CEN | dane PSE / dane przygotowane do modelu | Nie |
| `sciezki_RDB.xlsx` | ścieżki cen RDB | dane przygotowane do scenariusza | Nie |
| `Ceny i niezbilansowanie na RB.xlsx` | rozliczenie CEN i niezbilansowania | dane rynku bilansującego / PSE | Nie |

## Pliki generowane pośrednio

Notebooki przygotowujące dane tworzą m.in.:

- `industrial_load_schedule_2026_15min.csv`,
- `helsinki_heat_scaled_15min.csv`,
- `helsinki_heat_weather_scaled_15min.csv`,
- pliki wynikowe prognoz i optymalizacji.

Nie są one wersjonowane w repozytorium, ponieważ można je odtworzyć z kodu po dostarczeniu właściwych danych źródłowych.

## Dane TGE

Historyczne dane cenowe TGE wykorzystane w pracy nie są udostępniane w tym repozytorium. Osoba chcąca odtworzyć analizę powinna pozyskać wymagane dane bezpośrednio od właściwego dostawcy na podstawie własnych uprawnień/licencji, a następnie przygotować pliki o strukturze zgodnej z notebookami.
