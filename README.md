# get-out
A base frame for measuring/analyzing in and outs. It's kind of a people counting software.

# charts
- line chart of strength at time(minute/hour wise)
- bar chart of month(each day people count - days window)
- bar chart of year(each month people count - months window)
- bar chart of onlys INs/OUTs(minute/hour wise)
- custom chart of current capacity percentage

# APIs
#### add location:
[POST] /location <br>
Body: {location_name, capacity, desc, gates = {`[gate_name, used_for, desc]}} <br>
Return: {location_id, gates = {[gate_name, gate_id]}

#### add record:
[POST] /record <br>
Body: {location_id, gate_id, entry_type, timestamp} <br>
Return: {record_id}


# entries info
each location_id will be a collection and each collection will have following:<br>
[
  {
    "timestamp_minute_1": {
      "tot_ins": "count",
      "tot_outs": "count",
      "records": [
        {
          "entry_id": "id",
          "gate_id": "gate id",
          "entry_type": "entry/exit",
          "timestamp": "timestamp"
        },
        {
          "entry_id": "id",
          "gate_id": "gate id",
          "entry_type": "entry/exit",
          "timestamp": "timestamp"
        }
      ]
    }
  },
  {
    "timestamp_minute_2": {
      "tot_ins": "count",
      "tot_outs": "count",
      "records": [
        {
          "entry_id": "id",
          "gate_id": "gate id",
          "entry_type": "exit",
          "timestamp": "timestamp"
        }
      ]
    }
  }
]


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
