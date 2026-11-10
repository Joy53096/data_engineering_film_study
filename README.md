# Film shot lengths, 1950–1999

This project collects shot statistics from Cinemetrics and metadata from Wikidata. TMDB provides ratings and vote counts for checking a larger candidate pool. It explores changes across decades and genres, and whether average and median shot lengths tell the same story.

The current starter sample focuses on well-known films. It is a purposive sample, so its results will describe the selected classics rather than all films.

## Current stage

- The Titanic demo shows one HTML/API match.
- `Film_Selection.ipynb` reads one TMDB results page per decade, sorted by vote count: 100 candidates from five successful requests. No rating or vote-count cutoff has been chosen. These candidates have not been matched to Cinemetrics.
- `film_list.json` proposes five familiar films per decade: 25 candidates in total.
- Twenty-three titles refer to Douban Top 250; two use the BFI Sight and Sound 2022 critics' list. The source, rank, audience score where available, and check date are recorded separately. These measures are not combined.
- Page links were found for 22 candidates in a bounded title/year directory check. Three remain pending; this does not prove that the site has no matching measurement.
- Identity and full-film boundaries still need review. No final sample or decade trend is claimed. The project remains below the course's 2,000-record requirement.

## Main files

| File or folder | Purpose |
| --- | --- |
| `Titanic_Demo.ipynb` | Short one-film walkthrough |
| `Film_Selection.ipynb` | Check TMDB candidates before setting final selection rules |
| `Film_Collection.ipynb` | Read the list, request HTML/API data, match and save |
| `film_list.json` | Editable titles, years, source links, item IDs and ranking references |
| `01_raw/ranked_films/` | Current saved responses, logs and source-discovery evidence |
| `01_raw/tmdb_candidates/` | TMDB candidate responses and request logs |
| `02_audit/tmdb_candidates.json` | The 100 candidates and collection checks |
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

Open a notebook and select **Restart Kernel and Run All Cells**. Each notebook runs independently. Keep the three notebook files beside `01_raw`.

All three notebooks default to `live = False`, which reads saved responses. Set `live = True` for new requests. After editing the film list, collect a new batch before replaying it. A live run creates a new folder and saves raw responses and a request log. Keep each complete run folder together with its `latest_run.txt` pointer when committing evidence.

To add a film, copy its public Cinemetrics page URL and Wikidata item ID into the list, then check its title, year and director. The teaching notebook does not run the earlier directory-query or automatic-search system.

## TMDB candidate check

Run `Film_Selection.ipynb` before expanding the film list. Its default mode reads the saved responses without a token. To make new requests, create a local `.env` file with `TMDB_READ_TOKEN=your_token`, then set `live = True`. Never print the token or headers. `.env` is ignored by Git.

This check uses page 1 from each decade and sorts by vote count. It is not a random sample or a final list of classics. No country or genre cutoff is applied; English labels do not mean English-only films. Original language does not establish production country. Shorts and full-film measurement boundaries still need review.

All five saved responses report 20,001 results and 1,001 pages. These totals were not verified and are not used as coverage estimates. Only the 100 returned records are counted here. The existing 25-film pilot stays separate.

## What the collector keeps

HTML: title, year, IMDb links, shot count, measured duration, ASL, MSL and contributor comment.

API: IMDb IDs, release years, directors, countries, genres and runtimes. Multiple values are retained and IDs receive readable labels. The published shot statistics are read from the source.

A shared IMDb ID and supported year are labelled as an identity match. Other records stay marked for review. A match does not establish full-film measurement. Article text is still pending. The earlier Top Gun excerpt remains a saved teaching example in the notebook.

## Sources and assistance

<a href="https://www.themoviedb.org"><img src="https://www.themoviedb.org/assets/2/v4/logos/v2/blue_short-8e7b30f73a4020692ccca9c88bafe5dcb6f8a62a4c6bc55cd9ba82bb2cd95f6c.svg" width="120" alt="TMDB"></a>

This product uses the TMDB API but is not endorsed or certified by TMDB.

TMDB sources: [Discover API](https://developer.themoviedb.org/reference/discover-movie) and [attribution](https://www.themoviedb.org/about/logos-attribution). Ratings and vote counts are saved at request time and may change.

Selection references: [Douban Top 250](https://movie.douban.com/top250) and [BFI Sight and Sound](https://www.bfi.org.uk/sight-and-sound/greatest-films-all-time). Douban references were checked in a web viewer, not scraped by the teaching notebook. Audience scores can change; BFI ranks refer to the stated 2022 poll.

Data sources: [Cinemetrics](https://cinemetrics.uchicago.edu/) and [Wikidata](https://www.wikidata.org/wiki/Wikidata:REST_API). Source material retains its original attribution and terms.

Codex assisted with code, source checks, debugging and replay verification. Logs identify assisted runs. The student still needs to review the final sample and complete the analysis. Earlier failures, including a missing early HTTP 429 body, remain documented in the historical review and process notes.
