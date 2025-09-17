# 📺 Friends TV Series – Audience & Cultural Impact Analysis  

This project explores the audience of the TV series **Friends** across its 10 seasons, combining quantitative metrics (viewership and ratings) with qualitative aspects (directors, writers, and iconic quotes). The goal is to analyze **which factors influenced the audience** and how certain elements became part of the **cultural legacy** of the show.  

🔗 **Interactive visualizations on Tableau Public**  
- [Friends TV Series – Audience & Cultural Impact](https://public.tableau.com/views/FriendsTVSeriesProjectDashboardandAnalytics/TheOneWherePeaktoFinale_1?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)  
- [Tableau Portfolio with Advanced Features – Ana Nobre Santos](https://public.tableau.com/app/profile/ana.nobre/vizzes)  

---

## 🎯 Project Objectives  
- Analyze the evolution of viewership per season and episode.  
- Assess whether **episode direction** had a direct impact on audience levels.  
- Investigate whether **iconic quotes** influenced peaks in viewership.  
- Demonstrate the connection between **viewership data** and the **cultural impact** of *Friends*.  

---

## 🖥️ How to Open the Project  

### Tableau Public  
1. Download **Tableau Public Desktop** (free).  
2. Open the `.twbx` packaged workbooks inside the **Tableau/** folder.  
3. Or access directly via the Tableau Public links above.  

### Power BI (Mac users with VirtualBox)  
1. Install **VirtualBox** and set up a Windows VM.  
2. Inside Windows, install **Power BI Desktop** (free from Microsoft Store).  
3. Clone or download this GitHub repository **inside the Windows environment**.  
4. Open the file with Power BI Desktop:  
   ```
   Power-BI/Friends - Power BI.pbix
   ```
📌 **Note:** Power BI Desktop only runs on Windows. If you are on macOS or Linux, you will need to use a Windows VM (e.g., VirtualBox, Parallels) to open the `.pbix` file.  

---

## 📊 Tableau Visualizations  

1. **Big Numbers**  
- **236 episodes** across 10 seasons.  
- **32M peak audience** in the U.S.  
- **52.9M viewers** for the final episode.  
- **Average IMDb rating: 8.5/10**.  
- **Cultural longevity**: iconic quotes like *“How you doin’?”* and *“Oh my God!”* remain part of popular culture decades after airing.  

2. **Audience by Season (Total & Average Views)**  
   - Consolidated viewership per season.  
   - Insight: the show averaged **22M–26M viewers per season**, peaking in Season 2.  
   
   🏆 **Top 5 Episodes by Audience (US Nielsen Ratings; counting two‑parters individually):**  
   1. *“The One After the Superbowl, Part 1”* (S2E12) → **part of 52.9M combined**  
   2. *“The One After the Superbowl, Part 2”* (S2E13) → **part of 52.9M combined**  
   3. *“The Last One, Part 1”* (S10E17) → **part of 52.5M combined**  
   4. *“The Last One, Part 2”* (S10E18) → **part of 52.5M combined**  
   5. *“The One Where Rachel Has a Baby, Part 2”* (S8E24) → **34.9M viewers**  

3. **Directors vs Audience**  
   - Stacked area chart comparing directors’ contributions.  
   - Insight: no strong correlation between directors and audience; trends aligned with the narrative arc.  

4. **Quotes, Views & Cultural Impact**  
   - Cross-analysis of quotes (*“How you doin’?”*, *“Oh my God!”*) vs ratings.  
   - Insight: quotes did not spike viewership but became part of the **cultural memory**.  

## 📷 Tableau Dashboard Previews  

**1. The One With the Context**  
![Dashboard 1](Tableau/(1)%20The%20One%20With%20the%20Context.png)  

**2. The One Where Peak to Finale**  
![Dashboard 2](Tableau/(2)%20The%20One%20Where%20Peak%20to%20Finale.png)  

**3. The One With the Highest Ratings**  
![Dashboard 3](Tableau/(3)%20The%20One%20With%20the%20Highest%20RatingsScreenshot.png)  

---

## 📊 Power BI Visualizations  

**1. Audience Overview**  
![Power BI Dashboard 1](Power-BI/Dashboard-1-Power-BI.png)  
- KPIs: total episodes (236), seasons (10), IMDb rating (8.46), total audience (~6B views).  
- Viewership trends by season and across time (year/quarter/month/day).  

**2. Quotes by Character**  
![Power BI Dashboard 2](Power-BI/Dashboard-2-Power-BI.png)  
- Distribution of quotes by character.  
- Breakdown of iconic phrases (*“Oh my God!”*, *“How you doin’?”*, *“We were on a break!”*).  
- Dynamic **Season filter** for interactivity.  

**3. Directors & Top Episodes**  
![Power BI Dashboard 3](Power-BI/Dashboard-3-Power-BI.png)  
- Number of episodes directed by each director.  
- Correlation between **directors, votes, and average viewers**.  
- Highlight of the **Top 5 episodes by audience** using a Treemap visualization.  

**4. Audience by Episode Release Day**  
![Power BI Dashboard 4](Power-BI/Dashboard-4-Power-BI.png)  
- Evolution of viewership by episode release date.  
- Spikes visible for milestone episodes (Super Bowl special, finale).  

---

## ⚡ Advanced Features Implemented  

### 🔹 Tableau  
- **Navigation Buttons** → interactive storytelling across dashboards.  
- **Calculated Fields (with rationale):**  

```tableau
// Season & Episode 
// Creates a compact, readable key (e.g., "S2E13") to uniquely identify each episode
// across the entire series. Useful for labeling charts, building tooltips, joining tables,
// and enabling quick filtering/search by episode code.

Code: "S" + STR(INT([Season])) + "E" + STR(INT([Episode Number]))

// Standardize character names
// Source data had inconsistent casing (e.g., "rachel", "RACHEL", "Rachel").
// PROPER() normalizes to "Rachel", ensuring clean grouping, accurate aggregations,
// correct sorting, and a polished look in legends/labels.

Code: PROPER([Author])

// Detect iconic quote
// Flags whether a quote contains Joey’s catchphrase regardless of capitalization.
// LOWER() standardizes text to lower case; CONTAINS() finds the substring.
// This boolean can drive filters, highlight actions, counts by episode/character,
// and comparisons against viewership peaks.

Code: CONTAINS(LOWER([Quote]), "how you doin")

### 🔹 Power BI  
- **Buttons with Bookmarks** — Add **interactivity** and a clean UX by letting users **toggle between chart states** (e.g., different visuals, views, or filters) within the **same page**. This avoids clutter, keeps context, and supports storytelling (e.g., “Overview” vs “Deep Dive”).  
  - How it works (high-level):
    1. Arrange the visuals for **View A** (e.g., line chart) and **View B** (e.g., bar chart).  
    2. Create a **bookmark** for each state (View A, View B) capturing **data/visibility**.  
    3. Insert **buttons** and assign **Action → Bookmark** (View A / View B).  
    4. (Optional) Use **Selection Pane** to show/hide visuals per bookmark and **Sync slicers** to carry the same filters across views.  

- **Custom DAX Column** — Detects an **iconic phrase** in the quotes table regardless of capitalization, so you can **segment**, **filter**, or **highlight** episodes/characters that use it. This enables counts, comparisons (e.g., against viewership peaks), and dynamic labels.

```DAX
-- Returns a readable label
-- Returns a Boolean (preferred for modeling/filters), more efficient for measures and visuals that need TRUE/FALSE logic.
-- Useful for filters, visuals, and storytelling (“Contains OMG” vs “Does not contain”).
Column_OMG =
IF (
    CONTAINSSTRING ( LOWER ( 'friends_quotes'[quote] ), "oh my god" ),
    "Contains OMG",
    "Does not contain"
)

---

## 🎬 Data Storytelling  
This project goes beyond data visualization. By combining **interactivity (buttons, filters, parameters)** with **cultural context (quotes, characters, directors)**, the dashboards create a storytelling experience that explains not just *what* happened with *Friends* viewership, but also *why* it mattered in popular culture.  

---

## 📂 Repository Structure  

```
Portfolio-Tableau-Friends-Audience-Impact/
│
├── 📄 README.md
├── 📂 data/                 
│   ├── friends_episodes_v3.csv
│   ├── friends_info.csv
│   └── friends_quotes.csv
│
├── 📂 Power-BI/             
│   ├── Friends - Power BI.pbix
│   ├── Dashboard-1-Power-BI.png
│   ├── Dashboard-2-Power-BI.png
│   ├── Dashboard-3-Power-BI.png
│   └── Dashboard-4-Power-BI.png
│
├── 📂 Tableau/              
│   ├── (1) The One With the Context.twbx
│   ├── (2) The One Where Peak to Finale.twbx
│   └── (3) The One With the Highest Ratings.twbx
```

---

## 📌 Key Insights  

**Audience consistency**
Across 10 seasons, Friends maintained unusually steady mass audiences, with typical season averages around 22–26 million and a high around ~31 million in Season 2—evidence of durable loyalty over a long run. The ~5 million gap between a late-series average (~26M) and the Season-2 high (~31M) is itself comparable to the entire audience of many successful primetime shows.

**Why peaks happened** 
The largest spikes were driven by special contexts, not by who directed the episode. “The One After the Superbowl” (S2E12–13), scheduled immediately post-Super Bowl, drew ~52.9M viewers, the series’ all-time high; the finale “The Last One” (S10E17–18) reached ~52.5M through event status and narrative closure.

**Direction wasn’t determinant** 
Prolific directors such as Kevin S. Bright and Michael Lembeck helmed iconic entries, but week-to-week ratings patterns align more with programming context and character-driven story beats than with specific directors, consistent with the Super Bowl lead-out and finale effects.

**Iconic quotes** 
Cultural memory, not weekly spikes. Catchphrases powered long-tail appeal rather than immediate overnights. Notably, Joey says “How you doin’?” ~22 times across 236 episodes—far fewer than many remember—illustrating how a handful of sticky moments became brand-defining and kept the show culturally present decades later.

---

## 👩‍💻 Author  
**Ana Nobre Santos**  
- [LinkedIn](https://www.linkedin.com/in/ana-nobre-santos)  
- [Tableau Public](https://public.tableau.com/app/profile/ana.nobre/vizzes)  
- [GitHub](https://github.com/ana-nobre) 

---

📂 This project is part of my **Data Analytics portfolio**, showcasing the blend of **data visualization, interactivity, and storytelling** applied to one of the most popular TV series of all time. Explore my [**Tableau Public**](https://public.tableau.com/app/profile/ana.nobre/vizzes) and [**GitHub**](https://github.com/ananobre) for more projects featuring advanced **Tableau** and **Power BI** techniques.
