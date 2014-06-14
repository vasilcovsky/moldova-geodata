moldova-geodata
===============

GPS coordinates in CSV format mapped to Moldova's zip codes & cities.

Format: 
  * zip code
  * city name
  * latitude
  * longitude

Bonus
===============
The following code returns distance in km for 2 GPS points: 

```
function distance(point1, point2) {
    var R = 6371,
        rad = function(r) { return r * Math.PI / 180; },
        f1 = rad(point1[0]),
        f2 = rad(point2[0]),
        df = rad(point2[0]-point1[0]),
        dl = rad(point2[1]-point1[1]),
        a = Math.pow(Math.sin(df/2), 2) +
            Math.cos(f1) * Math.cos(f2) *
            Math.pow(Math.sin(dl/2), 2),
        c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a));

    return R * c;
}

var chisinau = [47.00560, 28.85750];
var cahul = [45.90750, 28.19444];
var km = distance(chisinau, cahul);
console.log('Distance: ' + km + ' km.');  // Distance: 132 km 
```
