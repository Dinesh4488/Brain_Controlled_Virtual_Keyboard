# P300 Speller Using CNN

A complete pipeline for P300-based Brain-Computer Interface (BCI) speller using Convolutional Neural Networks (CNNs). This project includes data preprocessing, model training, evaluation, and a Tkinter-based GUI for testing predictions.





## Setup & Installation

1. **Clone the repository**
2. **Install dependencies:**
   ```
   pip install -r requirements.txt
   ```
3. **Prepare data:**
   - Place your raw `.mat` files in the `datasets/` folder.
   - Run `Data Preprocessing.py` to generate all necessary `.npy` files.

---

## Download EEG Datasets
You can download EEG datasets from the following link:
- https://drive.google.com/drive/folders/1bPkUAXfaNIASRYOV8dfZ4E5meMvylhy_?usp=drive_link

Place the downloaded `.mat` files in the `datasets/` folder before running preprocessing.

---

## Model Training & Evaluation

### 1. Create the Base Model
```
python P300_Speller_Using_CNN.py
```
This creates `Models/Base_Model.h5`.

### 2. Train and Evaluate
- **Subject A:**
  ```
  python Subject_A_CNN.py
  ```
- **Subject B:**
  ```
  python Subject_B_CNN.py
  ```
- **Combined (A+B):**
  ```
  python Subject_AB_CNN.py
  ```

---

## Example Results

**Subject A:**
```
Confusion Matrix:
[[3883  197]
 [ 214  602]]
Classification Report:
              precision    recall  f1-score   support

           0       0.95      0.95      0.95      4080
           1       0.75      0.74      0.75       816

    accuracy                           0.92      4896
   macro avg       0.85      0.84      0.85      4896
weighted avg       0.92      0.92      0.92      4896
```

**Subject B:**
```
Confusion Matrix:
[[3875  205]
 [ 215  601]]
Classification Report:
              precision    recall  f1-score   support

           0       0.95      0.95      0.95      4080
           1       0.75      0.74      0.74       816

    accuracy                           0.91      4896
   macro avg       0.85      0.84      0.84      4896
weighted avg       0.91      0.91      0.91      4896
```

**Combined Model (Test Set AB):**
```
Confusion Matrix:
[[3787  293]
 [ 191  625]]
Classification Report/Test Set A:
              precision    recall  f1-score   support

           0       0.95      0.93      0.94      4080
           1       0.68      0.77      0.72       816

    accuracy                           0.90      4896
   macro avg       0.82      0.85      0.83      4896
weighted avg       0.91      0.90      0.90      4896

Confusion Matrix:
[[3851  229]
 [ 138  678]]
Classification Report/Test Set B:
              precision    recall  f1-score   support

           0       0.97      0.94      0.95      4080
           1       0.75      0.83      0.79       816

    accuracy                           0.93      4896
   macro avg       0.86      0.89      0.87      4896
weighted avg       0.93      0.93      0.93      4896
```

---

## GUI Usage

1. **Run the GUI:**
   ```
   python GUI.py
   ```
2. **Select a model** (Subject A, B, or Combined)
3. **Load a test sample** from `datasets/Test_Data/`
4. **Click Predict** to see the model's prediction and the actual character

---

## Notes & Recommendations
- All file paths are now relative and cross-platform.
- Models are saved in the `Models/` directory.
- Test data for the GUI is in `datasets/Test_Data/`.
- For best results, ensure your data is preprocessed with `Data Preprocessing.py` before training.
- You can further tune the model, try different architectures, or balance the dataset for improved P300 detection.

---

## License
MIT License

---

## Citation
If you use this codebase for research, please cite appropriately.

