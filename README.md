# Film shot lengths, 1970–2019

This project collects shot statistics from Cinemetrics and metadata from Wikidata. TMDB provides ratings and vote counts for checking a larger candidate pool. It explores changes across decades and genres, and whether average and median shot lengths tell the same story.

The main candidate pool now covers 1970–2019. It uses TMDB ratings and vote counts, with the same cutoffs in every decade. A vote-ranked candidate list is purposive, so later results will describe selected films rather than all cinema. Earlier 1950–1999 files remain as pilot evidence.

## Current stage

- The Titanic demo shows one HTML/API match.
- `Film_Selection.ipynb` collects one TMDB page per decade from 1970 to 2019, then requests film details. The student confirmed rating >= 7.0 and vote count >= 1,000. Identity and full-film measurement checks remain pending.
- The earlier `film_list.json` contains 25 familiar 1950–1999 pilot candidates. It is not the new main sample.
- Twenty-three titles refer to Douban Top 250; two use the BFI Sight and Sound 2022 critics' list. The source, rank, audience score where available, and check date are recorded separately. These measures are not combined.
- The earlier 25-film pilot found links for 22 titles. Its files and review flags remain separate from the new candidate pool.
- The current batch contains 253 parsed HTML measurements for 80 of the 100 candidates. After recorded identity/duration/source checks and one-per-film selection, 54 films form a provisional working sample. No decade trend is claimed. The project remains below the written 2,000-record requirement.

## Main files

| File or folder | Purpose |
| --- | --- |
| `Titanic_Demo.ipynb` | Short one-film walkthrough |
| `Film_Selection.ipynb` | Collect 1970–2019 candidates with confirmed rating/vote cutoffs and film details |
| `Film_Collection.ipynb` | Fetch Cinemetrics measurement pages and join the current TMDB candidates |
| `film_list.json` | Earlier pilot titles, source links, item IDs and ranking references |
| `01_raw/ranked_films/` | Earlier 25-film pilot responses and logs |
| `01_raw/candidate_links/` | Directory lookups and candidate-page link checks |
| `01_raw/film_measurements/` | Current HTML responses, input snapshot and logs |
| `01_raw/tmdb_candidates/` | TMDB candidate responses and request logs |
| `02_audit/tmdb_candidates.json` | The current TMDB candidates, film details and collection checks |
| `02_audit/ranked_films.json` | Earlier 25-film pilot output |
| `02_audit/film_measurements.json` | Current HTML/API measurement records and review flags |
| `data_passport.json` | Active collection window, request outcomes, units and field dictionary |
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

All three notebooks default to `live = False`, which reads saved responses. Set `live = True` for new requests. After editing the film list, collect a new batch before replaying it. A live run creates a new folder and saves raw responses and a request log. Keep each complete run folder together with its `latest_run.txt` pointer when committing evidence. The current order is `Film_Selection.ipynb` then `Film_Collection.ipynb`; the Titanic demo is a separate walkthrough.

The HTML collector reads a saved, reviewed directory-link input. Exact-title directory lookups are a discovery step; title/year matches do not alone approve identity. A failed lookup does not prove that Cinemetrics has no measurement. Repeat measurements are retained as separate records for review. The shorter teaching notebook does not contain the directory-query engine.

## Collection standard

| Item | Rule |
| --- | --- |
| Window | 1970-01-01 through 2019-12-31, grouped into five decades |
| Rating source | TMDB; do not mix Douban or IMDb scores into this cutoff |
| Rating cutoff | At least 7.0, confirmed by the student |
| Vote cutoff | At least 1,000 ratings, confirmed by the student |
| Candidate order | Vote count descending, using the same query in every decade |
| Current request budget | One page / up to 20 candidates per decade; this is not a final sample quota |
| Country and genre | No restrictions; retain all production countries and genre names |
| Eligible film scope | Feature films; exclude TV episodes, shorts, clips and excerpt measurements |
| Required match | Shared IMDb ID and year, or a documented manual title/year/director check |
| Duration screen | Measured seconds / (TMDB runtime minutes * 60) from 0.90 through 1.10, confirmed by the student |
| Shot measurements | Require supported identity, positive finite fields, no clear partial wording and no source accuracy warning |
| Duplicates | One film in the working table: choose the passing measurement closest to reference runtime, then page ID for a fixed tie-break; keep all alternatives |
| Missing or unclear evidence | Keep pending; do not invent shot data or silently replace a failed title |

Screen ratings and vote counts from the saved discovery response. Keep detail-response values separately if they differ. Both describe the request-time data. No film is selected by its average shot length or whether it supports a decade trend. These rules are applied to each measurement before counting it in the working sample and before trend analysis. A duration over one hour alone does not establish a whole film. Rejected records keep their reasons; replacements should follow the same vote-ranked candidate order. A final whole-dataset audit is still needed. Future rule changes must be recorded.

Run `Film_Selection.ipynb` to read the saved candidate pool and film details. Its default is `live = False`, which does not need a token. For new requests, use a local `.env` file containing `TMDB_READ_TOKEN=your_token` and set `live = True`. Never print the token or request headers. `.env` is ignored by Git. If your network needs a proxy, add an optional `HTTPS_PROXY` URL to that local file; the collector uses it only for requests.

The candidate pool comes from the first page ordered by vote count. English labels and original language do not establish production country. Date, rating and vote checks do not prove that a film has usable Cinemetrics data. The first screened working sample contains 54 films (13, 13, 8, 11 and 9 by decade). It is provisional: source editions and playback speed were not independently verified. Final sample size is not yet fixed. Earlier runs remain in their dated raw folders; only the latest pointer identifies the active candidate run.

## What the collector keeps

HTML: title, year, IMDb links, shot count, measured duration, ASL, MSL and contributor comment.

API: TMDB IMDb ID, release date, runtime, all production countries, genre names, overview, rating and vote count. Discovery and detail values are retained separately when they can change. Wikidata remains the API source for the Titanic demo and earlier pilots. The published shot statistics are read from the HTML source.

Identity uses a shared IMDb ID and year, or exact title/year plus a shared director name. Other records stay marked for review. Identity alone does not establish full-film measurement. The working sample uses the recorded duration and source-wording screens; edition and playback uncertainty remain explicit limitations. The current pool includes TMDB overviews for later text work; that analysis has not started. The earlier Top Gun excerpt remains documented in the pilot audit and Git history.

## Sources and assistance

<a href="https://www.themoviedb.org"><img src="https://www.themoviedb.org/assets/2/v4/logos/v2/blue_short-8e7b30f73a4020692ccca9c88bafe5dcb6f8a62a4c6bc55cd9ba82bb2cd95f6c.svg" width="120" alt="TMDB"></a>

This product uses the TMDB API but is not endorsed or certified by TMDB.

TMDB sources: [Discover API](https://developer.themoviedb.org/reference/discover-movie) and [attribution](https://www.themoviedb.org/about/logos-attribution). Ratings and vote counts are saved at request time and may change.

Selection references: [Douban Top 250](https://movie.douban.com/top250) and [BFI Sight and Sound](https://www.bfi.org.uk/sight-and-sound/greatest-films-all-time). Douban references were checked in a web viewer, not scraped by the teaching notebook. Audience scores can change; BFI ranks refer to the stated 2022 poll.

Data sources: [Cinemetrics](https://cinemetrics.uchicago.edu/) and [Wikidata](https://www.wikidata.org/wiki/Wikidata:REST_API). Source material retains its original attribution and terms.

Codex assisted with code, source checks, debugging and replay verification. Logs identify assisted runs. The student still needs to review the final sample and complete the analysis. Earlier failures, including a missing early HTTP 429 body, remain documented in the historical review and process notes.
