# Data

## Source
- **Dataset:** DataCo Smart Supply Chain for Big Data Analysis (public, Kaggle)
- **Grain:** one row per order item (an order with several products has several rows)

## Cleaning Steps (Power Query)
1. **Kept only the columns needed.** Removed customer personal data (first name, last name, email, password, street address) and columns not used in the analysis (product description, product image, product status, order zipcode).
2. **Parsed dates with the correct locale.** Order date and shipping date were stored as text in US format (M/D/YYYY), converted to date/time using the English (United States) locale to avoid day/month mix-ups.
3. **Set numeric types.** Sales, order item total, profit per order, benefit per order, product price, discount and discount rate set to decimal; Late_delivery_risk and quantities set to whole number.
4. **Added DelayDays** = `Days for shipping (real)` − `Days for shipment (scheduled)`, as a whole number. Positive = shipped late, zero = on time, negative = shipped early.

## Tables Not Loaded
The source includes an access-log table and a description table; neither is used in the report, so they are not loaded into the model.
