# Real Estate Dataset Milan
Here you can find the code to obtain a CSV dataset from *Casa.it*

## Prerequisites 
**libraries**: scrapy, geopy


Install by hand or run:
```bash
pip install -r prerequisites.txt
```

## Steps
Use an intermediate dataset with name *<file_name>*

### Step #1

*Scrape Casa.it website* 

```bash
scrapy runspider scraping_casa_it.py -o <file_name>.csv -t csv
```

With this step, you get a dataset called *<file_name>.csv*:
- name
- mq
- address
- energy class (HEC)
- number of bathrooms

*Stop here if you do not need anything else!*

### Step #2 

*Georeference all the real estates*

```bash
python3 get_lat_long_dist.py <file_name>.csv
```

With this step, you get a dataset called *<file_name>_updated.csv*:
- latitude
- longitude
- altitude
- distance from the dome (DFD)

## Final Reminder

Do you need other cities or other difference distances?
*Pls, modify the code as you prefer!*

In *scraping_casa_it.py*, change <city> variable to obtain another dataset in a different italian city, you can also get more pages (*default 8*)

In *get_lat_long_dist.py*, modify the <dome> variable to change the reference point in order to get the distance you need!
