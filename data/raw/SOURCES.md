# Data sources (approved sites only)

| File | What it holds | Source |
|---|---|---|
| `tsdl_match_table_raw.csv` | 103 matches (72 group stage + 31 knockout): date, teams, score, goals by half, cards, corners by half, xG, shots, shots on target, fouls, for both teams | The Stats Don't Lie - World Cup 2026 page, "Fixtures / Results / Match Stats" table. The site embeds it from a published Google Sheet (gid=995472238, ranges A1:AB75 and A76:AB121): https://www.thestatsdontlie.com/football/world-cup-2026/ |
| `fifa_third_place_playoff.csv` | The 104th match (third-place play-off), final score only | FIFA Official Website, match centre: https://www.fifa.com/en/match-centre/match/17/285023/289291/400021542 |

Notes
- The Stats Don't Lie table does NOT contain the third-place play-off, which is why it comes from FIFA.
- The FIFA statistics page (/statistics) shows tournament-total leaderboards, not match-by-match data, so it is not used for pre-match variables (totals would include the match being predicted).
- FBref: the World Cup 2026 section could not be read in the tool used; it is not used.
- Scores include extra time. A "p" next to a score marks the side that won the penalty shoot-out; shoot-outs are NOT counted, so those matches have goal_diff = 0.
- Values were read from the live page, saved, then checked against per-row checksums calculated in the page and against a separate raw file in the group repo (Dorjee/data/raw/Rawdata.csv). One typing error was found and fixed (Panama v Croatia, yellow cards).
