# NHL API

## Introduction

**NHL API** provides instant access to the latest data for all operations and players in the NHL. It features scores, odds, bookmakers' stats, standings, and historical data.

## Authentication

The URL you need to use is the following: `https://nhl-api5.p.rapidapi.com/`
The API requires the headers listed below:

- **`x-rapidapi-host`**: `nhl-api5.p.rapidapi.com`
- **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/nhl-api5/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

## Endpoints

The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

### 1. **`GET /nhlsummary`**

- **Description**: Retrieves the game summary data for a specific NHL game.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
|   `id`    | string | -       | The unique identifier for the NHL game | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlsummary?id=401559988', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "boxScore": {
    "teams": [
      {
        "team": {
          "id": "1",
          "uid": "s:70~l:90~t:1",
          "slug": "boston-bruins",
          "location": "Boston",
          "name": "Bruins",
          "abbreviation": "BOS",
          "displayName": "Boston Bruins",
          "shortDisplayName": "Bruins",
          "color": "000000",
          "alternateColor": "fdbb30",
          "logo": "https://a.espncdn.com/i/teamlogos/nhl/500/bos.png"
        },
        "statistics": [
          {
            "name": "blockedShots",
            "abbreviation": "BS",
            "displayValue": "20",
            "label": "Blocked Shots"
          },
          {
            "name": "hits",
            "abbreviation": "HT",
            "displayValue": "19",
            "label": "Hits"
          },
          ...
```

### 2. **`GET /nhlteamplayers`**

- **Description**: Retrieves the list of players for a specific NHL team.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `teamid`  | string | -       | The unique identifier for the NHL team | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlteamplayers?teamid=17', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "team": {
    "id": "17",
    "uid": "s:70~l:90~t:17",
    "slug": "colorado-avalanche",
    "location": "Colorado",
    "name": "Avalanche",
    "nickname": "Avalanche",
    "abbreviation": "COL",
    "displayName": "Colorado Avalanche",
    "shortDisplayName": "Avalanche",
    "color": "860038",
    "alternateColor": "005ea3",
    "isActive": true,
    "logos": [
      {
        "href": "https://a.espncdn.com/i/teamlogos/nhl/500/col.png",
        "width": 500,
        "height": 500,
        "alt": "",
        "rel": [
          "full",
          "default"
        ],
        "lastUpdated": "2024-07-02T15:51Z"
      },
      {
        "href": "https://a.espncdn.com/i/teamlogos/nhl/500-dark/col.png",
        "width": 500,
        "height": 500,
        ...
```

### 3. **`GET /nhlpicks`**

- **Description**: Retrieves the PickCenter data for a specific NHL game.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
|   `id`    | string | -       | The unique identifier for the NHL game | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlpicks?id=401559988', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "id": 401559988,
  "gameInfo": {
    "venue": {
      "id": "1845",
      "fullName": "Wells Fargo Center",
      "address": {
        "city": "Philadelphia",
        "state": "PA",
        "zipCode": "19255",
        "country": "USA"
      },
      "grass": false,
      "images": [
        {
          "href": "https://a.espncdn.com/i/venues/nhl/day/1845.jpg",
          "width": 2000,
          "height": 1125,
          "alt": "",
          "rel": [
            "full",
            "day"
          ]
        }
      ]
    },
    "attendance": 19276,
    "officials": [
      {
        "fullName": "David Brisebois",
        ...
```

### 4. **`GET /injuries`**

- **Description**: Retrieves the current season's NHL injuries.

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/injuries', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "timestamp": "2024-10-29T11:20:21Z",
  "status": "success",
  "season": {
    "year": 2025,
    "type": 2,
    "name": "Regular Season",
    "displayName": "2024-25"
  },
  "injuries": [
    {
      "id": "25",
      "displayName": "Anaheim Ducks",
      "injuries": [
        {
          "id": "536313",
          "longComment": "Gibson has missed the first few weeks of the regular season while recovering from an appendectomy, but he appears to be closing in on a return. While it's not yet clear when he could be back in game action, it's encouraging that he'll travel with the team for the upcoming four-game road trip. Once Gibson is able to return, he'll likely compete with Lukas Dostal for the starting goaltender job.",
          "shortComment": "Head coach Greg Cronin said Monday that he anticipates Gibson (abdomen) accompanying the Ducks on their upcoming road trip, which begins Saturday against the Rangers, Derek Lee of The Hockey News reports.",
          "status": "Injured Reserve",
          "date": "2024-10-21T19:47Z",
          "athlete": {
            "firstName": "John",
            "lastName": "Gibson",
            "displayName": "John Gibson",
            "shortName": "J. Gibson",
            "links": [
              {
                "language": "en-US",
                "rel": [
                  "playercard",
                  ...
```

### 5. **`GET /nhlteamlist`**

- **Description**: Retrieves the list of all NHL teams and their identification information.

| Parameter | Type   | Default | Description                             | Required |
|-----------|--------|---------|-----------------------------------------|----------|
| `limit`   | string | `400`   | The maximum number of results to return | No       |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlteamlist', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "sports": [
    {
      "id": "70",
      "uid": "s:70",
      "name": "Ice Hockey",
      "slug": "hockey",
      "leagues": [
        {
          "id": "90",
          "uid": "s:70~l:90",
          "name": "National Hockey League",
          "abbreviation": "NHL",
          "shortName": "NHL",
          "slug": "nhl",
          "teams": [
            {
              "team": {
                "id": "25",
                "uid": "s:70~l:90~t:25",
                "slug": "anaheim-ducks",
                "abbreviation": "ANA",
                "displayName": "Anaheim Ducks",
                "shortDisplayName": "Ducks",
                "name": "Ducks",
                "nickname": "Anaheim",
                "location": "Anaheim",
                "color": "fc4c02",
                "alternateColor": "000000",
                "isActive": true,
                ...
```

### 6. **`GET /nhlteaminfo`**

- **Description**: Retrieves the information for a specific NHL team.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `teamid`  | string | -       | The unique identifier for the NHL team | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlteaminfo?teamid=17', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "team": {
    "id": "17",
    "uid": "s:70~l:90~t:17",
    "slug": "colorado-avalanche",
    "location": "Colorado",
    "name": "Avalanche",
    "nickname": "Avalanche",
    "abbreviation": "COL",
    "displayName": "Colorado Avalanche",
    "shortDisplayName": "Avalanche",
    "color": "860038",
    "alternateColor": "005ea3",
    "isActive": true,
    "logos": [
      {
        "href": "https://a.espncdn.com/i/teamlogos/nhl/500/col.png",
        "width": 500,
        "height": 500,
        "alt": "",
        "rel": [
          "full",
          "default"
        ],
        "lastUpdated": "2024-07-02T15:51Z"
      },
      {
        "href": "https://a.espncdn.com/i/teamlogos/nhl/500-dark/col.png",
        "width": 500,
        "height": 500,
        ...
```

### 7. **`GET /nhlstandings`**

- **Description**: Retrieves the NHL team standings of a specific year.

| Parameter | Type   | Default | Description                                                                        | Required |
|-----------|--------|---------|------------------------------------------------------------------------------------|----------|
| `year`    | string | -       | The year of the standings (YYYY)                                                   | Yes      |
| `group`   | string | -       | The group to retrieve the standings for (e.g., 'league', 'conference', 'division') | No       |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlstandings?year=2022', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "uid": "s:70~l:90~g:9",
  "id": "9",
  "name": "National Hockey League",
  "abbreviation": "NHL",
  "standings": {
    "id": "1",
    "name": "expanded",
    "displayName": "Expanded Standings",
    "links": [
      {
        "language": "en-US",
        "rel": [
          "standings",
          "desktop"
        ],
        "href": "https://www.espn.com/nhl/standings/_/group/9",
        "text": "Table",
        "shortText": "Standings",
        "isExternal": false,
        "isPremium": false
      }
    ],
    "season": 2022,
    "seasonType": 2,
    "seasonDisplayName": "2021-22",
    "entries": [
      {
        "team": {
          "id": "26",
          ...
```

### 8. **`GET /nhlscoreboard`**

- **Description**: Retrieves the NHL scoreboard data for a specific date.

| Parameter | Type   | Default | Description                             | Required |
|-----------|--------|---------|-----------------------------------------|----------|
| `year`    | string | -       | The year of the scoreboard (YYYY)       | Yes      |
| `month`   | string | -       | The month of the scoreboard (MM)        | Yes      |
| `day`     | string | -       | The day of the scoreboard (DD)          | Yes      |
| `limit`   | string | `200`   | The maximum number of results to return | No       |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlscoreboard?year=2022&month=05&day=11&limit=100', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "leagues": [
    {
      "id": "90",
      "uid": "s:70~l:90",
      "name": "National Hockey League",
      "abbreviation": "NHL",
      "slug": "nhl",
      "season": {
        "year": 2022,
        "startDate": "2021-07-21T07:00Z",
        "endDate": "2022-07-01T06:59Z",
        "displayName": "2021-22",
        "type": {
          "id": "2",
          "type": 2,
          "name": "Regular Season",
          "abbreviation": "reg"
        }
      },
      "logos": [
        {
          "href": "https://a.espncdn.com/i/teamlogos/leagues/500/nhl.png",
          "width": 500,
          "height": 500,
          "alt": "",
          "rel": [
            "full",
            "default"
          ],
          ...
```

### 9. **`GET /news`**

- **Description**: Retrieves the latest NHL news.

| Parameter | Type   | Default | Description                                       | Required |
|-----------|--------|---------|---------------------------------------------------|----------|
| `limit`   | string | `40`    | The maximum number of news articles to return     | No       |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/news?limit=30', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "description": "With 20 days in the books, our panelists revisit preseason predictions and identify how many players will eclipse 100 points this season.",
    "headline": "NHL insiders debate Jets' early keys, preseason predictions",
    "link": "https://www.espn.com/nhl/story/_/id/42057850/nhl-2024-25-jets-perfect-standings-predictions-best-moments",
    "images": [
      "https://a.espncdn.com/photo/2024/1028/r1407272_1296x729_16-9.jpg",
      "https://a.espncdn.com/media/motion/2024/1027/ss_20241027_211834756_26759131283/ss_20241027_211834756_26759131283.jpg"
    ],
    "published": "2024-10-29T11:01:56Z",
    "premium": false,
    "lastModified": "2024-10-29T11:01:52Z",
    "categories": [
      {
        "id": 9580,
        "description": "NHL",
        "type": "league",
        "sportId": 90,
        "leagueId": 90,
        "createDate": "2024-10-29T11:00:00Z"
      },
      {
        "id": 91961,
        "description": "Winnipeg Jets",
        "type": "team",
        "sportId": 90,
        "leagueId": "",
        "createDate": "2024-10-29T11:00:00Z"
      },
      {
        ...
```

### 10. **`GET /nhlsbox`**

- **Description**: Retrieves the box score data for a specific NHL game.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `id`      | string | -       | The unique identifier for the NHL game | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlsbox?id=401559988', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "teams": [
    {
      "team": {
        "id": "1",
        "uid": "s:70~l:90~t:1",
        "slug": "boston-bruins",
        "location": "Boston",
        "name": "Bruins",
        "abbreviation": "BOS",
        "displayName": "Boston Bruins",
        "shortDisplayName": "Bruins",
        "color": "000000",
        "alternateColor": "fdbb30",
        "logo": "https://a.espncdn.com/i/teamlogos/nhl/500/bos.png"
      },
      "statistics": [
        {
          "name": "blockedShots",
          "abbreviation": "BS",
          "displayValue": "20",
          "label": "Blocked Shots"
        },
        {
          "name": "hits",
          "abbreviation": "HT",
          "displayValue": "19",
          "label": "Hits"
        },
        {
          ...
```

### 11. **`GET /nhlplay`**

- **Description**: Retrieves the play-by-play data for a specific NHL game.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `id`      | string | -       | The unique identifier for the NHL game | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlplay?id=401458986', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "teams": [
    {
      "id": "1",
      "uid": "s:70~l:90~t:1",
      "order": 0,
      "homeAway": "home",
      "winner": false,
      "team": {
        "id": "1",
        "uid": "s:70~l:90~t:1",
        "location": "Boston",
        "name": "Bruins",
        "nickname": "Bruins",
        "abbreviation": "BOS",
        "displayName": "Boston Bruins",
        "color": "000000",
        "alternateColor": "fdbb30",
        "logos": [
          {
            "href": "https://a.espncdn.com/i/teamlogos/nhl/500/bos.png",
            "width": 500,
            "height": 500,
            "alt": "",
            "rel": [
              "full",
              "default"
            ],
            "lastUpdated": "2024-07-02T15:51Z"
          },
          ...
```

### 12. **`GET /players/id`**

- **Description**: Retrieves the player IDs for a specific NHL team.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `teamId`  | string | -       | The unique identifier for the NHL team | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/players/id?teamId=16', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "data": [
    {
      "playerId": "3096237",
      "firstName": "Noel",
      "lastName": "Acciari",
      "fullName": "Noel Acciari",
      "displayName": "Noel Acciari",
      "shortName": "N. Acciari",
      "link": "https://www.espn.com/nhl/player/_/id/3096237"
    },
    {
      "playerId": "3904107",
      "firstName": "Anthony",
      "lastName": "Beauvillier",
      "fullName": "Anthony Beauvillier",
      "displayName": "Anthony Beauvillier",
      "shortName": "A. Beauvillier",
      "link": "https://www.espn.com/nhl/player/_/id/3904107"
    },
    {
      "playerId": "4697455",
      "firstName": "Joel",
      "lastName": "Blomqvist",
      "fullName": "Joel Blomqvist",
      "displayName": "Joel Blomqvist",
      "shortName": "J. Blomqvist",
      "link": "https://www.espn.com/nhl/player/_/id/4697455"
    },
    {
      ...
```

### 13. **`GET /team/id`**

- **Description**: Retrieves the team IDs for the NHL.

| Parameter | Type   | Default | Description                              | Required |
|-----------|--------|---------|------------------------------------------|----------|
| `limit`   | string | `100`   | The maximum number of team IDs to return | No       |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/team/id?limit=100', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
[
  {
    "teamId": "25",
    "displayName": "Anaheim Ducks",
    "shortDisplayName": "Ducks",
    "abbreviation": "ANA",
    "slug": "anaheim-ducks",
    "link": "https://www.espn.com/nhl/team/_/name/ana/anaheim-ducks"
  },
  {
    "teamId": "1",
    "displayName": "Boston Bruins",
    "shortDisplayName": "Bruins",
    "abbreviation": "BOS",
    "slug": "boston-bruins",
    "link": "https://www.espn.com/nhl/team/_/name/bos/boston-bruins"
  },
  {
    "teamId": "2",
    "displayName": "Buffalo Sabres",
    "shortDisplayName": "Sabres",
    "abbreviation": "BUF",
    "slug": "buffalo-sabres",
    "link": "https://www.espn.com/nhl/team/_/name/buf/buffalo-sabres"
  },
  {
    "teamId": "3",
    "displayName": "Calgary Flames",
    "shortDisplayName": "Flames",
    "abbreviation": "CGY",
    ...
```

### 14. **`GET /nhlschedule`**

- **Description**: Retrieves the NHL schedule data for a specific date.

| Parameter | Type   | Default | Description                           | Required |
|-----------|--------|---------|---------------------------------------|----------|
| `year`    | string | -       | The year of the schedule (YYYY)       | Yes      |
| `month`   | string | -       | The month of the schedule (MM)        | Yes      |
| `day`     | string | -       | The day of the schedule (DD)          | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/nhlschedule?year=2022&month=05&day=11', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "20220511": {
    "calendar": [
      "2021-07-21T07:00Z",
      "2021-07-22T07:00Z",
      "2021-07-23T07:00Z",
      "2021-07-24T07:00Z",
      "2021-07-25T07:00Z",
      "2021-07-26T07:00Z",
      "2021-07-27T07:00Z",
      "2021-07-28T07:00Z",
      "2021-07-29T07:00Z",
      "2021-07-30T07:00Z",
      "2021-07-31T07:00Z",
      "2021-08-01T07:00Z",
      "2021-08-02T07:00Z",
      "2021-08-03T07:00Z",
      "2021-08-04T07:00Z",
      "2021-08-05T07:00Z",
      "2021-08-06T07:00Z",
      "2021-08-07T07:00Z",
      "2021-08-08T07:00Z",
      "2021-08-09T07:00Z",
      "2021-08-10T07:00Z",
      "2021-08-11T07:00Z",
      "2021-08-12T07:00Z",
      "2021-08-13T07:00Z",
      "2021-08-14T07:00Z",
      "2021-08-15T07:00Z",
      "2021-08-16T07:00Z",
      ...
```

### 15. **`GET /schedule-team`**

- **Description**: Retrieves the schedule for a specific NHL team and season.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `season`  | string | -       | The season for the schedule (YYYY)     | Yes      |
| `teamId`  | string | -       | The unique identifier for the NHL team | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/schedule-team?season=2023&teamId=16', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "requestedSeason": {
    "year": 2023,
    "type": 2,
    "name": "Regular Season",
    "displayName": "2022-23"
  },
  "team": {
    "id": "16",
    "abbreviation": "PIT",
    "location": "Pittsburgh",
    "name": "Penguins",
    "displayName": "Pittsburgh Penguins",
    "clubhouse": "https://www.espn.com/nhl/team/_/name/pit/pittsburgh-penguins",
    "color": "000000",
    "logo": "https://a.espncdn.com/i/teamlogos/nhl/500/pit.png",
    "recordSummary": "3-6-1",
    "seasonSummary": "2024-25",
    "standingSummary": "7th in Metropolitan Division",
    "groups": {
      "id": "33",
      "parent": {
        "id": "7"
        },
      "isConference": false
    }
  },
  "events": [
    {
      "id": "401458607",
      ...
```

### 16. **`GET /team-statistic`**

- **Description**: Retrieves the statistics for a specific NHL team.

| Parameter | Type   | Default | Description                            | Required |
|-----------|--------|---------|----------------------------------------|----------|
| `teamId`  | string | -       | The unique identifier for the NHL team | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/team-statistic?teamId=17', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "stats": {
    "id": "0",
    "name": "All Splits",
    "abbreviation": "Total",
    "categories": [
      {
        "name": "general",
        "displayName": "General",
        "abbreviation": "gen",
        "stats": [
          {
            "name": "games",
            "displayName": "Games Played",
            "shortDisplayName": "Games",
            "description": "Total games played.",
            "abbreviation": "GP",
            "value": 10,
            "displayValue": "10"
          },
          {
            "name": "timeOnIce",
            "displayName": "Time On Ice",
            "shortDisplayName": "Time On Ice",
            "description": "Total time on ice.",
            "abbreviation": "TOI",
            "value": 214137,
            "displayValue": "3568:57"
          },
          {
            ...
```

### 17. **`GET /player-statistic`**

- **Description**: Retrieves the statistics for a specific NHL player.

| Parameter  | Type   | Default | Description                              | Required |
|------------|--------|---------|------------------------------------------|----------|
| `playerId` | string | -       | The unique identifier for the NHL player | Yes      |

Example request:

```javascript
fetch('https://nhl-api5.p.rapidapi.com/player-statistic?playerId=3042003', {
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'nhl-api5.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:

```json
{
  "id": "0",
  "name": "All Splits",
  "abbreviation": "TOTAL",
  "type": "total",
  "categories": [
    {
      "name": "defensive",
      "displayName": "Defensive",
      "shortDisplayName": "Defensive",
      "abbreviation": "def",
      "summary": "",
      "stats": [
        {
          "name": "goalsAgainst",
          "displayName": "Goals Against",
          "shortDisplayName": "Goals Against",
          "description": "Total goals against.",
          "abbreviation": "GA",
          "value": 0,
          "displayValue": "0"
        },
        {
          "name": "avgGoalsAgainst",
          "displayName": "Goals Against per Game",
          "shortDisplayName": "Goals Against / Game",
          "description": "Average goals against per game.",
          "abbreviation": "GA/G",
          "value": 0,
          "displayValue": "0.00"
          ...
```

## Error Handling

The  API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if rate limit exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |
