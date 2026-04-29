# Automatyczna Klasyfikacja Obrazów Fasoli / Automated Bean Image Classification

*English version is available below.*

---

## Wersja Polska

### Opis Projektu i Cel Biznesowy
Niniejszy projekt ma na celu stworzenie i wdrożenie systemu rozpoznawania odmian fasoli na podstawie obrazów. System realizuje zadanie wieloklasowej klasyfikacji, rozróżniając 12 odrębnych gatunków/odmian fasoli. 

### Źródło Danych
Projekt opiera się na otwartym zbiorze obrazów: [Hyacinth bean image dataset](https://www.kaggle.com/datasets/pratikgorde/hyacinth-bean-image-dataset) udostępnionym w serwisie Kaggle.

### Architektura i Potok Przetwarzania Danych (Pipeline)
Ostateczna wersja projektu znajduje się w folderze najduje się w folderze `OSTATECZNY PROJEKT`. Został on podzielony na kilka niezależnych notatników Jupyter, z których każdy odpowiada za konkretny etap tworzenia modelu uczenia maszynowego:

1. **Eksploracyjna Analiza Danych i Ekstrakcja Cech (`projekt_ML_eda_OSTATECZNA.ipynb`)**
   * Oczyszczanie, normalizacja i ujednolicenie formatu danych wejściowych.
   * Zaawansowana analiza rozkładów kanałów RGB oraz ekstrakcja podstawowych cech numerycznych z obrazów, tworzących zbiór danych tabelarycznych dla klasycznych algorytmów.

2. **Augmentacja Danych (`Augmentation_OSTATECZNA.ipynb`)**
   * Zwiększenie odporności modelu na wariancję danych wejściowych.
   * Zastosowane techniki obejmują: odbicia lustrzane, losowe obroty w zakresie od -30 do 30 stopni oraz losowe przycięcia obrazu (do 30% jego powierzchni).
   * Podział zbioru danych na treningowy i testowy w proporcji 80/20.

3. **Klasyfikacja przy użyciu Tradycyjnego Uczenia Maszynowego (`Clasification_OSTATECZNA.ipynb`)**
   * Trenowanie klasycznych estymatorów (np. Random Forest) na wyekstrahowanych cechach (tabelarycznych).
   * Przeprowadzenie analizy istotności cech (Feature Importance) w celu zrozumienia, które składowe obrazu (np. statystyki kolorów) mają największy wpływ na decyzję modelu.

4. **Głębokie Uczenie - Sieci Konwolucyjne (`sieci neuronowe_OSTATECZNA.ipynb`)**
   * Opracowanie architektury, trening i ewaluacja głębokich konwolucyjnych sieci neuronowych (CNN) w oparciu o framework TensorFlow/Keras.
   * Wykorzystanie biblioteki OpenCV do optymalnego potoku ładowania i wstępnego przetwarzania obrazów przed podaniem ich do sieci.

5. **Strojenie Hiperparametrów i Modele Zespołowe (`fine tuning.ipynb`)**
   * Optymalizacja hiperparametrów algorytmów przy użyciu metody `GridSearchCV`.
   * Skonstruowanie modelu głosującego (`Soft-Voting Classifier`) łączącego predykcje regresji logistycznej, algorytmu k-najbliższych sąsiadów (KNN) oraz drzew decyzyjnych.
   * Walidacja interpretowalności predykcji za pomocą wartości SHAP (SHapley Additive exPlanations).



### Technologie i Narzędzia
* **Język programowania:** Python
* **Przetwarzanie danych i obrazów:** Pandas, NumPy
* **Wizualizacja:** Matplotlib, Seaborn
* **Uczenie Maszynowe:** Scikit-learn
* **Głębokie Uczenie:** TensorFlow



---

## English Version

### Project Overview and Business Objective
This project aims to develop and deploy a computer vision system capable of recognizing bean varieties from digital images. The system performs multi-class classification, distinguishing between 12 distinct bean species/varieties.

### Data Source
The project relies on an open-source image dataset: [Hyacinth bean image dataset](https://www.kaggle.com/datasets/pratikgorde/hyacinth-bean-image-dataset) available on Kaggle.

### Architecture and Data Pipeline
The project is modularly divided into several independent Jupyter notebooks, each responsible for a specific stage of the machine learning lifecycle:

1. **Exploratory Data Analysis and Feature Extraction (`projekt_ML_eda_OSTATECZNA.ipynb`)**
   * Cleaning, normalizing, and standardizing the input data format.
   * Advanced analysis of RGB channel distributions and extraction of basic numerical features from images, creating a tabular dataset for classical algorithms.

2. **Data Augmentation (`Augmentation_OSTATECZNA.ipynb`)**
   * Increasing model robustness to input data variance.
   * Applied techniques include: horizontal/vertical flips, random rotations (-30 to 30 degrees), and random cropping (up to 30% of the image area).
   * Splitting the dataset into training and testing sets with an 80/20 ratio.

3. **Classification using Traditional Machine Learning (`Clasification_OSTATECZNA.ipynb`)**
   * Training classical estimators (e.g., Random Forest) on the extracted tabular features.
   * Conducting Feature Importance analysis to understand which image components (e.g., color statistics) most strongly influence the model's decisions.

4. **Hyperparameter Tuning and Ensembles (`fine tuning (1).ipynb`)**
   * Optimizing algorithm hyperparameters using `GridSearchCV`.
   * Constructing a `Soft-Voting Classifier` combining predictions from Logistic Regression, K-Nearest Neighbors (KNN), and Decision Trees.
   * Validating prediction interpretability using SHAP (SHapley Additive exPlanations) values.

5. **Deep Learning - Convolutional Neural Networks (`sieci neuronowe_OSTATECZNA.ipynb`)**
   * Designing, training, and evaluating deep Convolutional Neural Networks (CNN) using the TensorFlow/Keras framework.
   * Utilizing OpenCV for an optimal image loading and preprocessing pipeline before feeding data into the network.

### Technologies and Tools
* **Programming Language:** Python
* **Data and Image Processing:** Pandas, NumPy, OpenCV (cv2), Pillow (PIL)
* **Visualization:** Matplotlib, Seaborn
* **Machine Learning:** Scikit-learn
* **Deep Learning:** TensorFlow
* **Interpretability:** SHAP


## Authors
- Mateusz Jamroż
- Karol Kacprzak


