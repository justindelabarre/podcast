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
| 2 | Data & IA | Christophe Blépharic (BLEF) | Fusion Fivetran × dbt — stratégie & impacts | [→](episodes/blef_fivetran_x_dbt/summary.md) |

## Setup
```bash
# Depuis la racine du repo
python -m venv venv
venv\Scripts\activate                # Windows
# source venv/bin/activate           # Mac / Linux

pip install -r scripts/requirements.txt

# Activer le strip automatique des outputs Jupyter avant chaque commit
nbstripout --install
```

## Téléchargement

```bash
yt-dlp -o "audio/episode.webm" "https://www.youtube.com/watch?v=..."
```

## Utilisation

1. Télécharge le fichier audio dans `audio/` via la commande ci-dessus
2. Ouvre `scripts/extract_transcript.ipynb`
3. Mets à jour `EPISODE_SLUG` et `AUDIO_FILE` dans la cellule de configuration en haut du notebook
4. **Kernel > Restart & Clear Outputs** puis **Run All**
5. La transcription est générée dans `episodes/{slug}/transcript.txt`

## ⚠️ Avant chaque commit

Les outputs du notebook sont strippés automatiquement par `nbstripout` (hook git local).
Aucune action manuelle requise — pense simplement à lancer `nbstripout --install` après le setup.