# MN – Projekt semestralny  
## Detekcja obiektów (samochody) z użyciem PyTorch i TorchVision

---

## 1. Cel projektu
Celem projektu było stworzenie kompletnego systemu detekcji obiektów klasy **samochód**, obejmującego pełny pipeline przetwarzania danych:
- przygotowanie i etykietowanie zbioru danych,
- wykorzystanie gotowych modeli detekcji obiektów,
- porównanie kilku architektur sieci neuronowych,
- samodzielny trening (fine-tuning) wybranego modelu,
- detekcję obiektów na obrazach.

Projekt został zrealizowany w środowisku **Google Colab** z wykorzystaniem biblioteki **PyTorch**.

---

## 2. Zbiór danych
- Liczba obrazów: **409**
- Klasa obiektów: **samochód**
- Format etykiet: **YOLO**
- Narzędzie do etykietowania: **LabelImg**

Struktura zbioru danych:
dataset/
├── images/
│ ├── train/
│ ├── val/
│ └── test/
└── labels/
├── train/
├── val/
└── test/

Zbiór danych został ręcznie oznaczony w narzędziu LabelImg.  
Do etapu treningu wykorzystano wyłącznie obrazy zawierające co najmniej jeden obiekt, ponieważ modele detekcji w bibliotece TorchVision wymagają obecności bounding boxów w danych uczących.

---

## 3. Wykorzystane technologie i biblioteki
- Python 3
- PyTorch
- TorchVision
- PIL (Python Imaging Library)
- NumPy
- Google Colab

---

## 4. Modele detekcji obiektów – porównanie
W części porównawczej projektu wykorzystano pięć gotowych (pretrained) modeli detekcji obiektów dostępnych w bibliotece TorchVision:

- Faster R-CNN ResNet50 FPN  
- Faster R-CNN MobileNetV3 Large FPN  
- RetinaNet ResNet50 FPN  
- SSD300 VGG16  
- FCOS ResNet50 FPN  

Modele zostały porównane wizualnie na tych samych obrazach wejściowych pod kątem:
- liczby wykrytych obiektów,
- stabilności detekcji,
- jakości wyznaczonych ramek ograniczających (bounding boxów).

---

## 5. Samodzielny trening modelu (maksymalny poziom)
W celu spełnienia wymagań maksymalnego poziomu projektu wykonano **fine-tuning** wybranego modelu detekcji obiektów:

**Faster R-CNN MobileNetV3 Large FPN**

Cechy treningu:
- wykorzystanie własnego zbioru danych z etykietami YOLO,
- mapowanie wszystkich obiektów do jednej klasy (samochód),
- trening demonstracyjny w środowisku Google Colab,
- zapis wytrenowanych wag modelu do pliku `.pth`.

Trening miał charakter demonstracyjny i służył zaprezentowaniu pełnej procedury uczenia modelu detekcji obiektów, zgodnie z wymaganiami zadania.

---

## 6. Detekcja obiektów po treningu
Po zakończeniu treningu zapisane wagi modelu zostały użyte do detekcji obiektów na obrazach walidacyjnych.  
Procedura detekcji jest identyczna jak w przypadku modeli wstępnie wytrenowanych, z tą różnicą, że wykorzystywane są wagi modelu dostosowanego do własnego zbioru danych.

Plik z wagami modelu (`.pth`) **nie został umieszczony w repozytorium**, ponieważ jest to plik binarny i nie jest wymagany do oceny projektu.

---

## 7. Zawartość repozytorium
├── notebooks/
│ ├── inference.ipynb – detekcja obiektów i porównanie modeli pretrained
│ └── training.ipynb – trening (fine-tuning) modelu detekcji
├── README.md – dokumentacja projektu
├── .gitignore
└── requirements.txt

---

## 8. Uruchamianie projektu
Projekt przeznaczony jest do uruchamiania w środowisku **Google Colab**.

Aby uruchomić projekt:
1. Otworzyć wybrany notebook (`training.ipynb` lub `inference.ipynb`) w Google Colab.
2. Podpiąć Google Drive zawierający zbiór danych.
3. Uruchomić notebook od początku do końca.

---

## 9. Podsumowanie
Projekt spełnia wszystkie wymagania zadania:
- przygotowano i oznaczono zbiór danych,
- wykorzystano bibliotekę PyTorch oraz TorchVision,
- porównano pięć modeli detekcji obiektów,
- wykonano samodzielny trening (fine-tuning) modelu,
- uzyskano działającą detekcję obiektów na obrazach.

Projekt został zrealizowany zgodnie z założeniami i wymaganiami formalnymi.
