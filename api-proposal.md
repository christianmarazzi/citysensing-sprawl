#citysensing 2.0 API PROPOSAL (static files)

###Time framing
8 daily updates, 1 per 3 hour span.
For each 3 hour span data is aggregated every 15 minutes.

**Geograpic view**
----

###City zoom
---
####Social activity timeline

Returns json data about the amount of tweets (and/or other sources) in a 3 hour span.

######HTTP REQUEST

`GET http://api.citysensing.org/v1/geo/city/social_activity/timeline`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 3h span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'timeline':
    [
      { 'date' : 1433314800000, 'value' : 208 },
      { 'date' : 1433315700000, 'value' : 302 },
      { 'date' : 1433316600000, 'value' : 150 },
      ...
    ]
}
```
---
####Calls timeline

  Returns json data about the amount of calls in a 3 hour span.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/city/calls/timeline`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 3h span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'timeline':
    [
      { 'date' : 1433314800000, 'value' : 1008 },
      { 'date' : 1433315700000, 'value' : 2032 },
      { 'date' : 1433316600000, 'value' : 2404 },
      ...
    ]
}
```
---
####Social activity

  Returns json data about the social activity [0,1] inside all the cells in a 15 minute time span.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/city/social_activity/cells`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15 minute span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433315700000,
  'timeline':
    [
      { 'cellId' : 1, 'value' : 0.0 },
      { 'cellId' : 2, 'value' : 0.4 },
      { 'cellId' : 3, 'value' : 1 },
      ...
    ]
}
```
---
####Calls anomaly

  Returns json data about the calls anomaly [0,1] inside all the cells in a 15 minute time span.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/city/calls_anomaly/cells`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15 minute span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433315700000,
  'timeline':
    [
      { 'cellId' : 1, 'value' : 0.0 },
      { 'cellId' : 2, 'value' : 0.4 },
      { 'cellId' : 3, 'value' : 1 },
      ...
    ]
}
```
---
####General stats

  Returns json data about general statistics in a 15 minute time span.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/city/general_stats`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15 minute span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433315700000,
  'totPosts': 2346,
  'topSocialNil': 'Duomo',
  'topSocialCellId': 2,
  'topAnomalyNil': 'Lambrate'
}
```
---


###EXPO area zoom
---
####Social activity timeline

  Returns json data about the amount of tweets (and/or other sources) in a 3 hour span.

  ######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/expo/social_activity/timeline`

  ######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 3h span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'timeline':
    [
      { 'date' : 1433314800000, 'value' : 208 },
      { 'date' : 1433315700000, 'value' : 302 },
      { 'date' : 1433316600000, 'value' : 150 },
      ...
    ]
}
```
---
####Checkins timeline

  Returns json data about the amount of checkins in a 3 hour span related to the EXPO venues.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/expo/checkins/timeline`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 3h span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'timeline':
    [
      { 'date' : 1433314800000, 'value' : 1008 },
      { 'date' : 1433315700000, 'value' : 2032 },
      { 'date' : 1433316600000, 'value' : 2404 },
      ...
    ]
}
```
---
####Social Activity

  Returns json data about every single georeferenced tweets (or other sources) in a 15 minutes span.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/expo/social_activity/posts`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 3h span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'posts':
    [
      { 'type' : tweet, 'lat' : 45.3920, lon: 9.3248 },
      { 'type' : tweet, 'lat' : 45.4039, lon: 9.4439 },
      { 'type' : instagram, 'lat' : 45.4039, lon: 9.4439 },
      ....
    ]
}
```
---
####Checkins Activity

  Returns json data about checkins inside the Expo venues in a 15 minutes span.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/expo/checkins/venues`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 3h span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'posts':
    [
      { 'venueId' : 29384, 'value' : 20, 'venueName' : 'Padiglione Italia' },
      { 'venueId' : 94382, 'value' : 520, 'venueName' : 'Decumano' },
      { 'venueId' : 10388, 'value' : 59, 'venueName' : 'Cluster mediterraneo' },
      ....
    ]
}
```
---
####General stats

  Returns json data about general statistics in a 15 minute time span.

######HTTP REQUEST

  `GET http://api.citysensing.org/v1/geo/expo/general_stats`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15 minute span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433315700000,
  'totPosts': 2346,
  'topSocialVenue': 'Padiglione Italia',
  'topCheckins': 2382,
  'topCheckinsVenueId': 37374,
  'topCheckinsVenueName': 'Decumano',
}
```
---

**Network view**
----

###City zoom
---
####Graph

  Returns json data about the graph in a 15 minutes span.

  ######HTTP REQUEST

  `GET http://api.citysensing.org/v1/network/city/graph`

  ######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15m span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'nodes':
    [
      { 'name' : 'expo', 'type' : 'cluster' },
      { 'name' : '#food', 'type' : 'entity' },
      { 'name' : '@secolourbano', 'type' : 'user' },
      ...
    ],
  'links':
    [
      { 'source' : 1, 'target' : 3, value: 0.1 },
      { 'source' : 23, 'target' : 3, value: 0.5 },
      { 'source' : 3, 'target' : 10, value: 1 },
      ...
    ]
}
```
---
####Top users

  Returns json data about the top users in a 15 minutes span.

  ######HTTP REQUEST

  `GET http://api.citysensing.org/v1/network/city/users`

  ######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15m span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'users':
    [
      { 'name' : '@expo2015milano', 'value' : 23, 'cluster':'expo' },
      { 'name' : '@triennale', 'value' : 2, 'cluster':'#food' },
      { 'name' : '@secolourbano', 'value' : 45, 'cluster':'expo' },
      ...
    ]
}
```
---

###EXPO area zoom
---
####Graph

  Returns json data about the graph in a 15 minutes span.

  ######HTTP REQUEST

  `GET http://api.citysensing.org/v1/network/expo/graph`

  ######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15m span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'nodes':
    [
      { 'name' : 'expo', 'type' : 'cluster' },
      { 'name' : '#food', 'type' : 'entity' },
      { 'name' : '@secolourbano', 'type' : 'user' },
      ...
    ],
  'links':
    [
      { 'source' : 1, 'target' : 3, value: 0.1 },
      { 'source' : 23, 'target' : 3, value: 0.5 },
      { 'source' : 3, 'target' : 10, value: 1 },
      ...
    ]
}
```
---
####Top users

Returns json data about the top users in a 15 minutes span.

######HTTP REQUEST

`GET http://api.citysensing.org/v1/network/expo/users`

######QUERY PARAMETERS

|Parameter|Type|Default|Description|
|---|---|---|---|
|startDate|int (millisec)|`1433314800000`|start date of the 15m span

######SUCCESS RESPONSE:

```
{
  'startDate':1433314800000,
  'endDate':1433322000000,
  'users':
    [
      { 'name' : '@expo2015milano', 'value' : 23, 'cluster':'expo' },
      { 'name' : '@triennale', 'value' : 2, 'cluster':'#food' },
      { 'name' : '@secolourbano', 'value' : 45, 'cluster':'expo' },
      ...
    ]
}
```
---