# Detekcja obiektów – samochody (Computer Vision)

## 1. Opis projektu
Celem projektu jest detekcja obiektów klasy **samochód** na obrazach przy użyciu
gotowych, wstępnie wytrenowanych modeli detekcji obiektów dostępnych w bibliotece
TorchVision. Projekt został zrealizowany w środowisku **Google Colab** i skupia się
na porównaniu jakości działania różnych architektur detekcyjnych.

Projekt nie obejmuje treningu modeli od zera – wykorzystano modele **pretrained**
wytrenowane na zbiorze COCO.

---

## 2. Dataset
Do projektu wykorzystano gotowy zbiór danych zawierający obrazy z obiektami klasy
samochód.

- Liczba obrazów: 409
- Format adnotacji: YOLO
- Narzędzie do etykietowania: LabelImg

Struktura datasetu:




Zbiór danych nie jest dołączony bezpośrednio do repozytorium.
Link do datasetu: **[do uzupełnienia]**

---

## 3. Wykorzystane biblioteki
- Python 3
- PyTorch
- TorchVision
- NumPy
- OpenCV / PIL
- Matplotlib

---

## 4. Wykorzystane modele detekcji
W projekcie wykorzystano pięć różnych architektur detekcji obiektów:

1. Faster R-CNN (ResNet50 + FPN)  
2. Faster R-CNN (MobileNetV3 + FPN)  
3. RetinaNet (ResNet50 + FPN)  
4. SSD300 (VGG16)  
5. FCOS (ResNet50 + FPN)  

Wszystkie modele są wstępnie wytrenowane na zbiorze **COCO** i używane wyłącznie
w trybie inferencji.

---

## 5. Metodologia
- Wczytanie obrazu wejściowego przez użytkownika w środowisku Google Colab
- Załadowanie gotowego modelu detekcji
- Przeprowadzenie inferencji
- Wykrycie obiektów klasy *car* (mapowanej opisowo na *samochód*)
- Wizualizacja wyników w postaci bounding boxów oraz wartości confidence

Projekt nie obejmuje etapu treningu ani fine-tuningu modeli.

---

## 6. Wyniki
Dla każdego z pięciu modeli wykonano detekcję na tym samym obrazie testowym.
Wyniki przedstawiono w postaci obrazów z zaznaczonymi bounding boxami
oraz wartościami confidence.

Przykładowe wyniki znajdują się w folderze:
assets/results/

---

## 7. Porównanie modeli
Modele porównano pod względem:
- jakości detekcji obiektów
- liczby poprawnie wykrytych samochodów
- stabilności detekcji
- subiektywnej jakości bounding boxów
- czasu inferencji (opcjonalnie)

---

## 8. Wnioski
Na podstawie przeprowadzonych eksperymentów można wskazać różnice pomiędzy
poszczególnymi architekturami detekcji obiektów oraz ich przydatność do zadania
detekcji samochodów na obrazach.

---

## 9. Uruchomienie projektu
1. Otwórz notebook `notebooks/inference.ipynb` w Google Colab
2. Uruchom wszystkie komórki
3. Załaduj obraz wejściowy
4. Obejrzyj wyniki detekcji dla poszczególnych modeli
