# ICC T20 Men's World Cup 2024 – Player Performance Analysis

**Tools:** Power BI, DAX  
**Domain:** Sports Analytics | Player Segmentation | Performance Metrics  
**Portfolio:** [mg67.vercel.app](https://mg67.vercel.app/) | **GitHub:** [Mg6700](https://github.com/Mg6700)

---

## Project Overview

This project builds a comprehensive player performance analysis system for the ICC T20 Men's World Cup 2024. Rather than relying on surface-level statistics (runs, wickets), the dashboard introduces role-based performance segmentation and composite DAX metrics to evaluate players the way professional selectors think — by role, by phase of play, and by consistency across Group Stage and Super Eight matches.

The flagship feature is an interactive **Final XI selector** — a tool that lets users pick any combination of players from the full tournament pool and instantly view the combined team's batting and bowling strength metrics.

---

## Dashboard Preview

> **Page 1 — Final XI Builder:** Select players from the full tournament list, assign batting order, view combined team strength  
> **Page 2 — Openers Analysis:** Top openers ranked by Runs, Average, Strike Rate, Boundary %  
> **Page 3 — Middle Order Analysis:** Middle-order batsmen comparison with scatter plots  
> **Page 4 — All-Rounders Analysis:** Dual batting + bowling metric view  
> **Page 5 — Finishers Analysis:** Lower-order impact players by strike rate and boundary %  
> **Page 6 — Bowlers Analysis:** Wickets, Economy, Bowling Strike Rate, Dot Ball % comparison  

---

## Dataset

| Field | Description |
|---|---|
| PlayerName | Full player name |
| Team | Country |
| BattingStyle | Right/Left hand bat |
| PlayingRole | Batsman / WK-Batsman / All-Rounder |
| BowlingStyle | Bowling style (for bowlers and all-rounders) |
| Innings Batted / Bowled | Matches participated in each role |
| Runs, Balls Faced | Core batting data |
| Average, Strike Rate | Calculated batting KPIs |
| Highest Score | Personal best in the tournament |
| Boundary % | % of runs scored via boundaries |
| Wickets, Balls Bowled | Core bowling data |
| Economy, Bowling Average, Bowling Strike Rate | Calculated bowling KPIs |
| Best Bowling | Best figures in a single innings |
| Dot Ball % | % of balls bowled as dot balls |

**Coverage:** 50+ matches | Group Stage + Super Eight | All participating nations

---

## Role-Based Performance Framework

The core analytical framework segments all players into 5 roles, each evaluated on role-relevant metrics:

| Role | Primary Metrics | Key Context |
|---|---|---|
| Openers | Runs, Average, Strike Rate, Boundary % | Must score fast in powerplay |
| Middle Order | Average, Strike Rate, Highest Score | Stability + acceleration |
| All-Rounders | Runs + Wickets combined, both averages | Dual value assessment |
| Finishers | Strike Rate, Boundary %, Batting Position | Death-over impact |
| Bowlers | Wickets, Economy, Dot Ball %, Bowling SR | Control + wicket-taking |

---

## Key Findings

**Top Openers**

| Player | Team | Runs | Average | Strike Rate | Boundary % |
|---|---|---|---|---|---|
| Rohit Sharma | India | 257 | 36.71 | 156.71 | 72.37 |
| Travis Head | Australia | 255 | 42.50 | 158.39 | 76.08 |
| Quinton de Kock | South Africa | 243 | 27.00 | 140.46 | 66.67 |

**Top All-Rounders**

| Player | Team | Runs | SR | Wickets | Economy |
|---|---|---|---|---|---|
| Hardik Pandya | India | 144 | 151.58 | 11 | 7.64 |
| Andre Russell | West Indies | 78 | 165.96 | 11 | 6.99 |
| Axar Patel | India | 92 | 139.39 | 9 | 7.86 |

**Top Bowlers**

| Player | Team | Wickets | Economy | Dot Ball % | Best |
|---|---|---|---|---|---|
| Fazalhaq Farooqi | Afghanistan | 17 | 6.32 | 56.58 | 5/9 |
| Jasprit Bumrah | India | 15 | 4.18 | 61.80 | 3/7 |
| Trent Boult | New Zealand | 9 | 3.69 | 65.63 | 3/16 |

**Notable Insight:** Jasprit Bumrah's economy of 4.18 with 61.8% dot balls makes him statistically the most dominant bowler of the tournament — the scatter plot of Economy vs Bowling Strike Rate places him as a clear outlier from the rest of the field.

---

## Dashboard Features

### Final XI Builder
- Search and select any player from the full tournament pool
- Assign custom batting order positions
- View real-time combined team metrics: Total Runs, Average, Strike Rate, Wickets, Economy, Bowling Average

### Role Pages (Openers / Middle Order / All-Rounders / Finishers / Bowlers)
- Data table with all relevant role-specific statistics
- Toggle between **Group Stage** and **Super Eight** performance
- **Dual line charts** showing Runs/Average and Strike Rate/Boundary % trends across matches
- **Scatter plot:** Average vs Strike Rate (batting roles) or Economy vs Bowling Strike Rate (bowling roles) — sized by Runs/Wickets for impact weighting
- Multi-select player comparison: click any player name to isolate or compare their stats in the scatter and trend charts

---

## Custom DAX Measures

```dax
-- Boundary % (runs from boundaries as % of total runs)
Boundary % = DIVIDE([Boundary Runs], [Total Runs], 0) * 100

-- Dot Ball %
Dot Ball % = DIVIDE([Dot Balls], [Total Balls Bowled], 0) * 100

-- Combined Team Strike Rate (Final XI Builder)
Team Strike Rate = DIVIDE([Total Team Runs], [Total Team Balls], 0) * 100

-- Combined Team Economy
Team Economy = DIVIDE([Total Team Runs Conceded], [Total Team Overs], 0)
```

---

## How to Use

1. Clone or download the repository
2. Open the `.pbix` file in Power BI Desktop
3. Start on the **Final XI** page — use the search panel to pick 11 players and see combined team strength
4. Navigate to role-specific pages (Openers → Bowlers) using the top tab navigation
5. Click player names in the data table to isolate their performance in charts
6. Toggle Group Stage / Super Eight to compare phase-wise consistency

---

## Why This Project?

Standard cricket stats platforms show raw numbers. This dashboard answers the questions selectors actually ask:
- Who performs consistently vs who peaks in one game?
- Which opener has the best boundary rate under pressure?
- Can a team built around Russell and Pandya generate enough bowling variety?
- How does Bumrah's economy compare to other frontline bowlers in high-pressure Super Eight matches?

The role-based framework + interactive team builder transforms a statistics table into a genuine decision-support tool.

---

*Created by Mayur Goyal | [Portfolio](https://mg67.vercel.app/) | [LinkedIn](https://www.linkedin.com/in/mg67)*
