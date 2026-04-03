# 🎙️ Podcast Notes — Data & Tech

Archive personnelle de notes et résumés d'épisodes de podcasts data.

## Structure

```
episodes/
└── {slug_episode}/
    ├── transcript.txt   # Transcription brute
    └── summary.md       # Résumé structuré
scripts/
└── extract_transcript.ipynb  # Notebook de téléchargement / nettoyage
```

## Épisodes

| # | Podcast | Invité | Thème | Lien |
|---|---------|--------|-------|------|
| 1 | Data & IA | Matthias (N26) | Data for Marketing — MMM & User Value | [→](episodes/n26_matthias_data_marketing/summary.md) |

## Stack utilisée

- Python (Databricks / Jupyter)
- Whisper / YouTube DL pour les transcriptions (voir `scripts/`)
