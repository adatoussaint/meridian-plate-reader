# Meridian Plate Reader

Alphanumeric number-plate reader prototype for Meridian Access Systems — EMNIST-based character segmentation, recognition, and confidence-based routing (auto-accept vs. route to a human). Built for ISM 6642's Final Group Project, "Reading the Road."

## Quick start

```
pip install -r requirements.txt
jupyter notebook ML_Final_Project.ipynb
```

Then **Run All**. Parts A through I run entirely on CPU with no GPU or large downloads required — this covers the full pipeline (segmentation, preprocessing, the local MLP classifier, batch testing across noise conditions, and the business-cost analysis) and is enough to run the live demo.

**Part J** (the real CNN, trained on real EMNIST) needs a GPU and downloads the full EMNIST ByClass dataset (~535MB) on first run. Run that section in Google Colab with a GPU runtime (Runtime → Change runtime type → GPU).

## What's in this repo

- `ML_Final_Project.ipynb` — the full notebook: pipeline build, both models (MLP and CNN), evaluation, and the business-cost analysis.
- `docs/Approach_Document.docx` — problem framing, pipeline, data, modeling, evaluation, spike, scope, and risks.
- `docs/Results_Summary.docx` — metrics, conditions, confusion analysis, and failure modes.
- `docs/Business_Note.docx` — the auto-accept / route-to-human policy and its cost at 4,200 vehicles/day.
- `docs/Cell_By_Cell_Reference.docx` — a numbered map of every notebook cell, for quick lookup during the live Q&A.
- `requirements.txt` — Python dependencies.

## Live demo

Part G's live-demo cell accepts a real, previously-unseen image at runtime — see the markdown note directly under that cell for how to point `demo_img` at an uploaded file (either a local path, or `google.colab.files.upload()` in Colab).

## AI disclosure

Claude (Anthropic) was used throughout the build as an AI pair-programmer, as the project brief permits and expects. See the appendix of `docs/Approach_Document.docx` for details.
