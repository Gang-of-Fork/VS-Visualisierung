# Visualisierung

## Ausgabe der Simulation (json Format)
```
[
  {
    "type":"RREQ | RRES | DATA | RERR | ACK | RTU",
    "nodes": [
      {
        "x": number,
        "y": number,
        "id": string,
        "routingTable": [
          {
            "destination": string,
            "route": string
          }
        ],
        "inRange": [ string (NodeId) ]
      }
    ],
    
    //packet property is only set on type RREQ, RRES, DATA, RERR, ACK
    "packet": {
      "id": string,
      "dest": string,
      "sender": string,
      "source": string,
      "route": string,
      "type": string
    },
    
    //actions property is only set on type RREQ, RRES, DATA, RERR, ACK
    "actions" : {
      "sending": string (Node Id),
      "receiving_discarding": [ string (Node Id) ],
      "receiving_processing": [ string (Node Id) ],
    },
    
    //table_update property is only set on type RTU
    "table_update": {
      "type": "add | remove"
      "node": string (NodeId),
      "destination": string (NodeId),
      //route contains new route on add and old route on remove 
      "route": string
  }
]
```

