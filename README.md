<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>

<h1>🧠 EEG Seizure Detection and Prediction using Deep Learning</h1>

<p>This repository explores the application of deep learning algorithms for both <strong>seizure detection</strong> and <strong>seizure prediction</strong> using Electroencephalogram (EEG) signals.</p>

<h2>📊 Project Overview</h2>

<p>We implement and compare various deep learning models to detect and predict seizures in patients with neurological disorders. The models are trained and evaluated on Raw EEG samples.</p>

<h2>🧪 Dataset</h2>
<p>The <b>‘Seina Scalp Dataset’</b>, was utilized having clinical EEG recordings from epilepsy patients using the 10-20 EEG system and having sampling rate of 512 Hz.</p>
<ul>
  <li>Frontal (FP1, FP2, F3, F4, F7, F8, FZ)</li>
  <li>Central (C3, C4, CZ)</li>
  <li>Parietal (P3, P4, P7, P8, PZ)</li>
  <li>Temporal (T7, T8)</li>
  <li>Occipital (O1, O2)</li>
</ul>
<img width="800" height="400" alt="image" src="https://github.com/user-attachments/assets/95b11c3b-9485-4f72-996f-17ee9011fa69" />
<p>3 channels of EEG data are shown namely - FZ, CZ, PZ channels respectively, along with their categorization of 3 states of seizure – preictal, ictal, postictal.</p>

<h2>⚙️ Feature Engineering</h2>
<ul>
  <li><strong>Down-sampling: </strong>EEG recordings were down-sampled from 512 Hz to 128 Hz to reduce computational overhead without any compromise of vital brainwave dynamics.</li>
  <li><strong>Segmentation: </strong>EEG signals were divided into 5-second windows (640 samples per window at 128 Hz). This can help in better detection and prediction without overlapping.</li>
  <li><strong>Normalization: </strong>A specific type of feature scaling is done, called ‘z-score standardization’ in which single EEG epochs were individually normalised, i.e. by subtracting the mean and dividing by the standard deviation. This is applied so that it can reduce inter-patient data variation.</li>
  <li><strong>Artifact Management: </strong> These EEG Segments having extreme outliers, NaN values, or non-biological noise, were clipped, interpolated and removed.</li>
</ul>

<h2>🚀 Models Used</h2>
<h3>Seizure Prediction</h3>
<ul>
  <li><strong>Hybrid CNN-BiLSTM</strong></li>
  <li><strong>Attention-Augmented Multilayer Perceptron (MLP)</strong></li>
  <li><strong>Transformer-based Model</strong></li>
</ul>
<h3>Seizure Detection</h3>
<ul>
  <li><strong>Feedforward Neural Network (FNN)</strong></li>
  <li><strong>Transformer-based Model</strong></li>
</ul>

<h2>🏛️ Model Architecture</h2>
<img width="1100" height="600" alt="DL Architectures" src="https://github.com/user-attachments/assets/526e5e4c-a0db-4eea-a951-843fca8bc44e" />
Method Pipeline with Deep Learning Model Architectures

<h2>📈 Results</h2>
<h3>Seizure Prediction</h3>
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Model</th>
      <th>Accuracy</th>
      <th>Average Prediction Probabilities</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>CNN-BiLSTM</td>
      <td>0.9833 (98.33%)</td>
      <td>0.9692</td>
    </tr>
    <tr>
      <td>Autoencoder</td>
      <td>0.9696 (96.96%)</td>
      <td>0.9383</td>
    </tr>
    <tr>
      <td>Attention Model</td>
      <td>0.9567 (95.67%)</td>
      <td>0.8157</td>
    </tr>
  </tbody>
</table>
<h4>Visual Representation</h4>
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/16e14a71-30fe-4775-91e4-a7388bd816c6" />
<p>Probability of Preictal Detection across the Temporal Domain of Testing Dataset</p>

<h3>Seizure Detection</h3>
<table border="1" cellspacing="0" cellpadding="8">
  <thead>
    <tr>
      <th>Model</th>
      <th>True Positive Area</th>
      <th>False Positive Area</th>
      <th>Approx. Accuracy</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>FNN</td>
      <td>0.3 min</td>
      <td>0.1 min</td>
      <td>0.75 (75 %)</td>
    </tr>
    <tr>
      <td>Transformer Model</td>
      <td>1 min</td>
      <td>0.2 min</td>
      <td>0.89 (~90 %)</td>
    </tr>
  </tbody>
</table>
<h4>Visual Representation</h4>
<img width="900" height="200" alt="image" src="https://github.com/user-attachments/assets/9dfd46e2-f8ad-4d1b-9254-f3299c8ba87c" />
<p>Temporal Overlay Plot for Seizure Detection</p>

<h2>📂 Repository Structure</h2>
<pre>
├── EEG data/  
├── Models/
│   ├── Seizure Detection.ipynb
│   └── Seizure Prediction.ipynb
└── README.html
</pre>

</body>
</html>
