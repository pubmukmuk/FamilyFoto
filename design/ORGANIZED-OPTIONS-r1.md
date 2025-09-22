## ✅ OPTION 1: Flat by Decade → City
Great for high-level visual browsing and location-first grouping.

<pre>
organized/
├── 2000-2009/
│   ├── SaltLake_UT/
│   │   ├── 2007-07-21_UTSL_10-32.jpg
│   │   ├── ...
│   ├── Boston_MA/
│   └── Unknown_Location/
├── 2010-2019/
│   ├── Orlando_FL/
│   └── Seattle_WA/
</pre>

Pro: Easy to find all photos from one city regardless of year.

Con: Harder to sort by strict chronology.


## ✅ OPTION 2: Flat by Location → Year
Prioritize browsing by location, with date folders inside each.

<pre>
organized/
├── SaltLake_UT/
│   ├── 2007/
│   │   ├── 07-21_UTSL_10-32.jpg
│   ├── 2015/
│   └── metadata.csv
├── Orlando_FL/
├── Unknown/
</pre>

Pro: Great if you're organizing family albums by where events happened.

Con: Still moderately deep hierarchy.


## ✅ OPTION 3: Single Flat Folder with Smart Filename Indexing
Best for tools, search, and keeping the filesystem simple.

<pre>
organized/
├── 2007-07-21_UTSL_10-32.jpg
├── 2011-03-02_FLOR_12-10.jpg
├── 2015-11-15_UNKNOWN_08-00.jpg
├── ...
</pre>

Each file is:

YYYY-MM-DD_GEOCODE_HH-MM.jpg

With geocode (like SLC = Utah, Salt Lake)

Optionally indexed with a city-state table for mapping later

Pro: Very fast, searchable, tool-friendly

Con: Requires tools/scripts/tags to organize visually


## 🧠 Suggested Hybrid

<pre>
organized/
├── 2000-2009/
│   ├── SaltLake_UT/
│   │   ├── 2007-07-21_UTSL_10-32.jpg
│   │   ├── ...
│   ├── Orlando_FL/
│   ├── Unknown/
│   └── _index.csv      # mapping of geocodes to cities
</pre>


