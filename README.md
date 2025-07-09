# Dynamic Pricing for Urban Parking Lots
Capstone Project of Summer Analytics 2025

Urban parking spaces are a scarce and highly sought-after resource in bustling city environments. Traditionally, parking fees remain static throughout the day, which often results in two major problems: **overcrowding during peak hours and underutilization during off-peak periods.**
These inefficiencies contribute to increased traffic congestion, pollution, and driver frustration.

Dynamic pricing offers a promising solution by adjusting parking fees in real time based on demand fluctuations, competitor pricing, and other relevant conditions. Such a system encourages better distribution of parking space usage, improves revenue for parking lot operators, and enhances overall urban mobility.

This project aims to design and simulate an intelligent, data-driven pricing engine for 14 urban parking lots. The system will leverage real-time data streams combined with foundational economic principles and machine learning models developed from scratch (using only numpy and pandas) to optimize prices dynamically.

All processing is handled in real-time using the **Pathway** stream processing engine, and results are visualized with **interactive Bokeh plots**.
It intelligently updates prices based on:
- Occupancy patterns
- Queue lengths
- Traffic congestion
- Special events
- Vehicle types
- Competitive pricing from nearby lots

**Tech Stack Used:**

- **Python**       | Core programming language                  
- **Pathway**      | Stream processing engine for real-time data ingestion and transformation 
- **Pandas**       | Pre/post-processing and advanced pricing logic 
- **Bokeh + Panel**| Real-time plotting and interactive dashboards 
- **Google Colab** | Notebook environment for simulation    

**Architecture Diagram:**

 ![image](https://github.com/user-attachments/assets/8683da2c-9910-427b-a0d9-bd59f5039c01)


**Project Architecture & Workflow**
**1. Data Preprocessing:** Cleaning and organizing the time-series occupancy and pricing data.
Raw data contains per-minute parking data across multiple lots.We clean and add necessary features:
- Timestamps
- Traffic, Queue Length
- Special Events
- Simulated geolocation for each lot

**2. Pricing Engine:** Created an algorithm to set prices dynamically based on demand forecasts and competitor prices.
- Model 1	Recursive: price[n] = price[n-1] + α × occ_rate
- Model 2	Weighted formula using queue, traffic, vehicle type, and special day
  
  ![image](https://github.com/user-attachments/assets/45ceafae-85b7-42c0-ae3f-0d49e14b336b)

*To view the pricing plot for the 14 parking lots with Model 1 and Model 2, download the pricing_plot.html as raw file and view.*

**3. Visualisation:** Each pricing model is plotted in real-time graphs using Bokeh+Panel

**4. Smart Rerouting** made available through a message
If a lot is full and nearby lots are cheaper → Suggest rerouting.


Please find the attached report for further details on approach and implementation.

References:
- https://github.com/pathwaycom/pathway
- https://www.geeksforgeeks.org/data-visualization/python-bokeh-tutorial-interactive-data-visualization-with-bokeh/
- https://online.hbs.edu/blog/post/what-is-dynamic-pricing

