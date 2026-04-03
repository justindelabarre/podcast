# 🎙️ Podcast Notes — Data & Tech

Archive personnelle de notes et résumés d'épisodes de podcasts data.

## Structure
```
audio/                        # Fichiers audio locaux (non commités)
episodes/
└── {slug_episode}/
    ├── transcript.txt        # Transcription brute
    └── summary.md            # Résumé structuré
scripts/
├── extract_transcript.ipynb  # Notebook de transcription (Whisper)
└── requirements.txt
```

## Épisodes

| # | Podcast | Invité | Thème | Lien |
|---|---------|--------|-------|------|
| 1 | Data & IA | Matthias (N26) | Data for Marketing — MMM & User Value | [→](episodes/n26_matthias_data_marketing/summary.md) |

## Setup
```bash
# Depuis la racine du repo
python -m venv scripts/venv
scripts\venv\Scripts\activate        # Windows
# source scripts/venv/bin/activate   # Mac / Linux

pip install -r scripts/requirements.txt
```

## Téléchargement

Pour télécharger l'audio d'un épisode YouTube :
```bash
yt-dlp -x --audio-format mp3 -o "audio/episode.mp3" "https://www.youtube.com/watch?v=..."
```

- `-x` : extrait uniquement l'audio
- `--audio-format mp3` : convertit en mp3
- `-o` : chemin de sortie (dans `audio/`, ignoré par git)

## Utilisation

1. Télécharge le fichier audio dans `audio/` via la commande ci-dessus
2. Ouvre `scripts/extract_transcript.ipynb`
3. Mets à jour la variable `AUDIO_PATH` en haut du notebook (`../audio/episode.mp3`)
4. **Kernel > Restart & Clear Outputs** puis **Run All**
5. La transcription est générée dans `audio/transcript.txt`
6. Déplace-la dans `episodes/{slug}/transcript.txt`

## ⚠️ Avant chaque commit

Toujours faire **Kernel > Restart & Clear Outputs** pour ne pas committer les outputs du notebook.