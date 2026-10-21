# Assignment 10 — Audio Classification with STT and TTS

## Objective
Design and implement a deep learning application for audio classification that incorporates Speech-to-Text (STT) and Text-to-Speech (TTS), then evaluate its performance using suitable metrics.

## Application
A spoken-command voice assistant. A CNN classifies one of ten spoken commands from audio, STT produces a transcript, and TTS speaks the transcript and classifier prediction.

## Architecture
- **Dataset:** Google Speech Commands via TensorFlow Datasets
- **Audio features:** 64-bin log-Mel spectrograms from 16 kHz mono audio
- **Audio classifier:** CNN with convolution, batch normalization, max pooling, global average pooling, dropout, and softmax output
- **STT:** SpeechRecognition + Google Web Speech API (internet required)
- **TTS:** pyttsx3 (local speech engine; typically offline)
- **Metrics:** Accuracy, macro precision, macro recall, macro F1-score, inference latency, classification report, confusion matrix

## Files
- `Assignment_10_Audio_Classification_STT_TTS.ipynb` — full notebook with Markdown, code, training, evaluation, and end-to-end integration.
- `README.md` — this guide.
- `requirements.txt` — Python dependencies.

## Run the Notebook
Recommended: Python 3.10 or 3.11, with internet access for dataset/STT downloads.

```bash
python -m venv .venv
```

Windows PowerShell:
```powershell
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Open the notebook in VS Code and select the `.venv` kernel, or upload it to Google Colab. Run the notebook cells from top to bottom. Dataset and model training may take time; GPU is helpful but not mandatory.

## End-to-End Audio Demo
1. Record a short WAV file containing one of the supported words: `yes`, `no`, `up`, `down`, `left`, `right`, `on`, `off`, `stop`, or `go`.
2. Place the file in the notebook's working directory.
3. Set `AUDIO_FILE` in Section 13 to the file path.
4. Run the STT, CNN prediction, and TTS demonstration cell.

The notebook's test metrics and plots can be produced without a personal WAV recording. STT requires internet. TTS playback depends on a supported local audio device and speech engine; local execution is recommended.

## Generated Outputs
When the corresponding cells run, the notebook saves:
- `sample_logmel_spectrogram.png`
- `training_curves.png`
- `confusion_matrix.png`
- `evaluation_metrics.csv`
- `audio_command_cnn.keras`

Do not commit large generated model files unless your course requires them. Include the plots and actual metric table in the submission.

## Evaluation Notes
- Report actual test metrics from your run; do not invent values.
- Word Error Rate (WER) is not calculated automatically because ground-truth transcripts are not supplied for a personal audio recording. If formally evaluating STT, prepare reference transcripts and compare them to recognized text.
- TTS naturalness is not represented by classification accuracy; assess playback intelligibility or use a suitable listening evaluation.

## References
- Speech Commands paper: https://arxiv.org/abs/1804.03209
- TensorFlow Datasets: https://www.tensorflow.org/datasets/catalog/speech_commands
- TensorFlow: https://www.tensorflow.org/guide/keras
- Librosa: https://librosa.org/doc/latest/index.html
- SpeechRecognition: https://pypi.org/project/SpeechRecognition/
- pyttsx3: https://pyttsx3.readthedocs.io/
