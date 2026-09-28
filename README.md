# AI Artistry: Creativity in the Age of Artificial Intelligence

MSc Artificial Intelligence dissertation, City, University of London (2024). Graduated with Distinction.

This project asks how close generative models can get to human creative work, and how you would even measure that. It generates classical-style music and poetry, then combines the two into a single spoken-word-over-music piece.

## What's in the repo

| Part | Approach | Folder |
|---|---|---|
| Music generation | Three sequence models trained on the **MAESTRO v3** piano dataset: LSTM, GRU (64- and 256-unit variants) and a Transformer, built in TensorFlow/Keras with MIDI processing via `pretty_midi` and `music21` | `Music Generation Models/` |
| Poetry generation | **GPT-2** fine-tuned for poetry (Hugging Face Transformers) and compared against the base model | `Poetry Generation/` |
| Music + poetry | Generated poems voiced with text-to-speech (gTTS) and layered over the generated music | `TTS Model Combining Music and Poetry/` |

## Evaluation

Generative output is hard to score with a single number, so I designed task-specific metrics:

- **Music:** note density, empty-beat ratio, pitch centricity and macroharmony, used to compare the LSTM, GRU and Transformer outputs against the training data.
- **Poetry:** rhyme density, readability, sentiment and lyrical complexity, used to compare fine-tuned GPT-2 with the base model.

## Running it

The notebooks were written for Google Colab. The trained checkpoints and data files are too large for GitHub. The LSTM folder's README links to them; upload them into the Colab session, then run the `Generate_*` notebook for each model.

## Stack

Python · TensorFlow / Keras · Hugging Face Transformers (GPT-2) · pretty_midi · music21 · gTTS · Google Colab
