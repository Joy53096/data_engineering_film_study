# 2026-11-01 本轮真实过程记录（教学材料）

## 输入和失败

- 接手时本地只有作业 PDF；旧 ZIP 和原始采集清单不可用。
- 分享页的网页读取工具仅返回标题，没有可读正文。通过公开页面 HTML 中的序列化聊天内容读取原始用户背景及最终答复。
- 首次读取 PDF/聊天时，Windows 控制台默认 GBK 不能显示部分字符；调整输出编码为 UTF-8。没有把控制台编码错误当成网页缺字段。
- 旧域名 cinemetrics.lv 请求出现 SSL 错误，未关闭证书验证；随后依据分享聊天已经给出的新域名访问。
- 新目录静态 HTML 是空壳。使用浏览器正常搜索 193，等候异步结果稳定后记录第一页前三条实际链接。搜索切换期间曾短暂出现全库 24984 的旧计数，稳定后显示 1801；两者都不是核实后的年代电影数。

## 本轮执行

- 实际采集目录：01_raw/20261101T102603220414Z/。
- 采集器身份：助手辅助执行，尚无学生独立运行的证明。目录链接由助手观察浏览器取得。
- 真实记录的请求共 5 次，包括 robots、条款和三个详情页。此前探索请求不在此日志内；日志不是本次聊天全部网络活动的完整计数。
- robots 返回 404；条款是链接到的 OCHRE 软件许可文本。未将这些现象解释为批量采集许可，未点击接受协议，未作授权保证。
- 原始响应按字节保存，全部 SHA256 已重新计算并核对。
- 按原顺序执行 Notebook 全部 4 个代码格；默认离线模式下临时禁止网络调用，仍运行成功。未使用 Jupyter 内核执行器，验证方式为按序执行各代码格；学生仍需在自己的 Jupyter 中 Restart & Run All。
- 三页字段对照实际已读页面核验；第一条目录 MSL=6.9、详情页 MSL=6.8，保留差异，原因未知。
- 未核实电影身份、原始年份、语言/国家、类型、播放速度、版本及片头片尾边界；三条均不进入主分析。

## 本轮不作的声明

没有把本轮 3 条加到历史 32/51 条；没有全站覆盖结论、研究趋势结论、最终样本范围或课程规模达标声明。

## 学生继续记录（由本人填写）

- 自己实际运行的时间与环境：
- 自己网页抽查发现了什么：
- 是否遇到错误、如何修正：
- 哪些 AI 输出经过核验或调整：

以上是过程事实记录与填写提示，不是替学生撰写的反思报告正文。

## 实际运行环境

Python 3.13.4；requests 2.32.5；beautifulsoup4 4.14.3。

## 接续：身份核验与规模澄清（2026-11-01）

- 用户要求仅主线必要文件留在 CW1；本轮只更新现有 Notebook、核查表、计划与这一份过程记录，不另建脚本、报告或重复结果表。
- 人工核读 Filmový přehled 的页面索引内容，按原片名、1935 首映年和导演匹配三条测量；Osudná chvíle 的国家、类型、年份、片长另获 NFA 可直接读取页面交叉核对。
- 部分 Filmový přehled 直接打开返回 403；未绕过限制。Notebook 逐条说明索引/直接读取来源，不把人工核读伪装成 API 调用或 requests 成功日志。
- 三片参考片长分别 87、80、89 分钟；被测时长均更短。差异原因未知，不据此猜测播放速度、剪辑版本或判定片段。身份已匹配与测量完整性未核验分别存储。
- 书面数量重新核读 PDF 第2页 A1—A4：HTML至少200页；原页证据至少20页；双通道合并至少2000条、10字段、一个至少50字符文本字段、两个数值字段。三个详情页只是试采，尚无API合并，不达标。
- 身份来源字段直接嵌入原 Notebook，使离线重跑不会把核验结果永久改回 pending。前面采集格先生成待核表，最后核验格更新同一文件。

- 接续验证通过：默认离线模式下按顺序执行全部5个代码格，并禁止网络；最终核查表保留3条身份匹配，版本/速度/边界仍空，纳入标记均为False；原始证据哈希未变化。验证采用按序执行代码格，未使用Jupyter内核执行器。

## 2026-11-06：课件对应与录制练习准备

- 用户提供本地 Week2—7 六份 PDF。核读各份目录与 Week4 采集部分，确认第15页示例为 JSONPlaceholder /posts/1，第21—29页使用 Fake Python Jobs 与 requests/BeautifulSoup。
- 为避免 CW1 混入无关测试数据，只在课件目录下新建一个 demo Notebook，未把课堂测试响应、临时脚本或练习数据加入 CW1。
- 演示共5个短代码格：导入、API请求、JSON字段读取、HTML请求、HTML结构定位；两次GET响应均200，提取到帖子id=1、首条职位和公司，并按页面/官方示例核查。
- 助手按顺序执行代码格，保存真实测试输出；未在学生的Jupyter内核执行，未录制视频，尚无学生自行运行的证明。
- 原电影项目的3页试采、API未合并状态未因课堂练习改变。CW1内仅更新现有计划和此连续记录。

## 2026-11-06: English single-film dual-channel notebook

- The user requested the same film in both channels and English notebook content. Created 02_single_film_dual_channel_demo.ipynb for the main demonstration.
- Exploratory title searches did not reliably match the earlier Czech-film candidates. Intolerance was found through a public Cinemetrics detail result and a Wikidata search, then checked by exact IMDb ID tt0006864, title and year. No uncertain candidate was forced into a match.
- The demo acquires metadata using the documented Wikidata REST API. An earlier Action API search only found the starting candidate ID, outside the recorded two-request workflow.
- Two live response bodies, a received-response log and one linked record were saved. Published ASL/MSL were extracted, not newly computed as research metrics. Edition, speed and boundary checks remain pending.
- All 7 code cells passed in a fresh Jupyter kernel. Both live requests returned 200. Replay passed in a separate fresh kernel with network calls rejected; original evidence and linked output were unchanged. Response hashes, notebook format and absence of Chinese notebook text were checked.
- Notebook authoring initially failed before file creation because of Windows path escaping; forward-slash paths fixed it. A validation harness initially treated notebook source as a list; reading through nbformat.reads fixed that harness. Neither issue changed source data. No temporary authoring scripts were retained in CW1.
- Recommended video allocation is 2 minutes out of 10; it is a planning suggestion, not a course rule. The student has not yet executed or recorded this demonstration.

## 2026-11-07: Switch the existing English demo to Titanic (1997)

- User requested a familiar film such as The Odyssey or Titanic. Selected the requested Titanic example after verifying both channels; did not assume newer films had measurement coverage.
- Browser directory inspection timed out twice. Switched to public HTTP sources. The database HTML references /_next/static/chunks/08y3_m-grp-_d.js, which publishes its read-only OCHRE search request and query structure. Reproduced the site's limited directory search through that endpoint, preserving its scope and 50-result first-page limit; no unrestricted query or bulk download was performed.
- Search Titanic returned 6 measurements across 1943, 1953, and 1997. Chose the 1997 James Cameron row with an IMDb link and contributor boundary notes: 0e9a80c6-ce7f-45b3-976b-6211e51bd19b. Title/year/director distinguish it from other Titanic films. This is a teaching choice, not a final analytical selection.
- Search odyssey returned 11 records referring to other works, with no corresponding Nolan film identified in this search. This does not prove the site has no such data outside this search or at later dates.
- REST item Q44578 returned Titanic, James Cameron description, IMDb tt0120338, and regional publication years 1997/1998. Both years were retained; no arbitrary date was substituted.
- Updated the existing notebook and current linked JSON; did not create another notebook copy. Previous raw evidence remains intact. The current Titanic cache is separate from the retired Intolerance cache.
- Both fresh-kernel live requests returned 200; exact IMDb, title and supported-year checks passed. Fresh-kernel replay with all network requests blocked also passed. The saved record stayed unchanged during replay; raw-response hashes and English notebook content were verified. Film measurement validity remains pending.

## 2026-11-07: Short presentation notebook

Moved the current demo to Titanic_Demo.ipynb at the CW1 root. Direct deletion was rejected by automatic review, so the planning folder containing only next_steps.md was removed using the recoverable Windows Recycle Bin. Reduced notebook Markdown from 1402 to 222 words; removed video/assignment planning tables. All seven code cells and validated outputs remain. Notebook format, code syntax, English content and raw paths checked. No new network requests were needed.

## 2026-11-07: Debugged the user's active Jupyter session

The saved last cell showed NameError with execution count 1. Connected to the local Jupyter server and the existing Titanic kernel; api_record, html_record and api_data were absent from that kernel. Earlier displayed results were saved outputs, not current variables.

Renamed variables to folder, live, page, reply, item, html_data, api_data and film; shortened helper parameter names. Added a Run All Cells hint and a final-cell prerequisite check. Kept English notes brief and removed the trailing empty cell. A temporary renaming check corrected header keyword/attribute references before execution.

Executed all seven cells in the user's existing kernel (In[2] through In[8]), with two successful live requests and an exact tt0120338 match. Saved code and new outputs through Jupyter's Contents API. Verified the saved notebook has no error outputs, the order hint is clear, and response hashes match. Original notebook backup is outside the project in the system temporary directory. The user's browser may need reloading to display the saved revision.

## 2026-11-07: Lowercase configuration names

Renamed the eight uppercase configuration variables and all references in Titanic_Demo.ipynb. request_headers avoids colliding with the parsed HTML headings. Kept interface field names and source values unchanged. Executed all seven code cells through the existing Jupyter kernel and saved the new outputs through the server. Both live requests and the identity checks passed. Reload the browser notebook to display the saved revision and avoid resaving its previous in-memory copy.

## 2026-11-08: Shorter film demo

Rebuilt Titanic_Demo.ipynb as five code cells: setup, request/save function, HTML fields, API fields, and match/combine. Non-empty code lines decreased from 150 to 86. Removed repeated response handling, extra prints and unused director/genre/country ID lists from the displayed record. Full metadata remains in the raw API response. Fixed a truncated HTML request line in the saved notebook during the rewrite.

Retained separate HTML and REST sources, published shot statistics, title/year/IMDb checks, raw responses, a received-response log, timeout, delay and optional replay. The simplified helper parses API bytes with json.loads. No automatic retry/backoff was added. Both live requests returned 200 in a fresh Jupyter kernel; network-disabled replay passed without modifying saved files. This remains a small acquisition demo, not a completed bulk collector or analytical sample.


## 2026-11-08: First five-decade coverage probe

- The user preferred a staged compromise rather than immediately collecting 2,000 films. Proposed a collection budget of 200 verified films (about 40 per decade), with a possible 100-film intermediate stage. These are suggestions, not a frozen analytical sample or confirmation of compliance. A4 still specifies 2,000 merged records; the user reports oral flexibility, and no teacher confirmation about counting shot-level rows was supplied.
- Provisional window is 1950 <= page year < 2000. Country/genre inclusion and final sample rules remain to be decided before looking at trend results. No country scope was selected because it produced a desired effect.
- Created the mainline Film_Collection.ipynb, leaving Titanic_Demo.ipynb unchanged. No planning documents or extra authoring scripts were added to CW1.
- Reviewed the site's linked OCHRE software terms. Both hosts' robots.txt endpoints returned 404; this is not affirmative permission. Preserved those responses, the terms page and the public directory client script in the raw run. Used the public client's read-only directory query structure, exact integer directory-year conditions, and its 50-row first-page limit; request bodies are logged. This is a convenience coverage probe, not a representative sampling frame.
- Retrieved five catalog response pages and 25 candidate detail HTML pages (five per decade). Exact title/year/director labels were deduplicated within each decade; this does not establish distinct film identities. Directory measurement counts were 1616, 1769, 1473, 1367 and 2307. These counts include repeated measurements and ineligible works; they are not verified film counts.
- The live run logged 35 attempts: 32 HTTP 200 responses, two expected robots HTTP 404 responses, and one ReadTimeout followed by a successful retry. Used a declared User-Agent, sequential requests, 1.2-second pauses, connect/read timeouts, bounded retries and exponential backoff. Retry response filenames are separate, and every logged response SHA256 matched its saved file.
- All 25 candidate pages parsed the four overall measurement fields. Only seven included IMDb links. All candidates remain pending for identity, full-film scope, edition/speed and metadata linkage. No main-analysis rows are approved. Comments explicitly flag first-30-minute measurements for Ugestu and Stalker, and a volleyball-scene measurement for Top Gun. Differently labelled Xiao Wu measurements and Now records also require identity review. These observations are not a completed exclusion decision or trend result.
- The external execution progress printer hit a Windows GBK UnicodeEncodeError after live acquisition completed. Raw collection was intact. Rebuilt the intake from saved responses with networking disabled, then executed all six notebook code cells in a fresh Jupyter kernel with network requests blocked. Replay passed and did not change any raw responses, logs or intake files. Default collect=False avoids new requests on review; the displayed mode states saved responses.
- Saved current intake to 02_audit/decade_intake.json and an immutable-by-workflow copy in the raw run. Wikidata/Wikipedia enrichment, verified film deduplication, the final sampling frame and full-film eligibility checks remain pending. No trend plots, analysis conclusions, MapReduce implementation or report paragraphs were generated.


## 2026-11-09: Identity review and source enrichment for the five-decade probe

- Continued the user's requested next step in the existing Film_Collection.ipynb. The Titanic video demo was not changed, and no planning documents or new notebook copies were created.
- Reused the saved 25-page intake and successful logged API responses after the earlier process interruption. The raw review folder name retains the original UTC start ID; actual per-request timestamps show the later resumption. The resume check validates both URL and response hash, so a cached filename alone is insufficient.
- Used documented Wikidata label/alias search and bounded full-text search for candidate discovery. External-ID searches use haswbstatement:P345=... as documented by Wikidata. Retrieved 28 candidate items through the Wikibase REST API, then resolved director/country/genre names through batched Action API requests. Candidate items include rejected same-title works; they are not 28 verified films. Search cursors and request parameters remain in raw responses/logged URLs. Bounded searches do not establish absence from Wikidata.
- Twelve candidate measurement records obtained identity support: six by a shared IMDb ID and supported page year, and six by source title, supported page year and director-name evidence. Thirteen remain pending. Country and genre values are available for all twelve supported identities. Original country labels are retained alongside all API production-country values; multiple release years and runtime quantities are not reduced to one convenient value. Possible spelling corrections remain pending instead of silently changing source titles.
- Three contributor comments explicitly identify excerpt measurements: Ugestu (first 30 minutes), Stalker (first 30 minutes) and Top Gun (volleyball scene). Twenty-two other measurements remain scope-unverified. Two possible duplicate pairs (Now and Xiao Wu) are flagged for review and not merged. These quality flags overlap the identity categories; they are not disjoint sample counts. No measurement is selected for the main analysis.
- Added a readable review table, a country/genre enrichment view, and a Top Gun scope example for video use. The Top Gun record measures 01:16.9, the comment names the volleyball scene, and the linked API runtime is 109 minutes. Source duration and API runtime remain separate fields; no universal duration threshold or final eligibility rule was selected.
- The review request log contains 70 attempts: 64 HTTP 200, two HTTP 429, one interrupted attempt without a recorded result, two ConnectionError outcomes and one ReadTimeout. Requests were sequential; later API spacing is five seconds and numeric Retry-After instructions are honored within the bounded retry policy. Cached reuse is not counted as a new HTTP request.
- Fixed a real raw-evidence bug: the early retry helper replaced the first failed body's canonical filename with a successful retry cache alias. One early HTTP 429 body is therefore unavailable; its original log is retained and the defect is explicitly listed in film_review.json/evidence_issues. All 64 successful response bodies match their logged hashes. Later received responses use unique timestamped attempt files, with a separate cache alias, including the later 429 response. The historical missing body was not reconstructed or claimed as preserved.
- English Wikipedia introduction acquisition failed after three logged connection/timeout attempts. Saved a derived text_unavailable.json failure record; it is not an API response. Text remains missing, and replay reports this unavailable state. No generated synopsis was inserted. This does not complete the long-text field or later TF-IDF work.
- All twelve notebook code cells passed in a fresh Jupyter kernel with network requests blocked. The recomputed review exactly matched the saved audit. All saved raw sources, logs and audit files remained unchanged during replay. Both collection switches default to False. New API requests, analysis charts, MapReduce code, core evaluation code and report paragraphs were not generated during verification.
- The video/report framing requested by the user is a staged process: one-film method test, five-decade quality probe, then a larger documented sample. The final response supplies a timed video outline and report prompts, rather than additional project-planning files. Proposed 100/200-film budgets remain future targets, not achieved sample sizes or a claim of meeting the written 2,000-record floor.


## 2026-11-09: First Git-ready project snapshot

- User requested the files that can be committed now. Added an English README, pinned direct dependencies, Git ignore rules and Git attributes. Retained the current two main notebooks and their complete replay evidence. Older experiments, retired demo runs, course material, notebook checkpoints, local environments and recording/submission archives remain on disk but are ignored.
- Replaced the two hardcoded project paths with Path.cwd() and an explicit project-root check. Both notebooks now default to saved responses; the README describes how to request live data. No new collection requests were made for packaging.
- Added Git attributes that preserve exact response and audit bytes instead of converting their line endings. Other source files use LF line endings in Git.
- Initialized a local main branch. Git author identity was supplied explicitly by the user and configured for this repository only. No remote repository or GitHub upload was configured in this step.
- Verified the direct dependency versions in the actual Python 3.13.4 Jupyter kernel: requests 2.32.5, beautifulsoup4 4.14.3, pandas 2.3.3, jupyterlab 4.5.6 and ipykernel 7.2.0. This checked the installed environment; it was not a separate clean-environment installation.
- Exported only the Git-staged files to a different temporary directory and executed both notebooks in fresh Jupyter kernels with network access blocked. All five Titanic code cells and twelve collection code cells passed. Recomputed records matched the saved audits; no final-analysis sample was approved. All exported raw responses and audit bytes matched the source files, and replay left them unchanged. Saved the validated outputs back into the two main notebooks.
- The initial snapshot contains 160 files, approximately 28.53 MiB, including the current raw evidence. A targeted staged-text check found no local Jupyter session-token URL or bearer-token value. Course PDFs, legacy notebooks and checkpoint files were confirmed absent from the snapshot. Existing missing article text and the historical failed-response defect remain documented rather than hidden.
- This is the first actual Git version. Earlier process notes and request timestamps are retained as source history; no earlier commits were fabricated. GitHub publication is a separate next step requiring a destination repository.


## 2026-11-09: Shorter collector and familiar, rank-referenced film candidates

- User requested a core, classroom-level Film Collection notebook and better-known films. Replaced the 478 non-empty code lines with 150 lines in six code cells. The current notebook uses requests, BeautifulSoup, Python loops/dictionaries, JSON and pandas. Removed the runnable directory-query engine, automatic title discovery, alias/fuzzy matching, resume machinery and optional article acquisition. No external Python helper module replaces those removed parts. The previous implementation remains in the first Git commit.
- Added film_list.json as an editable data input: 25 familiar candidates, five per decade from the 1950s through the 1990s. Twenty-three reference publicly viewed Douban Top 250 entries; The Apartment and Taxi Driver reference the BFI Sight and Sound 2022 critics' poll. Recorded each source, reference rank, audience rating where available, URL and check date. BFI ranks and Douban audience scores are not combined. This is a purposive starter list, not a random or representative sample, and shot-length outcomes were not used to choose titles.
- Ranking references were checked through the web viewer. An attempted temporary reference-helper creation was rejected by automatic execution review without a detailed reason; no helper was created. Used read-only ranking references and separate logged film-source discovery instead. IMDb's chart was inaccessible, and Douban subject-page attempts redirected to a security page; those restrictions were not bypassed.
- Found page links for 22 candidates in bounded title/year checks against the public directory. Witness for the Prosecution, La Grande Vadrouille and Nezha Conquers the Dragon King remain pending. This is not proof that no corresponding record exists. Discovery queries/responses are retained separately under ranked_films/selection; the teaching notebook starts from the curated public links. A later exploratory broader lookup timed out before producing a response and is not represented as a successful acquisition.
- The initial Wikidata sitelink lookup returned a missing entry for the supplied 12 Angry Men page title. A discovery parser initially assumed every entry had an id; preserved the response, checked the missing-entry case and used the documented label search. Q2345 was supported by its 1957 Sidney Lumet description. Did not merge the 1997 TV film or a same-title play.
- Kept timeout, sequential five-second pauses, bounded retries with exponential backoff and Retry-After handling, separate received-response files, raw cache files and a structured SHA256 log. Kept direct REST retrieval and batched readable labels for country, director and genre IDs. The shorter collector has no final-sample approval rule or chosen runtime cutoff.
- Executed the new collector in a fresh Jupyter kernel: 22 HTML pages, 22 REST film items and two related-label batches, all 46 HTTP responses returned 200. All received-response hashes matched. Ten candidate records passed the shared-IMDb-plus-year check; twelve stayed marked for review. Three comments triggered a possible-excerpt flag; all other boundaries also remain under review. These flags overlap, and none of the 22 records is selected for the main analysis.
- Saved new outputs to 02_audit/ranked_films.json and a run-local records.json. Older audits, raw evidence and the Titanic demo were left intact. Retained the earlier Top Gun scene example as a short saved example at the end of the notebook. Article text and final-sample work remain pending.
- All six code cells passed again in a fresh kernel with HTTP requests blocked. The recomputed result exactly matched the saved audit; raw responses and audit files were unchanged. The default remains live=False. Updated the README for the new input file and single live/replay switch.


## 2026-11-10: TMDB connection test

- The student obtained a TMDB API Read Access Token and saved it in the ignored local .env file. The credential was not displayed or included in request logs.
- Sent one authenticated GET request to /3/movie/597, using the TMDB ID in the saved Titanic Wikidata response. HTTP 200 returned Titanic (1997), with IMDb ID tt0120338. Ratings, vote count and runtime were present.
- Saved the response and a request log in 01_raw/tmdb_check/20261110T080131389935Z/. Checked the saved response hash. This is a connection test, not a new decade sample. The notebooks and final sampling rules were not changed.


## 2026-11-10: TMDB five-decade candidate check

- Added Film_Selection.ipynb as a mainline selection step, separate from the short Titanic demo and the existing HTML/API collector. It has four code cells and 105 non-empty code lines, using requests, JSON, loops and pandas. Its default is live=False.
- Read page 1 of discover/movie for each decade from 1950 to 1999, sorted by vote_count.desc. The five sequential requests returned HTTP 200 and 20 records each: 100 distinct TMDB IDs. Date bounds, numeric rating fields, sort order and duplicate IDs passed the collection checks. No blank overview was found on these pages.
- No rating, vote-count, country or genre cutoff was set. Adult and video results were excluded through the API flags. These are high-vote first-page candidates, not a random sample, a final classics list or 100 verified whole-film Cinemetrics records. The existing 25-film pilot was not replaced.
- All five API responses reported total_results=20001 and total_pages=1001. Preserved those values as received, but did not treat them as verified decade totals or coverage estimates. Only the 100 returned records count as collected candidate data.
- The original-language field covers several languages overall, but every returned 1970s record uses English. Language is not production country, and this check does not establish geographic coverage. More rows from the same ordering would not by itself remove selection bias.
- Saved exact response bytes, per-attempt hashes, non-secret request logs and the derived candidate JSON. The local token was read only for live requests and was absent from saved outputs and logs. Added TMDB credit, its logo link and the required notice.
- Ran all four cells in a fresh Jupyter kernel with HTTP blocked. The recomputed candidates exactly matched the saved audit, no token was read in replay, and raw/audit bytes were unchanged. Final sampling parameters, Cinemetrics coverage, full-film boundaries and later analysis remain for review.


## 2026-11-10: Move the window and screen measurement scope

- The student changed the main window to 1970-2019 and confirmed TMDB rating >= 7.0, vote count >= 1,000, vote-count ordering and a measured-duration / reference-runtime band of 0.90-1.10 for initial screening. Later confirmed a working target of 20 passing films per decade (100 total). These choices were made before any decade-trend analysis.
- Collected 100 vote-ranked candidates, 20 per decade, with movie details and director credits. The active TMDB run contains 205 HTTP 200 responses; temporary network failures remain logged. A preceding aborted run has three ConnectTimeout outcomes. Direct access failed after local proxy settings were unavailable; the existing local proxy worked. Added an optional HTTPS_PROXY entry to the ignored local .env file without changing system settings. Separate unauthenticated /configuration diagnostics are not counted as collection successes or token failures.
- Used bounded public-directory title/decade lookups, including the second 1990s result page. The directory returned 255 distinct measurement links. Two rows had a candidate-year conflict and were deferred, leaving 253 pages for 80 distinct candidate films. Policy checks returned two unavailable robots files (404) and the linked OCHRE software terms (200); no blanket scraping permission or accepted agreement is claimed. Directory queries and source-policy responses are retained separately.
- All 253 HTML pages returned HTTP 200 and parsed successfully after six logged temporary network failures. Saved received bodies, hashes, cache copies and logs. Matched identity by shared IMDb ID/year, or exact title/year and a shared director name; unmatched identities remain pending.
- Applied duration, positive/finite-number, partial-wording and source-accuracy screens. Generic mentions of scenes in whole-film breakdown comments are not sufficient by themselves to reject a measurement. Source wording includes real first-30-minute, first-hour and sub-minute scene examples.
- Seventy-eight measurements passed the recorded initial checks, covering 54 films (13,13,8,11,9 by decade). Chose one passing measurement per film by closest reference runtime, then page ID for a fixed tie-break. Preserved every alternative and rejection reason. This is a provisional working sample under operational checks; source editions and playback speeds were not independently verified. It is not a claim of complete final quality audit or meeting the written 2,000-record floor.
- Moved the quality gate into the per-page loop, before passing-film counts. Generated data_passport.json with active run windows, request outcomes, units and a field dictionary. The missingness/outlier/controlled-impact analysis modules still remain for the student.
- Simplified the active selection and collection notebooks to five code cells each. The metadata loop reads details and director credits together. The Titanic demo was unchanged. Fresh-kernel replays with HTTP blocked passed for both notebooks; selected page IDs were stable, audits matched and original response bytes/hashes remained unchanged. No token appears in stored responses, notebook output or logs.
- The student reported a November 17 deadline. Prioritise the required pipeline and use November 16 as the intended packaging/video completion buffer; no optional models or extra data platforms were added.
