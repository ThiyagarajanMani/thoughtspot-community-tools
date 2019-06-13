# thoughtspot-community-tools
This repository maintains the bug fixes of thoughtspot provided community tools. 

#### Issue #1: 
convert_ddl.py missing columns that has the word "key" while generating the excel sheet from DDL

For example: DDL Extracted from existing RDBMS,

CREATE TABLE edw_product_d (
product_edw_key NUMBER(10),
product_code  VARCHAR2(28),
product_sku VARCHAR2(60),
..
);

ALTER TABLE edw_product_d ADD CONSTRAINT edw_product_d_pk PRIMARY KEY (product_edw_key);

Excel output generated for the above DDL script is missing the column product_edw_key, that subsequently missing the column TQL generation.

#### Cause: 
Code for "Ignore Key Declarations" of add_columns function in datamodelio.py
#### Status: 
Fixed


