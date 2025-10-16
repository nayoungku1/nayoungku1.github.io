---
title: "Finding the Optimal Candidate Locations of Vertiports for Hospital Accessibility using K-Means"
excerpt: "Project for HGU AIX20003 -- Introduction to ML (Fall'23) Advised by Prof. Junghyun Kim <a href='https://docs.google.com/presentation/d/1BldVgQSGUzeCSSf-0BxVl2764WyX8mEgviARHuxn_kA/edit?usp=sharing'>[Slide]</a>"
collection: portfolio
---


Project for HGU AIX20003 -- Introduction to ML (Fall'23) Advised by Prof. Junghyun Kim <a href='https://docs.google.com/presentation/d/1BldVgQSGUzeCSSf-0BxVl2764WyX8mEgviARHuxn_kA/edit?usp=sharing'>[Slide]</a>

Given Korea's geography, with many islands in the West Sea and mountains in the East Sea, we explored the potential use of urban air mobility (UAM) for medical emergencies, similar to current helicopter services for hospitals. Our goal was to identify candidate locations for vertiports that would maximize hospital accessibility.  

We collected a dataset of university hospitals in Korea, including their latitude and longitude, and applied K-Means clustering with five centroids. Since four existing vertiport centroids were already defined without considering hospitals, we focused on determining five additional locations to improve hospital access.  

**Results – Additional Vertiport Candidates:**  
1. **Yupo-ri (유포리):** The local transportation infrastructure is limited and the town is small, so we selected a nearby alternative location to improve accessibility.  
2. **Namwon-si (남원시):** While the city is moderately sized, a hospital centroid already exists in nearby Gwangju (광주), so we excluded this location to minimize construction costs.  
3. **Gunwi-gun (군위군) near Daegu (대구):** Proximity to Daegu International Airport and its central location in Gyeongsang-do make this area favorable for establishing a vertiport, leveraging existing airport infrastructure.  
4. **Osan-si (오산시):** This location offers excellent transportation connectivity and strategic positioning, making it an ideal candidate.  
