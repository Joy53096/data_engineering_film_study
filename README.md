# Film shot lengths, 1950–1999

This project collects shot statistics from Cinemetrics and film metadata from Wikidata. It asks:

- Do shot lengths change across five decades?
- Does the pattern hold within film genres?
- Do average and median shot lengths tell the same story?

The work follows three stages: test one film, check a small batch, then build a larger sample.

## Current progress

- A Titanic (1997) demo links one HTML page and one REST API item by IMDb ID, title and year.
- The first coverage check contains 25 candidate measurement pages: five per decade from the 1950s through the 1990s.
- Twelve records have identity support; thirteen still need review.
- Three comments explicitly describe excerpts. Two possible duplicate pairs are flagged, not merged.

These checks overlap. Identity support does not mean a full-film measurement. No record has been approved for the final analysis. The larger sample and analysis are still in progress; this pilot does not meet the course's 2,000-record scale requirement.

## Files

| File or folder | Purpose |
| --- | --- |
| `Titanic_Demo.ipynb` | Short HTML/API walkthrough |
| `Film_Collection.ipynb` | Candidate discovery, acquisition, metadata and review |
| `01_raw/` | Saved responses, request logs and replay pointers |
| `02_audit/` | Current intake, film review and demo record |
| `04_process/session_notes.md` | Original development record, including failures and fixes |

The Git snapshot includes the current replay runs. Earlier notebooks and retired runs stay local and are excluded by `.gitignore`.

## Run

Tested on Windows with Python 3.13. Open a terminal in the project root:

```powershell
python -m venv .venv
.\.venv\Scripts\python -m pip install -r requirements.txt
.\.venv\Scripts\python -m jupyterlab
```

Open either notebook and select **Restart Kernel and Run All Cells**. Both notebooks run independently. Keep the notebook files in the project root: paths start from the kernel's working directory.

The defaults use saved responses and make no HTTP requests:

| Notebook | Switches |
| --- | --- |
| Titanic demo | `live = False` |
| Film collection | `collect = False`, `review_live = False` |

To make new requests, change the relevant switch to `True`. `collect` fetches the coverage batch; `review_live` fetches metadata for that batch. In the review setup, `resume_from` can identify an interrupted run. Successful cached responses are reused only when their URL and hash agree with the log. A fresh live run leaves it empty. Keep complete run folders and their `latest_run.txt` pointers together when committing new evidence.

## Data and limits

HTML fields include title, page year, IMDb ID, shot count, measured duration, ASL and MSL. API fields add release years, directors, production countries, genres and runtimes. Multiple API values are retained. The source's shot statistics are published measurements, not statistics newly calculated by this project.

The first-page directory probe is a convenience sample. It includes uncertain titles, short works, excerpts and repeated measurements. Country and version coverage need further checks before comparing decades.

English Wikipedia article requests failed; that text is still missing. One early HTTP 429 response body was overwritten by an old retry helper. The original log and `film_review.json` describe this defect. Later attempts use separate files. All successful review-response bodies were checked against their logged hashes.

Sources: [Cinemetrics](https://cinemetrics.uchicago.edu/), [Wikidata REST API](https://www.wikidata.org/wiki/Wikidata:REST_API), [Wikibase Action API](https://www.mediawiki.org/wiki/Wikibase/API). Source material retains its original attribution and terms.

## Assistance

Codex assisted with acquisition code, debugging, documentation and replay checks. Assisted runs are labelled in the logs. The process record separates those checks from the student's own execution and final analytical decisions.
