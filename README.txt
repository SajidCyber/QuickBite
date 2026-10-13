QUICKBITE FOOD DELIVERY INSIGHT — SYNTHETIC DATASET (ROUND 2)

Purpose
This is fabricated synthetic data for practicing EDA and feature engineering. It is not real QuickBite business data and should not be presented as real-world measured evidence.

Files
- orders.csv: 505 rows (500 generated orders plus 5 intentional duplicate order-ID rows)
  order_id, order_time, restaurant, customer_zone, order_value
- riders.csv: 40 rider records
  rider_id, rider_name, experience_months, shift
- routes.csv: 500 route records
  order_id, distance_km, traffic_level, zone
- weather.csv: 500 weather records
  order_id, rain_level, temperature_c, visibility_km
- delivery.csv: 500 delivery records
  order_id, rider_id, pickup_time, delivered_time, status

Join keys
- orders.order_id joins to delivery.order_id, routes.order_id, and weather.order_id.
- delivery.rider_id joins to riders.rider_id.

Intentional data-quality issues
- Missing order/pickup/delivery timestamps
- Five duplicate order IDs in orders.csv
- Inconsistent zone spellings, capitalization, and whitespace
- Five negative delivery durations (delivered_time earlier than pickup_time)
- Missing weather readings
- Categorical fields and date/time fields that need preprocessing

Suggested Round 2 workflow
1. Load all CSVs with pandas.
2. Inspect shape, dtypes, nulls, duplicates, and summary statistics.
3. Parse timestamps and standardize zone labels before merging.
4. Remove/resolve duplicate orders; validate merge row counts.
5. Create delivery_duration_min, pickup_wait_min, order_hour, day_of_week, is_weekend, and delay flags.
6. Compare duration by zone, traffic, rain, restaurant, distance band, and hour.
7. Use charts and explain findings as patterns in synthetic data only.
