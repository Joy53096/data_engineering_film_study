# Film shot lengths, 1950–1999

This project collects shot statistics from Cinemetrics and metadata from Wikidata. It explores changes across decades and genres, and whether average and median shot lengths tell the same story.

The current starter sample focuses on well-known films. It is a purposive sample, so its results will describe the selected classics rather than all films.

## Current stage

- The Titanic demo shows one HTML/API match.
- `film_list.json` proposes five familiar films per decade: 25 candidates in total.
- Twenty-three titles refer to Douban Top 250; two use the BFI Sight and Sound 2022 critics' list. The source, rank, audience score where available, and check date are recorded separately. These measures are not combined.
- Page links were found for 22 candidates in a bounded title/year directory check. Three remain pending; this does not prove that the site has no matching measurement.
- Identity and full-film boundaries still need review. No final sample or decade trend is claimed. The project remains below the course's 2,000-record requirement.

## Main files

| File or folder | Purpose |
| --- | --- |
| `Titanic_Demo.ipynb` | Short one-film walkthrough |
| `Film_Collection.ipynb` | Read the list, request HTML/API data, match and save |
| `film_list.json` | Editable titles, years, source links, item IDs and ranking references |
| `01_raw/ranked_films/` | Current saved responses, logs and source-discovery evidence |
| `02_audit/ranked_films.json` | Output from the current collector |
| `04_process/session_notes.md` | Development history and known problems |

Earlier coverage and identity-review files remain as process evidence. They are separate from the new candidate list. The first Git commit preserves the earlier notebook version.

## Run

Tested on Windows with Python 3.13. From the project root:

```powershell
python -m venv .venv
.\.venv\Scripts\python -m pip install -r requirements.txt
.\.venv\Scripts\python -m jupyterlab
```

Open a notebook and select **Restart Kernel and Run All Cells**. Each notebook runs independently. Keep both notebook files beside `01_raw`.

Both notebooks default to `live = False`, which reads saved responses. Set `live = True` for new requests. After editing the film list, collect a new batch before replaying it. A live run creates a new folder and saves raw responses and a request log. Keep each complete run folder together with its `latest_run.txt` pointer when committing evidence.

To add a film, copy its public Cinemetrics page URL and Wikidata item ID into the list, then check its title, year and director. The teaching notebook does not run the earlier directory-query or automatic-search system.

## What the collector keeps

HTML: title, year, IMDb links, shot count, measured duration, ASL, MSL and contributor comment.

API: IMDb IDs, release years, directors, countries, genres and runtimes. Multiple values are retained and IDs receive readable labels. The published shot statistics are read from the source.

A shared IMDb ID and supported year are labelled as an identity match. Other records stay marked for review. A match does not establish full-film measurement. Article text is still pending. The earlier Top Gun excerpt remains a saved teaching example in the notebook.

## Sources and assistance

Selection references: [Douban Top 250](https://movie.douban.com/top250) and [BFI Sight and Sound](https://www.bfi.org.uk/sight-and-sound/greatest-films-all-time). Douban references were checked in a web viewer, not scraped by the teaching notebook. Audience scores can change; BFI ranks refer to the stated 2022 poll.

Data sources: [Cinemetrics](https://cinemetrics.uchicago.edu/) and [Wikidata](https://www.wikidata.org/wiki/Wikidata:REST_API). Source material retains its original attribution and terms.

Codex assisted with code, source checks, debugging and replay verification. Logs identify assisted runs. The student still needs to review the final sample and complete the analysis. Earlier failures, including a missing early HTTP 429 body, remain documented in the historical review and process notes.
