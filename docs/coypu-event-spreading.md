# coypu-event-spreading

Event spreading over neigbouring OpenStreetMaps relations based on event descriptions or structured event data.

Developed as a warning system wich checks for the possibility of spreading, rather than likelihood.

Spreading can be performed on one of these layers: Cities, Counties, States or Countries.

## Process overview
When an event text is submitted:

1. Event location tagging (optional)
    - Bert 
2. Entity link location to Wikidata (optional)
    - Falcon 2.0
3. Event type classification (optional)
    - Vicuna
4. Spread event based on attributes
    - via OpenStreetMaps borders 
    1. Linear spreading
        - based on prevous events in neighbourhood
        - next locations on continued trajectory
    2. Circular spreading
        - to all neighbours
6. Issue warning messages