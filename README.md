# Projekt RobotStudio: Mechanizm chwytaka i inteligentna obsługa stanowiska (ABB IRB 120)

Projekt symulacji zrobotyzowanego stanowiska realizowany w dwuosobowym zespole. Głównym celem było zaprojektowanie własnego mechanizmu chwytaka, implementacja logiki czujników oraz stworzenie inteligentnego algorytmu transportu detali z wykorzystaniem układów WorkObject.

## 🎥 Prezentacja działania

[▶ Zobacz nagranie z działania stacji na YouTube](https://youtu.be/47xB4UELqgc)

## 🛠 Technologie i narzędzia

* **Oprogramowanie:** ABB RobotStudio
* **Robot:** ABB IRB 120 (6 stopni swobody)
* **Język programowania:** RAPID
* **Komponenty:** Smart Components, Czujniki (LineSensor / PlaneSensor)

## 🎯 Zrealizowane założenia techniczne

W ramach projektu zaimplementowano następujące rozwiązania:

* **Autorski Mechanizm Chwytaka:** Zaprojektowano i zbudowano od podstaw własny chwytak. Mechanizm został w całości złożony w RobotStudio z nadaniem odpowiednich więzów kinematycznych i parametrów ruchliwości, co pozwala na dynamiczne chwytanie obiektów.
* **Logika Sensorowa:** Stacja wykorzystuje sensory do wykrywania obecności detalu. Dzięki temu robot pracuje w trybie warunkowym:
    * Sprawdza dostępność obiektu na pierwszym stanowisku (stół 1).
    * W przypadku wykrycia przedmiotu, następuje sekwencja chwytania i przeniesienia na drugie stanowisko.
    * Jeśli stół pierwszy jest pusty, robot wraca do pozycji bazowej (**Home**), a następnie sprawdza stół drugi, skąd może przetransportować obiekt z powrotem.
* **Zarządzanie układami współrzędnych (wobj):** Wszystkie targety zostały zdefiniowane względem ruchomych układów współrzędnych obiektu. Pozwala to na dowolne przesuwanie całych stołów wraz z punktami pracy bez konieczności ponownego programowania ścieżek robota.
* **Kod RAPID i I/O:** Program sterujący został napisany w języku RAPID z wykorzystaniem instrukcji warunkowych oraz obsługi sygnałów wejścia/wyjścia, co zapewnia pełną synchronizację chwytaka z ruchem ramienia.

## 🚀 Jak uruchomić projekt?

Cała stacja została wyeksportowana z zachowaniem wszystkich zależności (Pack & Go).

1. Pobierz z repozytorium plik z rozszerzeniem `.rspag`.
2. Uruchom oprogramowanie **ABB RobotStudio**.
3. Z menu głównego wybierz **File** -> **Share** -> **Unpack & Work** (Rozpakuj i pracuj).
4. Wskaż pobrany plik `.rspag` i wybierz folder docelowy.
5. Po załadowaniu stacji, uruchom wirtualny kontroler, przejdź do zakładki **Simulation** i kliknij **Play**.
