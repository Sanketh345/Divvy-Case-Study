# 🚴 Divvy Case Study — Google Data Analytics Capstone  

### 🧭 Project Description  
This project analyzes **12 months of Divvy (Cyclistic) bike-share data** to understand how **annual members** and **casual riders** use the service differently — and identify actionable strategies to **convert casual riders into annual members**.  

Cyclistic operates Chicago’s bike-share system with **5,800+ bikes** and **600+ docking stations**. Using **SQL in Google BigQuery** and **Looker Studio visualizations**, this analysis explores ride duration, frequency, and seasonal patterns to help the company grow its annual memberships and improve customer retention.  

---

## 🧰 Tools & Technologies  
| Tool | Purpose |
|------|----------|
| **Google Cloud Storage** | Store and organize monthly ride data |
| **BigQuery (SQL)** | Clean, transform, and analyze datasets |
| **Looker Studio** | Build and visualize analytical dashboards |
| **Google Sheets / Excel** | Validate and cross-check calculations |

---

## 🧹 Data Preparation Process  

1. **Data Upload:**  
   - All 12 months of Divvy trip data (Jan–Dec 2024) were uploaded into **Google Cloud Storage**.  

2. **BigQuery Integration:**  
   - Each CSV was combined into a single table `tripdata_all`.  
   - Schema was auto-detected with columns like `ride_id`, `rideable_type`, `started_at`, `ended_at`, `start_station_name`, `end_station_name`, `start_lat`, `start_lng`, `end_lat`, `end_lng`, and `member_casual`.

3. **Filtering and Validation:**  
   - Removed rows with `NULL` or invalid timestamps and coordinates.  
   - Ensured `ended_at > started_at`.  
   - Filtered lat/long values between **40–43°N** and **–88 to –87°W** to focus on Chicago rides.  

4. **Feature Engineering:**  
   - Added new fields for analytics:
     | Column | Description |
     |---------|-------------|
     | `ride_length_minutes` | Trip duration (`ended_at - started_at`) in minutes |
     | `day_of_week` | Extracted weekday (1=Sun to 7=Sat) |
     | `month_name` | Month label for visualizations |

---

## 🧮 Key Calculations  

### 🔹 Summary Statistics  
| Metric | Value (minutes) |
|:--|:--:|
| **Minimum Ride Length** | 0.0 |
| **Maximum Ride Length** | 1509.37 |
| **Average Ride Length** | 15.48 |

### 🔹 Average Ride Length by Rider Type  
| Rider Type | Avg Ride (min) |
|-------------|----------------|
| Member | 12.40 |
| Casual | 21.55 |

### 🔹 Total Rides by Rider Type  
| Rider Type | Total Rides |
|-------------|--------------|
| Casual | 2,080,119 |
| Member | 3,641,253 |

### 🔹 Average Ride by Day of Week  
| Day | Avg Ride (min) |
|------|----------------|
| Sunday | 18.99 |
| Monday | 14.71 |
| Tuesday | 13.76 |
| Wednesday | 14.19 |
| Thursday | 14.02 |
| Friday | 15.35 |
| Saturday | 18.92 |

---

## 📊 Visualizations  

### 🟦 1️⃣ Average Ride Length by Rider Type
![Average Ride Length](visuals/avg_ride_length_by_type.png)  
Casual riders take longer rides compared to members, suggesting more leisure-oriented usage.

---

### 🟩 2️⃣ Total Rides by Rider Type
![Total Rides](visuals/total_rides_by_type.png)  
Members take significantly more rides overall, reflecting regular commuting patterns.

---

### 🟨 3️⃣ Average Ride Length by Day of Week
![Average Ride Length by Day](visuals/avg_ride_length_by_day.png)  
Ride duration peaks on weekends — especially for casual riders — indicating higher leisure use.

---

### 🟥 4️⃣ Total Rides by Day of Week
![Total Rides by Day](visuals/total_rides_by_day.png)  
Members dominate weekday rides, while casual users surge on weekends.

---

### 🟪 5️⃣ Monthly Ride Trends by Rider Type
![Monthly Ride Trends](visuals/monthly_ride_trends_by_user_type.png)  
Both groups peak during summer months (June–September), but members maintain steadier year-round activity.

---

## 💡 Key Insights  

| Insight | Implication |
|----------|-------------|
| Casual riders take longer but fewer rides. | They likely use bikes for leisure or recreation. |
| Members ride shorter, frequent trips. | Indicates commuting and daily use. |
| Weekends & summer show spikes for casual riders. | Marketing should target seasonal and weekend promotions. |
| Members maintain steady usage. | Annual memberships support consistent revenue flow. |

---

## 🎯 Recommendations  

1. **Seasonal Trial Memberships:** Offer discounted summer memberships to convert casual riders.  
2. **Weekend/Flex Passes:** Create flexible membership tiers for leisure-focused riders.  
3. **Commuter Campaigns:** Highlight savings and convenience for regular weekday riders.  
4. **Local Partnerships:** Bundle memberships with hotels, events, and tourist attractions.  
5. **Loyalty Rewards:** Incentivize frequent casual riders to upgrade through milestone rewards.

---

## 🚀 Outcome  

- Cleaned and analyzed **5.7M ride records** using SQL in BigQuery.  
- Built **five core visualizations** in Looker Studio.  
- Delivered **data-backed marketing insights** to increase annual memberships.  

---

## 🧠 Skills Demonstrated  
- Data Cleaning (SQL / BigQuery)  
- Data Aggregation & Transformation  
- Descriptive Analysis  
- Looker Studio Dashboard Design  
- Data Storytelling & Visualization  

---

## 🧾 License  
Data © Motivate International Inc. — provided under an open data license.  

---

## 👤 Author  
**Sanketh Reddy**  
🎓 B.S. Computer Science — University of Kansas  
🔗 [LinkedIn](YOUR_LINKEDIN_URL) | [Looker Dashboard](YOUR_LOOKER_LINK_HERE) | [GitHub](https://github.com/sanketh-reddy)
