# 🧱 Git Summarizer Skeleton

This is a reusable GitHub Actions + utility script toolkit for integrating automatic Git commit summarization into any repository. It works in tandem with a deployed summarization microservice (e.g., [GitChangeSummary](https://github.com/your-org/GitChangeSummary)) and assumes the LLM API key (e.g., `GROQ_API_KEY`) is securely stored server-side.

---

## ✨ What It Does

- Automatically extracts Git diffs on each push
- Sends diffs to a central summarization API
- Stores and optionally displays summaries via that service's web UI

---

## 📦 What's Included
```
.
├── .github/
│ └── workflows/
│ └── summarize.yml # GitHub Action that triggers on push
├── scripts/
│ └── extract_diff.py # Script to extract latest commit hash and diff
├── README.md

```

## 🚀 How to Use

### 1. Add this skeleton to your repo

You can either:
- ✅ Manually copy `.github/workflows/summarize.yml` and `scripts/extract_diff.py`

> Ensure the `scripts/` folder is added to your project root.

ensure that SUMMARIZER_URL is the URL on which you run the summarizer service.


### 🛠️ Running `act` Locally

    To ensure compatibility across Apple Silicon and Windows machines:

    1. Create a `.actrc` file in the root of your repo that will contain:

    ```
    --container-architecture linux/amd64
    -P ubuntu-latest=ghcr.io/catthehacker/ubuntu:act-22.04
    ```

    Most Windows users run act on x86_64 by default , so no more configuration is needed




    