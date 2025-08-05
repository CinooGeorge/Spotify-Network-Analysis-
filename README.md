# Spotify-Network-Analysis
# 🎵 Spotify Artist Collaboration Network Analysis & Popularity Prediction  

## 📌 Project Overview  
This project analyzes the **Spotify artist collaboration network** and leverages **machine learning** to predict artist popularity. Using a **graph-based approach**, the study examines how artist collaborations and network positions influence popularity metrics.  

The analysis includes:  
- 📈 **Graph Network Analysis** of artist collaborations  
- 🔍 **Centrality Measures** to identify key influencers  
- 🤖 **Machine Learning (Linear Regression)** to predict popularity  
- 🔗 **Clustering (K-Means)** to group artists based on network characteristics  

---

## 👤 Developers  
- **Cinoo Bosco Thomas**  

---

## 📂 Dataset Overview  
Two datasets were used:  

### 🎶 Node Dataset (Artists)  
Contains attributes for 156,422 artists:  
- **Spotify ID** – Unique identifier  
- **Artist Name** – Name of the artist  
- **Followers** – Number of Spotify followers  
- **Genres** – Music styles associated with the artist  
- **Chart Hits** – Number of songs that charted  
- **Popularity** – Spotify popularity score (0–100)  

### 🎼 Edge Dataset (Collaborations)  
Contains 300,386 edges representing collaborations:  
- `artist_id_1` – Source artist  
- `artist_id_2` – Target artist  

---

## 🔄 Data Preprocessing  
- ✅ Dropped duplicates and irrelevant columns  
- ✅ Filled missing values for popularity  
- ✅ Normalized numerical features  
- ✅ Selected a **subset of 100 top-followed artists** for network analysis (for efficiency)  

---

## 🕸️ Network Analysis  
The artist network was analyzed using **centrality measures**:  
- **Degree Centrality** – Number of direct collaborations  
- **Betweenness Centrality** – Measures bridging capability  
- **Closeness Centrality** – Proximity to all other artists  
- **Eigenvector Centrality** – Influence via connections to influential artists  
- **PageRank** – Importance based on link structure  

### ✅ Key Findings  
- **Johann Sebastian Bach** emerged as the most influential artist across multiple measures.  
- The network is **sparse**, with an **average degree of 0.26**.  
- The **largest connected component** has a diameter of 20, indicating fragmentation.  

---

## 🤖 Popularity Prediction (Linear Regression)  
Using **PySpark MLlib**, a linear regression model was built to predict artist popularity using:  
- Followers  
- Degree, Betweenness, Closeness, Eigenvector, PageRank  

### 🧪 Model Performance  
- **RMSE:** 28,715.41  
- **R²:** -0.0012  

➡️ The negative R² indicates **poor predictive power**, suggesting that additional features or more complex models are required.  

### 🎯 Feature Impact  
- **Betweenness Centrality** had the strongest positive influence on popularity.  
- **Closeness & Eigenvector** centralities showed negative effects, meaning these measures alone do not guarantee popularity.  

---

## 🎯 Clustering (K-Means)  
K-Means was applied using **network features** to group artists:  
- Optimal **k = 2** (based on Silhouette Score)  

### 🟢 Cluster Insights  
- **Cluster 0:** Low influence artists, niche or emerging figures  
- **Cluster 1:** Highly influential artists with strong centrality  
- **Cluster 2:** Moderately influential artists, potential rising stars  

---

## ✅ Conclusion  
The analysis:  
- Identified **key influencers** and network structures  
- Showed **network position** (centrality) impacts popularity  
- Highlighted the need for **better features/models** to improve prediction accuracy  

---

## 🎯 Applications  
- 🎧 **Enhancing Music Recommendations** using network insights  
- 📢 **Targeting Influencers** for marketing campaigns  
- 🚀 **Identifying Emerging Artists** based on clustering  
- 🎶 **Curating Playlists** by artist influence and collaboration patterns  
- 📊 **Monitoring Trends** through network evolution  

---

## 🛠️ Technologies Used  
- **Big Data Processing:** Apache PySpark  
- **Graph Analysis:** NetworkX / GraphFrames (assumed usage)  
- **Machine Learning:** PySpark MLlib (Linear Regression, K-Means)  
- **Visualization:** Matplotlib, Seaborn  
- **Data Sources:** Spotify datasets (nodes & edges)  

---

## 🚀 How to Run  
1. Clone the repository:  
```bash
git clone https://github.com/CinooGeorge/Spotify-Network-Analysis.git
cd Spotify-Network-Analysis
