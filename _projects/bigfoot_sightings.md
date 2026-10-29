
---
name: Bigfoot Sightings in the United States
tools: [Python, Altair, Vega-Lite]
description: Exploring the geographic distribution and yearly trends of reported Bigfoot sightings.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Bigfoot Sightings in the United States

This project explores reported Bigfoot sightings in the United States using the BFRO dataset. I created two visualizations to compare the geographic distribution of reports and how reporting patterns have changed over time.

## Visualization 1: Top 15 States by Bigfoot Sightings

<vegachart schema-url="{{ site.baseurl }}/assets/json/bigfoot_states.json" style="width: 100%"></vegachart>

The first visualization is a horizontal bar chart showing the 15 states with the highest numbers of reported Bigfoot sightings. I used a nominal encoding for the states on the y-axis and a quantitative encoding for the number of reports on the x-axis. The bars are sorted from highest to lowest to make comparisons easier. I used the default blue color because the chart focuses on comparing one numerical variable across states. In Python, I grouped the reports by state, counted the records, and selected the top 15 states. Washington has the most reports, followed by California and Florida. This chart helps show how reported sightings are distributed across different parts of the country.

## Visualization 2: Bigfoot Sightings Over Time

<vegachart schema-url="{{ site.baseurl }}/assets/json/bigfoot_timeline.json" style="width: 100%"></vegachart>

The second visualization is a line chart showing how the number of reported Bigfoot sightings has changed over time. The x-axis represents years, while the y-axis shows the number of reports. I used quantitative encodings for both axes and a nominal color encoding to distinguish different report classifications. I converted the date column to a datetime format, removed records with missing dates or classifications, and counted reports by year and classification. The chart shows that reports generally became more frequent in later decades, although this may also reflect changes in reporting and data collection. The dataset contains 4,747 records, of which 3,797 have usable dates and classifications for this visualization.

I also added an interactive dropdown menu that allows users to select a report classification or view all categories together. This makes it easier to compare reporting trends and focus on one classification without the other lines getting in the way.

## Data and Analysis

The data comes from the BFRO reports dataset provided for IS445. The visualizations were created using Python, Pandas, and Altair.

<div class="left">
{% include elements/button.html link="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/bfro_reports_fall2022.csv" text="The Data" %}
</div>

<div class="right">
{% include elements/button.html link="https://github.com/Q11z/Q11z.github.io/blob/main/python_notebooks/HW5_Visualization.ipynb" text="The Analysis" %}
</div>
