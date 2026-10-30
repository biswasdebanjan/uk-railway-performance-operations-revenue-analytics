# DAX & Analytical Logic

The report uses DAX for business-facing KPIs, ranking logic, filtered calculations and analytical segmentation.

## Dynamic Top Revenue Route

```DAX
Top Revenue Route =
VAR T =
    TOPN(
        1,
        ADDCOLUMNS(
            VALUES('railway'[Route]),
            "Revenue", [Total Revenue]
        ),
        [Revenue],
        DESC
    )
RETURN
MAXX(T, 'railway'[Route])
```

## Dynamic Top Delay Reason

```DAX
Top Delay Reason =
VAR T =
    TOPN(
        1,
        ADDCOLUMNS(
            VALUES('railway'[Reason for Delay]),
            "Trips", [Total Trips]
        ),
        [Trips],
        DESC
    )
VAR Result =
    MAXX(T, 'railway'[Reason for Delay])
RETURN
IF(ISBLANK(Result), "All Data", Result)
```

## Average Refund Amount

```DAX
Avg Refund Amount =
AVERAGEX(
    FILTER(
        'railway',
        'railway'[Refund Request] = "Yes"
    ),
    'railway'[Price]
)
```

## Severe Delay Share

```DAX
Severe Delay % (of Delays) =
DIVIDE(
    CALCULATE(
        COUNTROWS('railway'),
        'railway'[Delay Status] = "Severe Delay (>60 mins)"
    ),
    CALCULATE(
        COUNTROWS('railway'),
        'railway'[Delay Status] <> "On Time"
    )
)
```

The README intentionally highlights only selected DAX logic that demonstrates meaningful analytical reasoning and is used in the report.
