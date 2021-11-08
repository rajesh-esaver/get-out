# get-out
A base frame for in and outs.

# charts
- line chart of day(entries count - time window)
- bar chart of month(each day count - days window)
- bar chart of year(each month count - months window)

# entries info
{
  "location_id": [
    {
      "id": "id",
      "location_id": "location id",
      "gate_id": "gate id",
      "entry_type": "entry/exit",
      "timestamp": "timestamp"
    },
    {
      "id": "id",
      "location_id": "location id1",
      "gate_id": "gate id",
      "entry_type": "exit",
      "timestamp": "timestamp"
    }
  ]
}

# locations schema
{
  "locations": [
    {
      "id": "id",
      "name": "location name",
      "desc": "descrption",
      "capacity": 100,
      "gates": [
        {
          "id": "id",
          "name": "gate name",
          "desc": "descrption",
          "used_for": "entry/exit"
        },
        {
          "id": "id",
          "name": "gate name 1",
          "desc": "descrption",
          "used_for": "entry/exit"
        }
      ]
    },
    {
      "id": "id",
      "name": "location name1",
      "desc": "descrption",
      "capacity": 1000,
      "gates": [
        {
          "id": "id",
          "name": "gate name",
          "desc": "descrption",
          "used_for": "entry"
        },
        {
          "id": "id",
          "name": "gate name 1",
          "desc": "descrption",
          "used_for": "entry_and_exit"
        }
      ]
    }
  ]
}
