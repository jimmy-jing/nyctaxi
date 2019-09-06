# nyctaxi
capstone project on nyc taxi rides

Edits for FHV:
1. renamed all columns for standardization (dispatch_id, pickup_time, dropoff_time, pickup_loc, dropoff_loc, rideshare, company)
2. only starting from mid 2017, did companies provide dropoff time and location so imputed all missing location values with 0
3. for lyft rides, rides are registered as rideshare as long as a rideshare request was made regardless of whether it was matched. for other HVFHS, only matched rideshares are marked as 1
4. imputed missing values for rideshare which was only tracked in 2018. 0 = no rideshare, 1 = rideshare, 9 = untracked
5. pickup_loc and dropoff_loc refer to nyc zones 1-263 which we have a map-dict for further analysis/heatmap.
6. missing pickup and dropoff time (dropoff time was only tracked from mid 2017 onwards) was imputed with 2019-06-01 15:00:00 so column could be cast into datetime object.

Edits for Yellow:
1. realigned columns in yellow_2016_7
2. standardized all the columns for each year (some have pickup/dropoff lat/long and some have zones)
3. imputed the missing pickup/dropoff info with 0
4. lowercased all column names for consistency
5. no other missing data
6. dropped store_and_fwd_flag column

Edits for Green (very similar to yellow):
1. standardized all columns to be same as yellow (one exception)
2. ONE EXTRA COLUMN IN GREEN CALLED trip_type
3. dropped store_and_fwd_flag column
4. dropped ehail_fee column (every value was NaN)
5. imputed missing trip_type with mode of 1.0
6. no other missing data