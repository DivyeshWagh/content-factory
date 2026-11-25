# Content Factory

A multi-agent GenAI content factory that turns a topic into a researched, edited,
illustrated blog article and saves it as a standalone HTML page.

## What it does

The notebook coordinates these steps:

1. **Clarifier** asks up to three questions to tailor the article.
2. **Researcher** finds current facts and links to sources.
3. **Writer** drafts an approximately 300-word article.
4. **Editor** checks the draft and can request revisions.
5. **Image designer** generates a feature image.
6. **HTML developer** packages the article and image into a page in `outputs/`.

The main workflow is in [`content_factory.ipynb`](content_factory.ipynb).
Example generated pages are included in [`outputs/`](outputs/).

## Requirements

- Python 3.10 or later
- An OpenAI API key with access to the models and tools configured in the notebook

## Setup

From this directory, create and activate a virtual environment:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

Copy `.env.example` to `.env` and add your API key:

```text
OPENAI_API_KEY=your_api_key_here
```

The `.env` file is ignored by Git. Never commit API keys or other credentials.

Start JupyterLab:

```powershell
jupyter lab
```

Open `content_factory.ipynb`, run its cells, and enter a topic when prompted.
Generated HTML files are saved under `outputs/` and opened in your browser.

## Project layout

```text
.
├── content_factory.ipynb
├── requirements.txt
└── outputs/
    └── generated article examples
```

## Notes

- The notebook contains the model names and web-search/image-generation settings
  used by this project. Make sure your API account supports them.
- Review generated research, citations, article text, and images before
  publishing.
- `outputs/` contains sample pages, including embedded images, so those files
  are larger than ordinary text-only HTML.
