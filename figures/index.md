# Final figure gallery

Source: saved Cinemetrics HTML and TMDB metadata collected 10–11 November 2026 (UTC).
The frozen sample contains 100 films, 20 per decade. Figures are exported at 300 dpi.

| Figure | What it shows | Interpretation |
| --- | --- | --- |
| [01](fig01.png) | Film ASL by release year and decade median | Log scale retains all 100 films and long-take extremes |
| [02](fig02.png) | Within-decade ASL distributions | Each decade has 20 films; flagged values may be valid |
| [03](fig03.png) | Adventure, Drama and Thriller ASL medians | Genre groups overlap; counts differ |
| [04](fig04.png) | Decade medians of film ASL and film MSL | Both series use the same selected film/page pairs |
| [05](fig05.png) | One page per film versus all passing pages | Repeated measurements change observation weights |
| [06](fig06.png) | Missing fields in the frozen sample | Denominator is 100 films; core completeness follows screening |
| [07](fig07.png) | Genre-label composition by decade | Percentages describe label assignments, not exclusive films |
| [08](fig08.png) | Apriori itemsets and archived timings at six thresholds | Axes have different units; timings are single-call measurements |
| [09](fig09.png) | Support, confidence and lift for 20 rules | Bubble area represents lift; overlapping rules are retained |
| [10](fig10.png) | Estimated MapReduce shuffle records and bytes | Local simulation estimates payload, not network traffic |
| [11](fig11.png) | Seventeen genres and 58 shared-film connections | Areas and widths encode counts; circle distances carry no statistical meaning |

Run `Film_Analysis.ipynb` to reproduce the charts. Figure 08 uses archived timings;
the notebook also displays fresh timings. Results describe this purposive sample.
