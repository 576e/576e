# HYPERPC · Sales & Customer Analytics

[← Back to profile](../README.md)

**Power BI · Power Query · DAX · RFM · ABC Analysis**

## Objective

Bring sales, customer, and product analysis together in a report that lets users move from overall trends to individual segments and products.

## My Contribution

During my internship at Paper Planes, I independently prepared sales and customer data, built the data model, and developed visualizations and DAX measures, including revenue per customer and RFM segmentation.

## Current Report

| Section | Analysis |
| :--- | :--- |
| Business overview | Revenue, sales documents, customers, average document value, and period comparisons |
| Sales and documents | Sales trends and the relationship between sales documents and customer orders |
| Customers and behavior | Repeat purchases within the selected period and returning customers from the previous period |
| Products and concentration | Revenue by product, the Top 10 SKU share, and ABC classes |
| Data quality and definitions | Identifier completeness, zero-value rows, and metric definitions |

## DAX Example

The model identifies a sales document by its type and number. This distinguishes documents that share a number but have different types. The example below retains the original model's table, column, and measure names.

```dax
BI Документы продаж =
COUNTROWS(
    SUMMARIZE(
        'Таблица продаж',
        'Таблица продаж'[Тип документа ],
        'Таблица продаж'[Номер док.продаж]
    )
)

BI AOV документа =
DIVIDE([BI Выручка], [BI Документы продаж])
```

## Metric Definitions

- **Revenue per customer** is revenue divided by the number of customers in the selected context. Originally labeled LTV in the model, it represents a historical average rather than a prediction of lifetime customer value.
- **Repeat customers within a period** have two or more sales documents in the selected period. This differs from retention between periods.
- The current report counts customers by name, so identical names may affect the results. The data status also notes that sales have not yet been reconciled against the primary source.

## Outcome

An analytical report connecting headline KPIs with customer behavior, product performance, and data quality checks. It supports trend exploration and hypothesis development; it does not measure the causal impact of business decisions.

This case study includes the project approach and example calculations, without the underlying customer data.
