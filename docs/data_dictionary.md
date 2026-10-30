# Data Dictionary

Source: `data/railway.csv`

**Grain:** one record per journey. 31,653 source records.

| Field | Description |
|---|---|
| Transaction ID | Unique journey transaction identifier |
| Date of Purchase | Ticket purchase date |
| Time of Purchase | Ticket purchase time |
| Purchase Type | Purchase channel/type |
| Payment Method | Payment method used |
| Railcard | Railcard category |
| Ticket Class | Standard or First Class |
| Ticket Type | Ticket category |
| Price | Ticket price / revenue value |
| Departure Station | Journey origin |
| Arrival Destination | Journey destination |
| Date of Journey | Journey date |
| Departure Time | Scheduled departure time |
| Arrival Time | Scheduled arrival time |
| Actual Arrival Time | Actual arrival time |
| Journey Status | Journey outcome/status |
| Reason for Delay | Operational reason where applicable |
| Refund Request | Whether a refund was requested |

### Derived analytical fields in Power BI

- Route
- Advance Booking Days
- Booking Type
- Refund Flag
- On-Time % Flag
- Journey Status interpretation
- Delay (Minutes)
- Delay Status
- Time Bucket
