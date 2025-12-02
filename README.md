# Footfall Counting & H3 Spatial Indexing

### *Footfall_Counting_Cellsite2H3.ipynb*

This repository contains a PySpark + H3-based data engineering workflow
that transforms raw CDR (Call Detail Record) + cellsite location data
into **H3-indexed footfall analytics**, enriched with customer
demographics (age groups). The final output is a parquet report
aggregated at **H3 resolution 9**.

## Project Overview

This notebook processes hourly footfall data by:

1.  Loading CDR + Cellsite reference tables
2.  Joining to estimate user positions from cellsite locations
3.  Converting latitude / longitude to H3 resolution-9
4.  Filter out irrelevant based on location metadata (H3 lookup table)
5.  Adding demographics from Customer360 table
6.  Aggregating footfall counts & age-group distributions
7.  Saving the final dataset to a Parquet file
