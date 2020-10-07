# OSIC-pulmonary-fibrosis-Competetion rank - 70 ( silver medal ) our score = -6.847 , First position score = -6.8305
  https://www.kaggle.com/c/osic-pulmonary-fibrosis-progression

# What is pulmonary fibrosis ? 

Pulmonary fibrosis is a lung disease that occurs when lung tissue becomes damaged and scarred. This thickened, stiff tissue makes it more difficult for your lungs to work properly. As pulmonary fibrosis worsens, you become progressively more short of breath.

<img src="https://www.pulmonaryfibrosis.org/images/default-source/default-album/normal-and-impaired-gas-exchange.png?sfvrsn=c3b0918d_0" width=600>

# What we need to predict ?

We need to predict a patient’s severity of decline in lung function based on a CT scan of their lungs. Lung function is assessed based on output from a spirometer, which measures the forced vital capacity (FVC), i.e. the volume of air exhaled. The challenge is to use machine learning techniques to make a prediction with the image, metadata, and baseline FVC as input.


<img src="https://i.imgur.com/8AWVnqQ.png" width=650>

# Evaluation metrics :-

- The evaluation metric of this competition is a modified version of Laplace Log Likelihood. 
Predictions are evaluated with a modified version of the Laplace Log Likelihood. For each sample in test set, an `FVC` and a `Confidence` measure (standard deviation σ) has to be predicted.

    `Confidence` values smaller than 70 are clipped.
    
    $\large \sigma_{clipped} = max(\sigma, 70),$

    Errors greater than 1000 are also clipped in order to avoid large errors.

    $\large \Delta = min ( |FVC_{true} - FVC_{predicted}|, 1000 ),$

    The metric is defined as:

    $\Large metric = -   \frac{\sqrt{2} \Delta}{\sigma_{clipped}} - \ln ( \sqrt{2} \sigma_{clipped} ).$


Read more about it on the [Evaluation Page](https://www.kaggle.com/c/osic-pulmonary-fibrosis-progression/overview/evaluation).
