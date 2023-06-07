# Speech Language Impairment Detection in childrens

# Set up 

For running the code locally eed [python](https://www.python.org/downloads/) and [jupyter lab](https://jupyter.org/install). However we recommend using [colab](https://colab.research.google.com/) as it already has the setup.

# File description

- data_processing.ipynb: This file is used for data visualization and extracting various spectrogram features from the speech.
- baseline.ipynb: This file contains the code for training baseline models such as XGboost adnd Naive Bayes over the spectrogram features. For XGboost feature importance can alos be visualized.
- wav2vec.ipynb: This file contains code for extracting wav2vec features from the speech. Further a Multi Layer Perceptron is trained on top of the extracted Wave2Vec features.
- PhoneticClassifier.ipynb: This file contains code for training a CNN architecture on the spectogram of speech. As a proof of concept the model is trained on speech signals containing `sh` phonemes. Multiple phonetic graders can be trained on different phonemes. The output of these phonetic graders can then be ensembled to get fina verdict.

# Results

| Model      | Sensitivity(%) | Specificity (%)    | Accuracy (%)|
| :---:       |    :----:   |          :---: | :---: |
|  XGBoost   |   63   | 98   |  89      |
|   Naive Bayes |  42       |  84     |  74   |
|  Multilayer perceptron (MLP)   |  81    | 55   |  61      |
|   Wav2vec + MLP |   52      |   93    |  83| 
|   Wav2vec + MLP + SMOTE  |   73   | 83   |  80      |

# References

```
XGboost - https://xgboost.readthedocs.io/en/stable/
Wav2vec - https://huggingface.co/docs/transformers/model_doc/wav2vec2
Scikit-learn: Machine Learning in Python, Pedregosa et al., JMLR 12, pp. 2825-2830, 2011.
Librosa - https://librosa.org/
pickle - for saving data https://docs.python.org/3/library/pickle.html
```
