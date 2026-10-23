# Theory First, AI Second: Aspect-Based Sentiment Analysis of Online Reviews

EMEA CHRIE Research Webinar, 23 October 2026.
Jeong-Yeol Park, Ph.D., Rosen College of Hospitality Management, University of Central Florida.

## What is here

| File | What it is |
|---|---|
| `EMEA_CHRIE_ABSA_Workshop.ipynb` | The webinar notebook. It has already been run, so every output is visible. |
| `data/maple_city_reviews.csv` | 11,010 restaurant reviews from Maple City, a synthetic, fictional city. Free to reuse. |
| `data/reference_coding_150.csv` | The 150 distinct sentences in the reviews, hand-coded by construct (aspect) and polarity. Used in Step 5. |
| `data/coded_samples_300.csv` | Two random samples of 300 sentences, coded by construct (AI-assisted). Round 1 built the bigram dictionary; round 2 tested it. Not needed to run the notebook. |
| `EMEA_CHRIE_Gemini_Prompts.docx` | The prompts to type into Gemini in Colab, one per step. |

## Open the notebook in Colab

[Open in Colab](https://colab.research.google.com/github/jeong-yeol/EMEA-CHRIE-Webinar/blob/main/EMEA_CHRIE_ABSA_Workshop.ipynb)

To keep your own copy: in Colab, click **File**, then **Save a copy in Drive**.

## Get the data into Colab

**1. Download the two files.** Open the `data` folder above. Click `maple_city_reviews.csv`, then the download button (arrow pointing down, top right). Do the same for `reference_coding_150.csv`. Both go to your Downloads folder.

**2. Put them in Google Drive.** Open [drive.google.com](https://drive.google.com). Click **+ New**, then **New folder**, and name it `EMEA_CHRIE`. Open the folder. Click **+ New**, then **File upload**, and pick the two files.

**3. Connect Colab to your Drive.** In Colab, click the folder icon on the left, then the Drive icon (folder with the Drive logo). Colab adds a cell at the top. Run it, click **Connect to Google Drive**, choose your Google account, and click **Continue**. A folder named `drive` appears.

**4. Read the files from Drive.** In Step 1 and Step 5 of the notebook, use the full path:

```python
reviews = pd.read_csv("/content/drive/MyDrive/EMEA_CHRIE/maple_city_reviews.csv")
ref = pd.read_csv("/content/drive/MyDrive/EMEA_CHRIE/reference_coding_150.csv").set_index("sentence")
```

If you use Drive, skip the upload prompt in the Setup cell.

**Quick alternative (one session only).** Click the folder icon on the left, then the upload arrow, and pick the two files. Colab deletes them when the session ends, so upload them again next time.

## Notes

- Maple City is synthetic. Every sentence is known, so you can see exactly where each method goes wrong. With your own data, hand-code a random sample of 100 to 200 sentences and run the same checks.
- In practice, people do the coding. In this webinar some checks were AI-assisted, for demonstration.
- The data and the model come from *Analyzing Online Reviews with AI: A No-Code Guide from Raw Data to Research Findings* (2026).

Questions: Jeong-Yeol.Park@ucf.edu
