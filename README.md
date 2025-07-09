# 🚗 Dynamic Pricing for Urban Parking Lots  
**Summer Analytics 2025 Capstone Project | Consulting & Analytics Club × Pathway**

## 📌 Overview  
Urban parking is often plagued by static pricing, leading to either overcrowding or underutilization. Our project builds a **real-time dynamic pricing system** for 14 urban parking lots using live data, machine learning, and intelligent demand-based pricing models.  

Our goal:  
- Improve parking space utilization  
- Provide explainable, smooth pricing behavior  
- Simulate real-world economic conditions and rerouting logic (optional)

---

## 🛠️ Tech Stack  
| Category              | Tool/Library               |
|-----------------------|----------------------------|
| Programming Language  | Python                     |
| Data Manipulation     | Pandas, NumPy              |
| Real-Time Streaming   | [Pathway](https://pathway.com/) |
| Visualization         | Bokeh, Panel               |
| Model Logic           | Custom Linear & Ridge Models |
| Notebook Environment  | Google Colab               |

---

## 🏗️ System Architecture  
```mermaid
flowchart TD
    subgraph Real-Time Engine
        A[CSV Stream - parking_stream.csv] --> B[Pathway Replay Engine]
        B --> C[Daily Tumbling Window]
        C --> D[Pricing Engine]
    end

    subgraph Pricing Engine
        D1[Model 1: Baseline Linear Model]
        D2[Model 2: Demand-Based Model]
        D3[Optional: Model 3 - Competitive Model]
        D --> D1
        D --> D2
        D --> D3
    end

    D --> E[Price Output Table]

    subgraph Visualization Layer
        E --> F[Bokeh Line Plot]
        F --> G[Panel Web Interface]
    end
