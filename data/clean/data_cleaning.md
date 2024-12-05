A record of data cleaning functions used on the raw data.


### Sheets and naming
1. .csv's loaded into Excel and renamed for ease of use.
    - customers.csv > 'profiles' Sheet
    - orders.csv > 'returns' sheet
    - geo_lookup.csv > 'region_codes'

2. rename headers for traceability
    - orders.id > orders.order_id
    - profiles.id > profiles.customer_id
    - retruns.id > returns.order_id

### orders sheet data
1. 27in"" 4k gaming monitor > 27in 4K gaming monitor
2. bose soundsport headphones > Bose Soundsport Headphones
3. 'usd_price' data type > Currency
4. 'usd_price' contains empty values. for these rows, 'local_price' is also zero and the 'order_id' values are not present in 'returns; sheet. So, deleted these.
    - Only occurse in the following currencies: KES, LKR, GHS, MAD, BOB, PYG, RSD, MMK, JOD, and DZD
5. Blanks in 'usd_price'. Local currency present > fill in blanks with corresponding values for these currencies from other rows. 
6. There are many more product codes than products. All codes correspond to a single product and I do not plan on using them for this analysis. So, leave them like they are. 
7. No duplicates found in 'order_id.'

### profiles sheet data
1. 973 rows are blank for the 'marketing_channel' and 'account_creation_method' fields. Filled 'marketing_channel' in with "unknown" value. Noticed that all of the unknown values correspond with the tv account creation method. 
    WARNING: 'marketing_channel' values have a direct relationship with 'account_creation_method.' Could be an error.

2. 'country_code' value "A1" changed to "AL."
3. Blank 'country_code' values > "unknown"
4. No duplicates found in 'customer_id.'

### returns sheet data
No changes.

### region codes data
1. Filled in blanks with correct country code. Asked ChatGPT to take a look and double checked changes. 