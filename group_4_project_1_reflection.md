# Yuhui Duan-project1-Reflection

At the start of this project, I thought it would mostly involve plotting climate trends. But as we examined the data, I realized it was more about grasping the physical significance behind those trends.

One of the initial challenges for me was managing the raw CESM model data. The units were confusing at first, especially precipitation measured in kg/m²/s. After converting everything into Celsius and millimeters, I understood how important proper data processing is. Even minor errors in units could impact the results.

Working with time-series data also helped me see why we use annual averages. Initially, I just followed the code. Later, I understood that annual aggregation helps reduce seasonal fluctuations and emphasizes long-term trends more clearly.

An interesting moment came when we analyzed precipitation. I expected rainfall to increase clearly with temperature. However, the data showed important variability but no clear long-term trend. This made me realize that climate systems are complex. Temperature is closely linked to energy input, but precipitation relies more on atmospheric circulation, which is less consistent.

I also learned that correlation does not imply causation. We had to connect statistical findings with physical mechanisms, such as radiative forcing and water vapor feedback. This changed how I approach data analysis.

When watching other groups' presentations, I noticed some analyzed data by seasons instead of only using annual averages. Their work seemed more detailed in some ways. This made me think that our project could also be expanded by doing deeper seasonal comparisons or including additional variables. Although I am not familiar with all the details of their analysis, it showed me that there are always different ways to explore the same dataset.

Overall, this project helped me move beyond just running code. I now better understand how to connect data, statistics, and physical reasoning. It also made me realize there is always room to improve and explore climate data from various perspectives.


---

Kedi_Li 14200199 Reflection
1. For research question
The research question directly determines how we process the data.
For example, if we want to check the yearly trend, we should use yearly mean values. The resolution is small, and the correlation is small. But it is answering the question based on the research question.
In our project, we use yearly data to answer the question: How does the weather change with time, and what are the potential controlling factors? Therefore, we use the code below to calculate the yearly mean and meanwhile create a new data frame.
annual_mean = df.groupby("year")[["TREFHT_C", "PRECT_mm", "FSNS", "FLNS", "QBOT_g_kg", "UBOT", "VBOT"]].mean().reset_index()
If we want to check whether two variables have a relationship or not, we may compare the temporal sampling data to check their potential linear relationship. But that is a different research question. It only shows short-term relations (like a day) but does not show long-term correlation.
When we work in a group, people should first know what their research question is; second, work on yearly, seasonal, or daily data comparison. Otherwise, their data output could have huge differences, especially regarding the correlation calculation.
2. For data format
At the beginning, we need to import packages with specific names for convenience.
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import linregress
The second thing is to read the CSV data by using pd. Without this step, we cannot manipulate our data. We generally manipulate our data in the format of a data frame.
The third thing is to transfer the date in array format to datetime format; therefore, the computer can know the data is a date.
df["time"] = pd.to_datetime(df["time"])
Therefore, we can extract the exact year to plot the graph.
df["year"] = df["time"].dt.year
3. For display in general (visualization format)
We can use the matplotlib.pyplot package at very beginning; therefore, we can make sure the unity of the format of every graph, including font, background, step size, etc.
More than that, in Python, graph production and display changes rely on two packages. Seaborn is responsible for drawing at first, and Matplotlib takes the responsibility of changing the canvas format and display.
A sample plot like temperature change with time can be achieved by Matplotlib as well.
However, in R, it is a combined package named ggplot2; the decoration and graph production can be formed in the same line of code.
4. For graph generation
The graph has limited size and limited volume; therefore, we need to select our data, either from random sampling or yearly mean. If we display all the data and the data is normally distributed, the graph could show a strange basketball shape (the American one), making the data unidentifiable for visualization. Therefore, trade-off is essential.
When we analyze our data, having a clear process is crucial.
corr_vars = ["TREFHT_C", "FSNS", "FLNS", "QBOT_g_kg", "UBOT", "VBOT", "PRECT_mm"]
corr_matrix = annual_mean[corr_vars].corr()
In this step, when we generate the correlation heatmap, we should first define the variables we want to select, then use them in the drawing process. Rather than mixing the code, we can separate them to make sure the process does not have any mistakes.

---


# Project Reflection

> **Overview:** This reflection is about my experience in the EART60702 project. It shows how our group learned to use Python to process large datasets and how I changed my understanding of climate change.

Name: Ruiqi Huang

Student ID: 14180111

Course: EART60702 Earth and Environmental Data Science

Date: 26 February 2026

---

## 1. At the Beginning

When I first opened the Excel file for this project, to be honest, I felt a bit lost. The table had a huge amount of daily climate data for 75 years. There were so many short names in the table headers (like `TREFHT`, `FSNS`, `QBOT`), and I had to search for their meanings one by one. I really didn't know how to start.

Luckily, our professor and the GTAs helped us a lot. None of the three members in our group had learned programming before, so we were totally beginners. The teachers taught us step by step. They also guided us to think about what the data really means, what topic we should choose, and what kind of charts we should draw. 

## 2. Learning Python and Fixing Bugs

In our group, I was mainly in charge of "integrating the code" and "drawing the annual trend and scatter plots". Because I didn't know how to write code, I went to Bilibili and watched a Python tutorial for beginners made by "Shangguigu" (尚硅谷). From the videos, I learned the basics of data analysis and visualization using `numpy`, `pandas`, and `matplotlib`.

When I tried to put my teammates' code together, it was not easy. I often met bugs and errors. When that happened, I would look at the error messages in PyCharm to see what was wrong, or sometimes I used AI to help me find the syntax mistakes. Through this process, my coding skills improved a lot.

## 3. A Discovery About Climate Change

Before doing this project, my understanding of "climate change" was very simple. I just thought it meant the temperature goes up because of greenhouse gases. 

But things changed when our group finished the Correlation Matrix and the scatter plots. I was surprised to find that the data perfectly matched the **Clausius-Clapeyron relation**. I realized that Surface Net Solar Radiation (`FSNS`) and Specific Humidity (`QBOT`) are also very important reasons that cause climate change. It is a complicated system. The high humidity actually makes the warming effect even worse. This was a big discovery for me.

## 4. Personal Growth

This project was a great learning experience for me. In the past, I only knew how to use Excel and Origin to draw simple charts. But for a huge dataset with tens of thousands of rows like this one, Python is much faster, more convenient, and has fewer mistakes. 

I am really glad that I learned how to use Python to process data. I also learned how to find the real physical rules behind a huge table of numbers. I believe these skills will be very helpful for my future studies.