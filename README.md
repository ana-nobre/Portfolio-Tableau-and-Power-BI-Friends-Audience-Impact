# 📺 Friends TV Series – Audience & Cultural Impact Analysis  

This project explores the audience of the TV series **Friends** over its 10 seasons, combining quantitative metrics (viewership and ratings) with qualitative aspects (directors and iconic quotes). The goal is to analyze **which factors influenced the audience** and how certain elements became part of the cultural legacy of the show.  

🔗 **Interactive visualizations on Tableau Public:**  
- [Friends TV Series – Audience & Cultural Impact](https://public.tableau.com/app/profile/ana.nobre/vizzes)  
- [Tableau Portfolio with Advanced Features – Ana Nobre Santos](https://public.tableau.com/app/profile/ana.nobre/viz/FriendsTVSeriesProjectDashboardandAnalytics/TheOneWherePeaktoFinale2)  


---

## 🎯 Project Objectives  
- Analyze the evolution of viewership per season and episode.  
- Assess whether **episode direction** had a direct impact on audience levels.  
- Investigate if **iconic quotes** influenced peaks in viewership.  
- Demonstrate the connection between **viewership data** and the **cultural impact** of *Friends*.  

---

## 📊 Visualizations  

1. **Audience by Season (Total & Average Views)**  
   - Shows consolidated viewership per season.  
   - Insight: the series averaged between **22M and 26M viewers** per season, with a peak in Season 2.  

2. **Directors vs Audience**  
   - Stacked area chart showing contributions of different directors over time.  
   - Insight: **no clear correlation** between directors and viewership; trends followed the narrative arc and life cycle of the show.  

3. **Quotes, Views and Cultural Impact**  
   - Combines visualizations of iconic quotes occurrence with episode ratings.  
   - Insight: quotes like *“How you doin’?”* and *“Oh my God!”* did not directly affect viewership but played a central role in the **cultural memory of the show**.  

4. **Big Numbers**  
   - IMDb average rating (8.5/10).  
   - Final episode audience (52.9M).  
   - Single-episode viewership peaks.  

---

## 🧮 Tableau Calculations  

Some of the calculated fields created in Tableau to structure and enrich the analysis:  

```tableau
// Create Season + Episode identifier
"S" + STR(INT([Season1])) + "E" + STR(INT([Episode]))

// Alternative version (with different field names)
"S" + STR(INT([Season])) + "E" + STR(INT([Episode Number]))

// Check for occurrence of the phrase "How you doin"
CONTAINS(LOWER([Quote]), "how you doin")

// Standardize author/character names
PROPER([Author])

// Create production year range
STR(MIN([Year of prod])) + " – " + STR(MAX([Year of prod]))
```

---

## 📂 Repository Structure  

```
Portfolio-Tableau-Friends-Audience-Impact/
│
├── 📄 README.md                          → Project documentation
│
├── 📂 images/                            → Dashboard screenshots
│   ├── (1) The One With the Context.png
│   ├── (2) The One Where Peak to Finale.png
│   └── (3) The One With the Highest RatingsScreenshot.png
│
├── 📂 data/                              → Datasets used for analysis
│   ├── friends_episodes_v3.csv
│   ├── friends_info.csv
│   └── friends_quotes.csv
```

---

## 🛠️ Tools Used  
- **Tableau Public**: dashboards and storytelling.  
- **GitHub**: version control and project portfolio.  

---

## 📌 Key Insights  
- *Friends* maintained a solid and loyal audience base throughout its 10-year run.  
- **Directors** were not a determining factor in explaining viewership peaks or declines.  
- **Iconic quotes** did not directly affect ratings but ensured the show’s **lasting cultural impact**.  
- The success of *Friends* is tied to its **narrative arc**, the **charisma of the characters**, and its **ability to create memorable moments**.  

---

## 👩‍💻 Author  
**Ana Nobre Santos**  
- [LinkedIn](https://www.linkedin.com/in/ana-nobre-santos)  
- [Tableau Public](https://public.tableau.com/app/profile/ana.nobre/vizzes)  

---

📂 This project is part of my **Data Analytics portfolio**, combining **data visualization and storytelling** to extract insights from one of the most popular TV series of all time.  
