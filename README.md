# MN – Projekt semestralny  
## Detekcja obiektów (samochody) z użyciem PyTorch i TorchVision

---

## 1. Cel projektu
Celem projektu było opracowanie systemu detekcji obiektów klasy **samochód**, obejmującego pełny pipeline przetwarzania danych, w tym:
- przygotowanie i etykietowanie zbioru danych,
- wykorzystanie gotowych modeli detekcji obiektów,
- porównanie wybranych architektur sieci neuronowych,
- samodzielny trening (fine-tuning) wybranego modelu,
- detekcję obiektów na obrazach.

Projekt został zrealizowany w środowisku **Google Colab** z wykorzystaniem biblioteki **PyTorch**.

---

## 2. Zbiór danych
Zbiór danych został przygotowany na potrzeby projektu i oznaczony ręcznie.

- **Liczba obrazów:** 409  
- **Klasa obiektów:** samochód  
- **Format etykiet:** YOLO  
- **Narzędzie do etykietowania:** LabelImg  

**Link do pobrania zbioru danych:**  
https://drive.google.com/drive/folders/1HxEg1A0xsfKOndxwit2XS6_EJVIDBNXg  

**Link do pobrania modeli detekcji obiektów:**  
https://drive.google.com/drive/folders/1gi0l8FnIhQ4CCizn9NyVLnzD9YjyTCwg  

**Struktura zbioru danych:**

<img width="103" height="247" alt="image" src="https://github.com/user-attachments/assets/33b46f77-22ef-427e-9dc7-34ca549a2f61" />

Do treningu wykorzystano wyłącznie obrazy zawierające co najmniej jeden obiekt. Jest to wymagane przez modele detekcji obiektów dostępne w bibliotece TorchVision, które oczekują obecności ramek ograniczających w danych uczących.

---

## 3. Wykorzystane technologie i biblioteki
W projekcie wykorzystano następujące technologie i biblioteki:
- Python 3  
- PyTorch  
- TorchVision  
- PIL (Python Imaging Library)  
- NumPy  
- Google Colab  

---

## 4. Modele detekcji obiektów – porównanie
W części porównawczej zastosowano wstępnie wytrenowane modele detekcji obiektów dostępne w bibliotece TorchVision:
- Faster R-CNN ResNet50 FPN  
- Faster R-CNN MobileNetV3 Large FPN  
- RetinaNet ResNet50 FPN  
- SSD300 VGG16  
- FCOS ResNet50 FPN  

Modele zostały przetestowane na tych samych danych wejściowych i porównane wizualnie pod kątem liczby wykrytych obiektów, stabilności detekcji oraz jakości ramek ograniczających.

---

## 5. Samodzielny trening modelu
W ramach projektu przeprowadzono fine-tuning modelu detekcji obiektów:
- **Faster R-CNN MobileNetV3 Large FPN**

Proces treningu obejmował:
- wykorzystanie własnego zbioru danych z etykietami w formacie YOLO,
- mapowanie wszystkich obiektów do jednej klasy,
- trening w środowisku Google Colab,
- zapis wytrenowanych wag modelu do pliku `.pth`.

Trening miał charakter demonstracyjny i służył przedstawieniu kompletnej procedury uczenia modelu detekcji obiektów.

---

## 6. Detekcja obiektów po treningu
Po zakończeniu treningu zapisane wagi modelu zostały wykorzystane do detekcji obiektów na obrazach walidacyjnych. Procedura inferencji jest analogiczna do tej stosowanej dla modeli wstępnie wytrenowanych, z tą różnicą, że użyto wag dostosowanych do własnego zbioru danych.

Plik z wagami modelu (`.pth`) nie został dołączony do repozytorium ze względu na binarny charakter pliku i brak wymagań formalnych dotyczących jego udostępnienia.

---

## 7. Zawartość repozytorium
Struktura repozytorium projektu:

<img width="472" height="200" alt="image" src="https://github.com/user-attachments/assets/4fdaef19-d2a6-47fb-a1c5-d63afb059331" />

---

## 8. Uruchamianie projektu
Projekt przeznaczony jest do uruchamiania w środowisku **Google Colab**.

W celu uruchomienia projektu należy:
- otworzyć notebook Test fasterrcnn  w Google Colab,
- podłączyć Google Drive zawierający zbiór danych fasterrcnn_mobilenet_finetuned.pth zgodny ze ścieżką która jest w programie bądź zmienić ścieżkę,
- uruchomić notebook od początku do końca.

---

## 9. Podsumowanie
W ramach projektu przygotowano i oznaczono własny zbiór danych, wykorzystano bibliotekę PyTorch oraz TorchVision, porównano kilka modeli detekcji obiektów oraz przeprowadzono samodzielny trening wybranego modelu. W efekcie uzyskano działający system detekcji obiektów klasy samochód.

Projekt został zrealizowany zgodnie z założeniami oraz wymaganiami formalnymi.

