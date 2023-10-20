# kaggle-CommonLit-EES (59th place)
### CommonLit - Evaluate Student Summaries 
The goal of this competition is to assess the quality of summaries written by students in grades 3-12. </br>The quality scores consists of 2 types of score (content score and wording score).

### Dataset
[Download kaggle dataset](https://www.kaggle.com/competitions/commonlit-evaluate-student-summaries/overview)


### Evaluation
Submissions are scored using **MCRMSE**, mean columnwise root mean squared error.

### Result
|Model| Tricks| Validation strategy| CV-score | Public-score |Private-score|
|:---:|:---:|:---:|:---:|:---:|:---:|
|DeBERTa-v3-large | freeze(top_half + embeddings)   |StratifiedKFold   |0.468|0.518 |0.544|
|DeBERTa-v3-large +<br /> LightGBM  | freeze(top_half + embeddings)| GroupKFold| 0.510|0.454|0.508|
|DeBERTa-v3-large +<br /> LightGBM  | freeze(top_half + embeddings), <br />Hyperparamter tuning    |GroupKFold|0.522|0.439 |0.486|
|DeBERTa-v3-large +<br /> LightGBM  | freeze(top_half + embeddings), <br />Hyperparamter tuning,<br /> LLRD      |GroupKFold|0.492|0.439|0.471|
|DeBERTa-v3-large +<br /> Catboost  | freeze(top_half + embeddings), <br />Hyperparamter tuning,<br /> LLRD  |GroupKFold|0.499|0.439 |0.484|

LLRD        =   Layer-wise Learning Rate Decay 