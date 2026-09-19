# Bakery-Waste-Reduction-Analysis
## Project Background
Fresh bakery products have a short shelf life, ranging from approximately 3 to 14 days, making inventory management especially important. In the grocery store bakery area where I work, I observed a recurring pattern of excess inventory, markdowns, and product waste.

When products do not sell, they are marked down in the last day of shelf life. The markdown is recorded in the system as waste and can trigger the replenishment process to send additional product from the warehouse. However, the replenishment system does not have visibility into all of the inventory stored in the store's backroom freezer. As a result, additional products may arrive even when the store already has one or more boxes of the same product in backroom inventory.This can create a recurring cycle:

##### Excess Inventory → Slow Sales → Markdown → Replenishment → More Inventory → Additional Markdown → Waste

The analysis will examine product sales patterns, inventory levels, markdown activity, shelf life, and waste in order to identify
*different product behaviors, 

*such as fast-moving products,

*slow-moving products,

*markdown-dependent products, 

*products with recurring overstock.

## Dataset Creation and Preparation
I started with a reference table containing 45 bakery products, including SKU, product name, price, markdown price, and shelf life. Using Excel, I created a 1,000-row synthetic dataset without manual data entry.

The dataset was generated using Excel formulas rather than manually entering individual records. Functions such as RANDBETWEEN were used to generate variable values for inventory, deliveries, sales, markdown sales, and waste. XLOOKUP was used to automatically retrieve product-specific information, including SKU, product name, price, markdown price, and shelf life, from the original 45-product reference table.

The most challenging part was modeling Starting Inventory, because it needed to connect each product's previous Ending Inventory to its next Starting Inventory rather than being generated independently. I used a combination of formulas and XLOOKUP to carry inventory forward between records. The inventory calculation follows:

##### Starting Inventory + Deliveries − Sold − Markdown Sold − Waste = Ending Inventory

This approach created a connected inventory flow and allowed the 1,000-row dataset to be generated and updated automatically rather than through manual entry.
