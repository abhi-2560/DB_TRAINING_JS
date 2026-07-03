For the query:


SELECT *
FROM bookings
WHERE doctor_id = ?
  AND appointment_date >= ?
  AND appointment_date <= ?;


### Proposed Composite Index

```
CREATE INDEX idx_bookings_doctor_date
ON bookings (doctor_id, appointment_date);
```


The order of columns in a composite index is important because the database uses the leftmost prefix rule. This means it first searches using the leftmost column and then uses the following columns.

* doctor_id is placed first because it is used with an equality (=) condition.
* appointment_date is placed second because it is used with a range condition (>= and <=).

### Why This Order?

1. **Equality columns should come first.**

   * The database quickly narrows the search to rows belonging to the specified doctor.
   * Equality conditions are highly selective and reduce the number of rows to examine.

2. **Range columns should come after equality columns.**

   * Once the matching doctor records are found, the index is scanned only for the required date range.
   * This avoids scanning appointments of other doctors.

3. **Improved Query Performance.**

   * The index allows efficient filtering by both doctor ID and appointment date.
   * It reduces disk I/O and minimizes the number of rows that need to be accessed.

### Answer :

The most appropriate composite index is:


CREATE INDEX idx_bookings_doctor_date
ON bookings (doctor_id, appointment_date);
