# data_cleaning_tojson
This test was administered as part of a data ingestion job application.  
Files
- Customer sheet
- Route sheet
- Sample output
### Overview
-The task at hand is modeled on part of a common data ingestion workflow. A customer provides
us with two sources of data. One is their customer sheet, which has come from QuickBooks.
The second is their route sheet, which they have created in Excel. In order to ingest their data
into our system, we need to match the customer names in the route sheet against the customer
names in the customer sheet, and parse the data into a JSON object that can be passed to our
API.
### Objective
Using the two source files provided, implement the following logic:
- Match the route sheet against the customer sheet based on the “Customer” field in both
tables.
- Note: matching is case-insensitive.
- Only the top level customer from the QuickBooks customers export should be
matched against. For example, the top level customer in the QuickBooks
customer field “John Smith:123 Main Street” would be “John Smith”.
- For each unique customer name (case insensitive) in the route sheet, create an object
consisting of the following fields:
- From the customer sheet:
- Customer
- Bill to 1
- Bill to 2
- Bill to 3
- Main Phone
- Note: each phone number should be formatted to include only
numeric characters. For example “555-123-4567: Tracy” should
become “5551234567”.
- Main Email
- Terms
○ From the route sheet:
- An array of jobs, each with the fields:
- Job Name/Well Name,
- Address
- City
- Schedule
- Scheduled Day
- Charge Type
- TOILET #
- Return a JSON-formatted array of these objects
