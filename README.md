# 🐕 Society Stray Dog Demographics & Behavioral Mapping

An observational citizen-science project mapping stray dog populations, pack structures, health conditions, and territory dynamics across 5 residential society lanes. 

This repository leverages physical health metrics and behavioral observations to build an interactive GIS safety and healthcare map for local residents and animal welfare advocates.

---

## 📌 Project Overview & Key Insights

By tracking specific dog packs at multiple intervals throughout the day (Morning, Afternoon, Evening, and Night), this dataset uncovers localized behavioral patterns:
* **Territorial Crossing:** Identification of active "border-crossing" trespassers navigating between Lane 1, Lane 3, and Lane 4/5/6.
* **Environmental Aggression Triggers:** Behavioral tracking highlights that specific dogs remain calm under neutral human conditions but exhibit defensive aggression when triggered by **speeding bikes** or **children throwing stones**.
* **Health Hotspots:** Tracking coordinates alongside health markers (`Ticks` and `Limping`) allows local animal NGOs to pinpoint exactly where medical intervention or tick treatments are needed most.

---

## 🗂️ Repository Structure

```text
├── society-dog-tracker/
│   ├── README.md                 <-- You are here! Project overview page
│   ├── society_dogs_data.csv     <-- Raw observational dataset
│   ├── analyze_society_dogs.py   <-- Python parsing and data processing script
│   ├── lane_population_density.png <-- Automatically generated density graph
│   └── society_health_and_safety.png <-- Health and aggression metrics dashboard
```

---

## 📊 Dataset Dictionary (Data Attributes)

The underlying dataset `society_dogs_data.csv` contains the following structured attributes:

| Column Header | Data Type | Description / Dropdown Value Options |
| :--- | :--- | :--- |
| **Lane** | Categorical | Specific society location sector (`L_1`, `L_3`, `L_4/5/6`) |
| **Dog_Name** | Text | Broader pack group label classification |
| **Dog_ID** | Text | Unique identifier nickname assigned to individual dogs |
| **Gender** | Categorical | Biological sex assignment (`male`, `female`) |
| **Ear_Cut** | Boolean | Indicates sterilization/vaccination status via municipal ear notch (`yes`, `no`) |
| **Ticks** | Boolean | Visible parasite burden presence (`yes`, `no`) |
| **Limping** | Categorical | Locomotion or injury tracking indicator (`no`, `minor`, `yes`) |
| **Time_Seen** | Temporal | Timestamp format or cyclical check period of the observation |
| **Longitude / Latitude** | Float (GPS) | High-precision geospatial coordinate points pulled from Google Maps |
| **Human_Aggressive** | Text/Categorical | Complex behavioral reactions (`no`, `yes`, or specific situational triggers) |
| **Defense_Role** | Categorical | Pack defense hierarchy role (`front`, `secondry`, `defence`) |
| **Is_Trespasser** | Boolean | Identifies if the individual crosses territorial boundaries (`yes`, `no`) |
| **Target_Territory** | Categorical | Destination zone if the dog exhibits active boundary crossing |

---

## 🚀 How to Run the Analysis & View the Interactive Map

### 1. Prerequisites
Ensure you have Python installed on your system along with the necessary data manipulation, graphing, and mapping packages:
```bash
pip install pandas folium matplotlib seaborn
```

### 2. Execute Analysis script
Run the main script to process your dataset and compile your visual graphics:
```bash
python analyze_society_dogs.py
```

### 3. Review Generated Outputs
* **`index.html`**: A fully interactive leaf map. Open this file directly in any web browser to click, zoom, and inspect your custom color-coded map pins.
* **`lane_population_density.png`**: Generates bar charts summarizing localized observation spikes.
* **`society_health_and_safety.png`**: Displays a detailed breakdown comparing health concerns vs localized aggression metrics across the lanes.

---

## 🌐 Deploy Your Live Interactive Map via GitHub Pages

You can host your generated interactive map online completely for free using **GitHub Pages**:
1. Push your updated files (including `index.html`) to your remote GitHub repository.
2. In your repository settings web interface, navigate to the left-hand column menu and click **Pages**.
3. Under the **Build and deployment** settings section, set the deployment source branch dropdown menu to your target branch (usually `main` or `master`) and select the `/root` folder path option.
4. Click **Save**. 

GitHub will generate an active public web link (e.g., `https://github.io`) where your live, interactive society GIS map can be accessed by neighborhood residents anytime!

