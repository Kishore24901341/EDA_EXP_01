```
Name: KISHORE V
Reg No: 212224240077
```

# Experiment 1: EDA in IPL Dataset
## Aim:
To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.

## Algorithm / Procedure:

## 1.Import Libraries
  Import pandas for data handling.
  Import matplotlib and seaborn for visualization.
## 2.Load Dataset
  Use pd.read_csv() to load the IPL matches dataset.
  Check dataset shape using .shape.
  View first 5 rows using .head().
## 3.Matches per Season (Univariate Analysis)
  Group data by season and count matches.
  Plot a bar chart to visualize growth/decline in matches.
## 4.Top Winning Teams (Univariate Analysis)
  Use value_counts() on the winner column.
  Plot top 5 winning teams in a bar chart.
## 5.Toss Decisions (Univariate Analysis)
  Count toss decision preferences (bat vs field).
  Plot results using a bar chart.
## 6.Top Venues (Univariate Analysis)
  Count matches per venue.
  Display top 5 venues with a horizontal bar chart.
## 7.Draw Insights
  Observe patterns in toss decisions.
  Identify teams with consistent winning trends.
  
  ## Program:

### Basic info about dataset:
```python
import pandas as pd 
import matplotlib.pyplot as plt
import seaborn as sns
matches = pd.read_csv("matches.csv")
print("Name:Kishore V")
print("reg no:212224240077")
print("Dataset Shape:",matches.shape)
print(matches.head())

```
### Matches per season:

```python
matches_per_season = matches.groupby("season").size().reset_index(name="matches")

print(matches_per_season)

plt.figure()
plt.plot(matches_per_season["season"], matches_per_season["matches"], marker='o')
plt.xlabel("Season")
plt.ylabel("Number of Matches")
plt.title("IPL Matches per Season")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
print("Name:Kishore V")
print("reg no:212224240077")
```

###  Most successful teams:
```python

team_wins = matches["winner"].value_counts().reset_index()
team_wins.columns = ["team", "wins"]

top_5_teams = team_wins.head(5)

print(top_5_teams)

plt.figure()
plt.bar(top_5_teams["team"], top_5_teams["wins"])
plt.xlabel("Team")
plt.ylabel("Number of Wins")
plt.title("Top 5 Teams with Most Wins in IPL")
plt.xticks(rotation=30)
plt.tight_layout()
plt.show()
print("Name:Kishore V")
print("reg no:212224240077")
```

###  Toss decisions (bat vs field)
```python
 toss_decision_counts = matches["toss_decision"].value_counts().reset_index()
toss_decision_counts.columns = ["decision", "count"]

print(toss_decision_counts)

plt.figure()
plt.bar(toss_decision_counts["decision"], toss_decision_counts["count"])
plt.xlabel("Toss Decision")
plt.ylabel("Number of Times Chosen")
plt.title("Toss Decision Preference in IPL (Bat vs Field)")
plt.tight_layout()
plt.show()
print("Name:Kishore V")
print("reg no:212224240077")
```

### Venues hosting most matches:
```python
 venue_counts = matches["venue"].value_counts().reset_index()
venue_counts.columns = ["venue", "matches"]

top_5_venues = venue_counts.head(5)

print(top_5_venues)

plt.figure()
plt.bar(top_5_venues["venue"], top_5_venues["matches"])
plt.xlabel("Stadium")
plt.ylabel("Number of Matches")
plt.title("Top 5 Stadiums Hosting Most IPL Matches")
plt.xticks(rotation=30, ha="right")
plt.tight_layout()
plt.show()
print("Name:Kishore V")
print("reg no:212224240077")

```

  ## Output:
### Basic info about dataset:

<img width="833" height="740" alt="image" src="https://github.com/user-attachments/assets/81fb563d-b08e-445d-adad-ad27d1ff3ac7" />


### Matches per season:

<img width="924" height="835" alt="image" src="https://github.com/user-attachments/assets/f458ae29-6b40-4594-8c87-ec9c4a2180eb" />


###  Most successful teams:

<img width="873" height="829" alt="image" src="https://github.com/user-attachments/assets/326c953c-ce25-4f99-b459-33a39d312025" />


###  Toss decisions (bat vs field)

<img width="925" height="752" alt="image" src="https://github.com/user-attachments/assets/6d994831-8036-412e-9cfc-88ffa6d8faaa" />


### Venues hosting most matches:

<img width="928" height="821" alt="image" src="https://github.com/user-attachments/assets/fcf9f73e-bf51-49a6-a57a-3a0afe71e574" />



 ## Result:
  Thus experiment is executed successfully




