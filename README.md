# End-to-end-data-pipeline-with-data-bricks-in-FMCG-domain

**Atlon**, an established sports equipment manufacturer with mature, structured ERP systems, has recently acquired **Sports Bar**, a fast-growing startup in the athletic nutrition space.
The core problem is the immediate need for a unified and reliable source of business intelligence across the two merged entities. Atlon’s decision to retain Sports Bar’s existing culture and processes has resulted in severe data chaos because Sports Bar's data is fragmented across disparate, unreliable sources (spreadsheets, cloud drives, WhatsApp exports, and hostily built APIs).

## Objective

* Build a consolidated data solution merging the existing ERP system’s data of the parent company and the newly acquired child company for all historical records.
* Create a data pipeline that ingests, cleans, transforms, and loads new raw data into a consolidated data warehouse.
* Automate the incremental data ingestion pipeline with logs and crash alerts, along with daily scheduled runs.

## Data Transformation obstacles encountered and handled:

> ### 1. Misspelled City Names

<img width="1139" height="562" alt="Misspelled CIties" src="https://github.com/user-attachments/assets/845eb345-abe3-4e97-a2ba-f622e43c3230" />

*used data mapping to achieve this*

> ### 2. Non Standard Date Formats

<img width="1139" height="562" alt="Date Standardization" src="https://github.com/user-attachments/assets/d0e98d68-300a-416f-be37-a6b349f77c65" />

*used regex and string formatting*

> ### 3. Resolved conflicts in dimensions of child dim_customer and parent dim_customer table
> 
> #### •	Added 3 static fields as per cross team consultations and verifications, as child company customers remain similar across these fields
>

<img width="940" height="374" alt="image" src="https://github.com/user-attachments/assets/e5b3450e-6ea9-4209-9119-c4ed79b755c3" />

> ### 4. Standardized Product attributes of child table to suit the parent data model
> 
> #### •	Added Division and Category fields as per business input
> #### •	Extracted Variant from product name using regex
> #### •	Added a product code using Sha algorithm from product name (not shown in this showcase as the code is lengthy)
> 
<img width="940" height="403" alt="image" src="https://github.com/user-attachments/assets/7e9247fb-b157-4ed5-a94f-dd302639ed09" />

> ### 5. Other Data Transformations
> 
> #### * Aggregated the Orders table to conform to the parent company’s data granularity
> #### * Handled Invalid Numbers
> #### * Droped Duplicates
> #### * Trimmed leading and trailing spaces
> #### * Normalised Casing 
> #### * Account for missing customer names and product info
> #### * Standardized misspelled words

## Data Model of Child Company:

<img width="1360" height="776" alt="Child Model" src="https://github.com/user-attachments/assets/b1530c22-db00-4b25-976a-0f50f422ee05" />

## Data Model Of Parent Company:

<img width="1334" height="798" alt="Parent Model" src="https://github.com/user-attachments/assets/c447b245-d62c-46ef-b10e-0c7d4952e5ff" />

## Data Pipeline Architecture:

<img width="1549" height="798" alt="Data Pipeline" src="https://github.com/user-attachments/assets/2d42af0b-2938-4c54-b115-2a3c602bbecb" />


