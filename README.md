# Dataset Information

The data in the `Dataset` folder comes from the [Hyacinth Bean Image Dataset](https://www.kaggle.com/datasets/pratikgorde/hyacinth-bean-image-dataset) on Kaggle.

---

## Dependencies

All Python dependencies are listed in `dependencies.txt`.  
Install them with:

```bash
pip install -r dependencies.txt
```

## Recommended Execution Order  
(from **OSTATECZNY PROJEKT**)  
1. `Augmentation.ipynb`  
2. `projekt_ML_eda_ostateczna.ipynb`  
3. `sieci_neuronowe.ipynb`  
4. `Clasification.ipynb`  
5. `Fine tuning.ipynb`  

## Completed Project Structure  
The **final project** folder contains:  
1. The five notebooks listed above  
2. Two data-frame files (training and test sets)  
3. Instructions: to generate both data frames from the raw images, run `projekt_ML_eda_ostateczna.ipynb` first on the training subset, then on the test subset (one of those two sections is commented out at the start/end of the notebook)  
4. Neural networks gave good but not sufficient results:  
   - A vanilla MLP reached up to **95%** accuracy after various tweaks  
   - A CNN, despite many trials, did not exceed **90%** accuracy, so additional metrics weren’t even calculated  
5. The most effective approach was a **SoftVote ensemble with optimized weights**, achieving **98%** across all metrics on a test sample of nearly 700 seeds  
6. Stacking also performed well, but all other individual models were significantly worse

## Validation
The project has been validated by independent teem and their feedback has been incorporated on the way

## Authors
- Mateusz Jamroż
- Karol Kacprzak


