# Glossary

### Summary

 - [Entity / Report Type](#entity--report-type)
 - [Interval](#interval)
 - [Operation](#operation)
 - [Comparison](#comparison)
 - [Field](#field)
 - [Report Columns](#report-columns)
 - [Report Conditions](#report-conditions)

<a id="entity--report-type"></a>
### Entity / Report Type
The main object of your report. Modig Report Builder comes out of the box with 3 predefined entities. To create reports on your custom entities please visit the [Creating a new report type](03-Developer-Guide.md#creating-a-new-report-type) section in the developer documentation.  

 - **Orders** - the actual orders placed on the website.
 - **Order Line Items** - the products ordered on the website.
 - **Customers** - Your website customers.

<a id="interval"></a>
### Interval 

Allows you to apply a quick date from-to filter for the entities you are creating a report.  
It is similar to creating 2 conditions `Created At less or equal with` and `Created At greater or equal to`.
An interval also allows to quickly get the same report for different periods of time at the time of the generation.
Modig Report Builder comes out of the box with predefined intervals. For adding new predefined intervals please visit the [Adding a new interval](03-Developer-Guide.md#adding-a-new-interval) section in the developer documentation.  

**Predefined Intervals**

- Specific interval - it allows you to select a date from and date to as you wish.
- Since The Big Bang - it does not apply a date filter to the entity creation date. You can still do it via conditions.
- Last 7 Days.
- Last 30 Days.
- Last 365 Days.
- Current week - Selects only the entities created in the current week, starting from Monday until today.
- Current Month - Selects only the entities created in the current month starting from the 1st.
- Current Year - Selects only the entities created starting January 1st of this year.
- Last week - Selects only the entities created from  Monday to Sunday previous week.
- Last month - Selects only the entities created from the 1st to last day (28, 29, 30, 31) of the previous month.
- Last Year - Selects only the entities created from January 1st to December 31st of last year.

<a id="operation"></a>
### Operation

Different operations can be applied to entity properties when generating the report. A good example would be if you want to retrieve the average of total paid for orders.

**Predefined Operations**
- minimum - applicable to integer and decimal fields;
- maximum - applicable to integer and decimal fields;
- average - applicable to integer and decimal fields;
- sum - applicable to integer and decimal fields
- count - applicable to all fields;
- year - applicable to date-time  fields;
- month - applicable to date-time  fields;
- day - applicable to date-time  fields;
- hour - applicable to date-time  fields;
- minute - applicable to date-time  fields;
- second - applicable to date-time  fields;
- day of week - applicable to date-time  fields.

For adding other operations, visit the [Creating a new operation](03-Developer-Guide.md#creating-a-new-operation) section in the developer documentation.

<a id="comparison"></a>
### Comparison

When creating a filter for your report, you can apply different comparisons between fields and specific values. 

Depending on the field type, you can apply different options to compare the value of the field with desired values.

**Predefined comparisons**

- Equals
- Does not equal
- Greater than
- Greater than or equals
- Less than
- Less than or equals
- Is one of
- Is not one of
- Is set
- Is not set
- Contains
- Does not contain
- Starts with
- Does not start with
- Ends with
- Does not end with

For adding custom comparisons, visit the [Creating a new comparison](03-Developer-Guide.md#creating-a-new-comparison) developer documentation

<a id="field"></a>
### Field

The fields, are the elements in database tables on which you can create reports.   
The fields are table columns for each entity but can also be calculated based on other fields (experimental feature!).  
The fields can be included in the report results or in the report conditions.
The fields are defined for each report type.  

*Examples*

For an order the fields can be:

- Total amount
- Net amount
- Order number
- Order bulling address country
- ….

For customers the fields can be:

- First name
- Last name
- Default billing address country
- ….

Each field can have a different type, based on the type of the table column or the calculation result. Based on this type, different operations can be applied in the report columns and different comparisons can be applied in the report conditions  
For adding extra fields, visit the [Field Types config](03-Developer-Guide.md#field-types-config) section in the developer guide

<a id="report-columns"></a>
### Report Columns

A report column represents values displayed in the report.

A column consists of the following:
- One Field - mandatory.
- Label - can be empty. if empty, it will be autogenerated.
- One Operation. It can be empty.
- “Group by this“ checkbox - determines if the results are grouped by the selected field.
- Sort - determines if the results are sorted by the selected field.

You can add as many columns as you wish. You can even add different columns for the same field with different operations applied to it.

<a id="report-conditions"></a>
### Report conditions

A condition is a filter on the data on which you build the report.

There are 2 types of conditions:
- Regular condition composed of: 
  - one Field - mandatory;
  - one comparison - mandatory;
  - one value (might be missing for certain comparison types).

- Aggregate conditions:
  - One group of regular conditions where they all need to be true (AND condition) or at least one needs to be true (OR condition).


