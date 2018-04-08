---
title: NHL API v1.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2
---

<h1 id="NHL-API">NHL API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Documenting the publicly accessible portions of the NHL API.

* [Base URL](https://statsapi.web.nhl.com/api/v1)

* [NHL API documentation](https://github.com/erunion/sport-api-specifications)

<h1 id="NHL-API-conferences">conferences</h1>

## getConferences

<a id="opIdgetConferences"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/conferences \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/conferences HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/conferences',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/conferences',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/conferences',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/conferences', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/conferences");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/conferences", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /conferences`

*Get all current NHL conferences.*

This only retrieves active conferences. For inactive conferences, use `/conferences/{id}`.

> Example responses

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 5,
      "name": "Eastern",
      "link": "/api/v1/conferences/5",
      "abbreviation": "E",
      "shortName": "East",
      "active": true
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getConferences-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Conferences](#schemaconferences)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getConference

<a id="opIdgetConference"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/conferences/{id} \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/conferences/{id} HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/conferences/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/conferences/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/conferences/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/conferences/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/conferences/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/conferences/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /conferences/{id}`

*Get an NHL conference.*

You can use this to also retrieve inactive conferences. For example, the ID for the World Cup of Hockey is `7`.

<h3 id="getConference-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the conference.|

> Example responses

```json
{
  "id": 15,
  "name": "Pacific",
  "link": "/api/v1/divisions/15",
  "abbreviation": "P",
  "conference": {
    "id": 5,
    "name": "Western",
    "link": "/api/v1/conferences/5"
  },
  "active": true
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getConference-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Division](#schemadivision)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-divisions">divisions</h1>

## getDivisions

<a id="opIdgetDivisions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/divisions \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/divisions HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/divisions',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/divisions',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/divisions',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/divisions', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/divisions");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/divisions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /divisions`

*Get all current NHL divisions.*

This only retrieves active divisions. For inactive divisions, use `/divisions/{id}`.

> Example responses

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 15,
      "name": "Pacific",
      "link": "/api/v1/divisions/15",
      "abbreviation": "P",
      "conference": {
        "id": 5,
        "name": "Western",
        "link": "/api/v1/conferences/5"
      },
      "active": true
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getDivisions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Divisions](#schemadivisions)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getDivision

<a id="opIdgetDivision"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/divisions/{id} \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/divisions/{id} HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/divisions/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/divisions/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/divisions/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/divisions/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/divisions/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/divisions/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /divisions/{id}`

*Get an NHL division.*

You can use this to also retrieve inactive divisions. For example, the ID for the old Patrick division is `13`.

<h3 id="getDivision-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the division.|

> Example responses

```json
{
  "id": 15,
  "name": "Pacific",
  "link": "/api/v1/divisions/15",
  "abbreviation": "P",
  "conference": {
    "id": 5,
    "name": "Western",
    "link": "/api/v1/conferences/5"
  },
  "active": true
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getDivision-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Division](#schemadivision)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-draft">draft</h1>

## getDraft

<a id="opIdgetDraft"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/draft \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/draft HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/draft',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/draft',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/draft',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/draft', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/draft");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/draft", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /draft`

*Get round-by-round data for current year's NHL Entry Draft.*

> Example responses

```json
{
  "copyright": "string",
  "drafts": [
    {
      "draftYear": 2017,
      "rounds": [
        {
          "roundNumber": 1,
          "round": "1",
          "picks": [
            {
              "year": 2017,
              "round": "1",
              "pickOverall": 1,
              "pickInRound": 1,
              "team": {
                "id": 1,
                "name": "New Jersey Devils",
                "link": "/api/v1/teams/1"
              },
              "prospect": {
                "id": 65242,
                "fullName": "Nico Hischier",
                "link": "/api/v1/draft/prospects/65242"
              }
            }
          ]
        }
      ]
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getDraft-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Draft](#schemadraft)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getDraftByYear

<a id="opIdgetDraftByYear"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/draft/{year} \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/draft/{year} HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/draft/{year}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/draft/{year}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/draft/{year}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/draft/{year}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/draft/{year}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/draft/{year}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /draft/{year}`

*Get round-by-round data for a specific year's NHL Entry Draft.*

<h3 id="getDraftByYear-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|year|path|number|true|The draft year.|

> Example responses

```json
{
  "copyright": "string",
  "drafts": [
    {
      "draftYear": 2017,
      "rounds": [
        {
          "roundNumber": 1,
          "round": "1",
          "picks": [
            {
              "year": 2017,
              "round": "1",
              "pickOverall": 1,
              "pickInRound": 1,
              "team": {
                "id": 1,
                "name": "New Jersey Devils",
                "link": "/api/v1/teams/1"
              },
              "prospect": {
                "id": 65242,
                "fullName": "Nico Hischier",
                "link": "/api/v1/draft/prospects/65242"
              }
            }
          ]
        }
      ]
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getDraftByYear-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Draft](#schemadraft)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getDraftProspects

<a id="opIdgetDraftProspects"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/draft/prospects \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/draft/prospects HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/draft/prospects',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/draft/prospects',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/draft/prospects',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/draft/prospects', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/draft/prospects");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/draft/prospects", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /draft/prospects`

*Get all NHL Entry Draft prospects.*

Be forewarned that this endpoint returns a **lot** of data and there does not appear to be a way to paginate results.

> Example responses

```json
{
  "copyright": "string",
  "prospects": [
    {
      "id": 65242,
      "fullName": "Nico Hischier",
      "link": "/api/v1/draft/prospects/65242",
      "firstName": "Nico",
      "lastName": "Hischier",
      "birthDate": "1999-01-04",
      "birthCity": "Naters",
      "birthCountry": "CHE",
      "nationality": "CHE",
      "height": "6' 2\"",
      "weight": 179,
      "shootsCatches": "L",
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      },
      "prospectCategory": {
        "id": 1,
        "shortName": "NA Skater",
        "name": "North American Skater"
      },
      "amateurTeam": {
        "link": "/api/v1/teams/null"
      },
      "amateurLeague": {
        "link": "/api/v1/league/null"
      },
      "ranks": {}
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getDraftProspects-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DraftProspects](#schemadraftprospects)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getDraftProspect

<a id="opIdgetDraftProspect"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/draft/prospects/{id} \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/draft/prospects/{id} HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/draft/prospects/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/draft/prospects/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/draft/prospects/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/draft/prospects/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/draft/prospects/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/draft/prospects/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /draft/prospects/{id}`

*Get an NHL Entry Draft prospect.*

<h3 id="getDraftProspect-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The prospect ID.|

> Example responses

```json
{
  "copyright": "string",
  "prospects": [
    {
      "id": 65242,
      "fullName": "Nico Hischier",
      "link": "/api/v1/draft/prospects/65242",
      "firstName": "Nico",
      "lastName": "Hischier",
      "birthDate": "1999-01-04",
      "birthCity": "Naters",
      "birthCountry": "CHE",
      "nationality": "CHE",
      "height": "6' 2\"",
      "weight": 179,
      "shootsCatches": "L",
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      },
      "prospectCategory": {
        "id": 1,
        "shortName": "NA Skater",
        "name": "North American Skater"
      },
      "amateurTeam": {
        "link": "/api/v1/teams/null"
      },
      "amateurLeague": {
        "link": "/api/v1/league/null"
      },
      "ranks": {}
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getDraftProspect-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[DraftProspects](#schemadraftprospects)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-games">games</h1>

## getGameBoxscore

<a id="opIdgetGameBoxscore"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/game/{id}/boxscore", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /game/{id}/boxscore`

*Get the boxscore for an NHL game.*

If you want detailed play information, you should use `/game/{id}/feed/live` or `/game/{id}/feed/live/diffPatch`.

<h3 id="getGameBoxscore-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the game. The first 4 digits identify the season of the game (ie. 2017 for the 2017-2018 season). The next 2 digits give the type of game, where 01 = preseason, 02 = regular season, 03 = playoffs, 04 = all-star. The final 4 digits identify the specific game number. For regular season and preseason games, this ranges from 0001 to the number of games played. (1271 for seasons with 31 teams (2017 and onwards) and 1230 for seasons with 30 teams). For playoff games, the 2nd digit of the specific number gives the round of the playoffs, the 3rd digit specifies the matchup, and the 4th digit specifies the game (out of 7).|

> Example responses

```json
{
  "copyright": "string",
  "teams": {
    "away": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "teamStats": {
        "teamSkaterStats": {
          "goals": 6,
          "pim": 6,
          "shots": 30,
          "powerPlayPercentage": "0.0",
          "powerPlayGoals": 0,
          "powerPlayOpportunities": 1,
          "faceOffWinPercentage": "59.3",
          "blocked": 21,
          "takeaways": 9,
          "giveaways": 6,
          "hits": 15
        }
      },
      "players": {
        "person": {
          "id": 8471709,
          "fullName": "Marc-Edouard Vlasic",
          "link": "/api/v1/people/8471709",
          "shootsCatches": "L",
          "rosterStatus": "Y"
        },
        "jerseyNumber": "44",
        "position": {
          "code": "D",
          "name": "Defenseman",
          "type": "Defenseman",
          "abbreviation": "D"
        },
        "stats": {
          "skaterStats": {
            "timeOnIce": "23:04",
            "assists": 0,
            "goals": 0,
            "shots": 2,
            "hits": 0,
            "powerPlayGoals": 0,
            "powerPlayAssists": 0,
            "penaltyMinutes": 0,
            "faceOffWins": 0,
            "faceoffTaken": 0,
            "takeaways": 0,
            "giveaways": 1,
            "shortHandedGoals": 0,
            "shortHandedAssists": 0,
            "blocked": 0,
            "plusMinus": 1,
            "evenTimeOnIce": "18:12",
            "powerPlayTimeOnIce": "1:07",
            "shortHandedTimeOnIce": "3:45"
          }
        }
      },
      "goalies": [
        0
      ],
      "skaters": [
        0
      ],
      "onIce": [
        0
      ],
      "onIcePlus": [
        {
          "playerId": 8477180,
          "shiftDuration": 458,
          "stamina": 33
        }
      ],
      "scratches": [
        0
      ],
      "penaltyBox": [
        0
      ],
      "coaches": [
        {
          "person": {
            "fullName": "Peter DeBoer",
            "link": "/api/v1/people/null"
          },
          "position": {
            "code": "HC",
            "name": "Head Coach",
            "type": "Head Coach",
            "abbreviation": "Head Coach"
          }
        }
      ]
    },
    "home": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "teamStats": {
        "teamSkaterStats": {
          "goals": 6,
          "pim": 6,
          "shots": 30,
          "powerPlayPercentage": "0.0",
          "powerPlayGoals": 0,
          "powerPlayOpportunities": 1,
          "faceOffWinPercentage": "59.3",
          "blocked": 21,
          "takeaways": 9,
          "giveaways": 6,
          "hits": 15
        }
      },
      "players": {
        "person": {
          "id": 8471709,
          "fullName": "Marc-Edouard Vlasic",
          "link": "/api/v1/people/8471709",
          "shootsCatches": "L",
          "rosterStatus": "Y"
        },
        "jerseyNumber": "44",
        "position": {
          "code": "D",
          "name": "Defenseman",
          "type": "Defenseman",
          "abbreviation": "D"
        },
        "stats": {
          "skaterStats": {
            "timeOnIce": "23:04",
            "assists": 0,
            "goals": 0,
            "shots": 2,
            "hits": 0,
            "powerPlayGoals": 0,
            "powerPlayAssists": 0,
            "penaltyMinutes": 0,
            "faceOffWins": 0,
            "faceoffTaken": 0,
            "takeaways": 0,
            "giveaways": 1,
            "shortHandedGoals": 0,
            "shortHandedAssists": 0,
            "blocked": 0,
            "plusMinus": 1,
            "evenTimeOnIce": "18:12",
            "powerPlayTimeOnIce": "1:07",
            "shortHandedTimeOnIce": "3:45"
          }
        }
      },
      "goalies": [
        0
      ],
      "skaters": [
        0
      ],
      "onIce": [
        0
      ],
      "onIcePlus": [
        {
          "playerId": 8477180,
          "shiftDuration": 458,
          "stamina": 33
        }
      ],
      "scratches": [
        0
      ],
      "penaltyBox": [
        0
      ],
      "coaches": [
        {
          "person": {
            "fullName": "Peter DeBoer",
            "link": "/api/v1/people/null"
          },
          "position": {
            "code": "HC",
            "name": "Head Coach",
            "type": "Head Coach",
            "abbreviation": "Head Coach"
          }
        }
      ]
    }
  },
  "officials": [
    {
      "official": {
        "id": 2071,
        "fullName": "Tim Peel",
        "link": "/api/v1/people/2071"
      },
      "officialType": "Linesman"
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getGameBoxscore-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GameBoxscores](#schemagameboxscores)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getGameContent

<a id="opIdgetGameContent"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/game/{id}/content \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/game/{id}/content HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/game/{id}/content',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/game/{id}/content',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/game/{id}/content',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/game/{id}/content', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/game/{id}/content");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/game/{id}/content", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /game/{id}/content`

*Get editorials, video replays and photo highlights for an NHL game.*

<h3 id="getGameContent-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the game. The first 4 digits identify the season of the game (ie. 2017 for the 2017-2018 season). The next 2 digits give the type of game, where 01 = preseason, 02 = regular season, 03 = playoffs, 04 = all-star. The final 4 digits identify the specific game number. For regular season and preseason games, this ranges from 0001 to the number of games played. (1271 for seasons with 31 teams (2017 and onwards) and 1230 for seasons with 30 teams). For playoff games, the 2nd digit of the specific number gives the round of the playoffs, the 3rd digit specifies the matchup, and the 4th digit specifies the game (out of 7).|

> Example responses

```json
{
  "copyright": "string",
  "link": "/api/v1/game/2017020851/content",
  "editorial": {
    "preview": {
      "title": "Preview",
      "topicList": "string",
      "items": [
        {
          "type": "article",
          "state": "A",
          "date": "2018-02-10T16:57:06-0500",
          "id": "295823824",
          "headline": "Oilers at Sharks preview",
          "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
          "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
          "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
          "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
          "slug": "edmonton-oilers-san-jose-sharks-game-preview",
          "commenting": true,
          "tagline": "string",
          "tokenData": {
            "tokenGUID": "token-EBDA2F0039BF4445D2C91",
            "type": "hyperLink",
            "id": "8471709",
            "teamId": "28",
            "name": "Marc-Edouard Vlasic",
            "seoName": "marc-edouard-vlasic",
            "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
            "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
          },
          "contributor": {
            "contributors": [
              {
                "name": "Eric Gilmore",
                "twitter": "string"
              }
            ],
            "source": "NHL.com Correspondent"
          },
          "keywordsDisplay": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "keywordsAll": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "approval": "string",
          "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
          "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
          "primaryKeyword": {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          },
          "media": {
            "type": "photo",
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            }
          },
          "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
        }
      ]
    },
    "articles": {
      "title": "Preview",
      "topicList": "string",
      "items": [
        {
          "type": "article",
          "state": "A",
          "date": "2018-02-10T16:57:06-0500",
          "id": "295823824",
          "headline": "Oilers at Sharks preview",
          "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
          "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
          "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
          "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
          "slug": "edmonton-oilers-san-jose-sharks-game-preview",
          "commenting": true,
          "tagline": "string",
          "tokenData": {
            "tokenGUID": "token-EBDA2F0039BF4445D2C91",
            "type": "hyperLink",
            "id": "8471709",
            "teamId": "28",
            "name": "Marc-Edouard Vlasic",
            "seoName": "marc-edouard-vlasic",
            "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
            "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
          },
          "contributor": {
            "contributors": [
              {
                "name": "Eric Gilmore",
                "twitter": "string"
              }
            ],
            "source": "NHL.com Correspondent"
          },
          "keywordsDisplay": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "keywordsAll": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "approval": "string",
          "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
          "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
          "primaryKeyword": {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          },
          "media": {
            "type": "photo",
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            }
          },
          "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
        }
      ]
    },
    "recap": {
      "title": "Preview",
      "topicList": "string",
      "items": [
        {
          "type": "article",
          "state": "A",
          "date": "2018-02-10T16:57:06-0500",
          "id": "295823824",
          "headline": "Oilers at Sharks preview",
          "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
          "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
          "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
          "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
          "slug": "edmonton-oilers-san-jose-sharks-game-preview",
          "commenting": true,
          "tagline": "string",
          "tokenData": {
            "tokenGUID": "token-EBDA2F0039BF4445D2C91",
            "type": "hyperLink",
            "id": "8471709",
            "teamId": "28",
            "name": "Marc-Edouard Vlasic",
            "seoName": "marc-edouard-vlasic",
            "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
            "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
          },
          "contributor": {
            "contributors": [
              {
                "name": "Eric Gilmore",
                "twitter": "string"
              }
            ],
            "source": "NHL.com Correspondent"
          },
          "keywordsDisplay": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "keywordsAll": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "approval": "string",
          "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
          "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
          "primaryKeyword": {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          },
          "media": {
            "type": "photo",
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            }
          },
          "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
        }
      ]
    }
  },
  "media": {
    "epg": [
      {
        "title": "NHLTV",
        "platform": "web",
        "items": [
          {
            "guid": "dbb39fa8-6679-4b22-a8c5-71eb5e39b462",
            "mediaState": "MEDIA_ARCHIVE",
            "mediaPlaybackId": "57463703",
            "mediaFeedType": "HOME",
            "callLetters": "NBCS-CA",
            "eventId": "221-1007449",
            "language": "eng",
            "freeGame": true,
            "feedName": "string",
            "gamePlus": true
          }
        ]
      }
    ],
    "milestones": {
      "title": "Milestones",
      "streamStart": "2018-02-11T03:04:32+0000",
      "items": [
        {
          "title": "Broadcast Start",
          "description": "Broadcast Start",
          "type": "BROADCAST_START",
          "timeAbsolute": "2018-02-11T03:04:36+0000",
          "timeOffset": "4",
          "period": "1",
          "statsEventId": "10",
          "teamId": "28",
          "playerId": "8477046",
          "periodTime": "01:15",
          "ordinalNum": "1st",
          "highlight": {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        }
      ]
    }
  },
  "highlights": {
    "scoreboard": {
      "scoreboard": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      },
      "gameCenter": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      }
    },
    "gameCenter": {
      "scoreboard": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      },
      "gameCenter": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      }
    }
  }
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getGameContent-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[GameContent](#schemagamecontent)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getGame

<a id="opIdgetGame"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /game/{id}/feed/live`

*Get all available data for an NHL game.*

This contains all data related to a game, from the boxscore, to play data and even on-ice coordinates. Be forewarned that, depending on the game, this endpoint can return a **lot** of data.

<h3 id="getGame-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the game. The first 4 digits identify the season of the game (ie. 2017 for the 2017-2018 season). The next 2 digits give the type of game, where 01 = preseason, 02 = regular season, 03 = playoffs, 04 = all-star. The final 4 digits identify the specific game number. For regular season and preseason games, this ranges from 0001 to the number of games played. (1271 for seasons with 31 teams (2017 and onwards) and 1230 for seasons with 30 teams). For playoff games, the 2nd digit of the specific number gives the round of the playoffs, the 3rd digit specifies the matchup, and the 4th digit specifies the game (out of 7).|

> Example responses

```json
{
  "copyright": "string",
  "gamePk": 2017020851,
  "link": "/api/v1/game/2017020851/feed/live",
  "metaData": {
    "wait": 10,
    "timeStamp": "20180211_054345"
  },
  "gameData": {
    "game": {
      "pk": 2017020851,
      "season": "20172018",
      "type": "R"
    },
    "datetime": {
      "dateTime": "2018-02-11T03:00:00Z",
      "endDateTime": "2018-02-11T05:30:42Z"
    },
    "status": {
      "abstractGameState": "Final",
      "codedGameState": "7",
      "detailedState": "Final",
      "statusCode": "7",
      "startTimeTBD": true
    },
    "teams": {
      "away": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "venue": {
          "name": "SAP Center at San Jose",
          "link": "/api/v1/venues/null",
          "city": "San Jose",
          "timeZone": {
            "id": "America/Los_Angeles",
            "offset": -8,
            "tz": "PST"
          }
        },
        "abbreviation": "SJS",
        "triCode": "SJS",
        "teamName": "Sharks",
        "locationName": "San Jose",
        "firstYearOfPlay": 1990,
        "division": {
          "id": 15,
          "name": "Pacific",
          "link": "/api/v1/divisions/15"
        },
        "conference": {
          "id": 5,
          "name": "Western",
          "link": "/api/v1/conferences/5"
        },
        "franchise": {
          "id": 29,
          "name": "Sharks",
          "link": "/api/v1/franchises/29"
        },
        "roster": {
          "roster": [
            {
              "person": {
                "id": 8466138,
                "fullName": "Joe Thornton",
                "link": "/api/v1/people/8466138"
              },
              "jerseyNumber": 19,
              "position": {
                "code": "C",
                "name": "Center",
                "type": "Forward",
                "abbreviation": "C"
              }
            }
          ]
        },
        "nextGameSchedule": {
          "totalItems": 1,
          "totalEvents": 0,
          "totalGames": 1,
          "totalMatches": 0,
          "dates": [
            {
              "date": "2018-02-10",
              "totalItems": 1,
              "totalEvents": 0,
              "totalGames": 1,
              "totalMatches": 0,
              "games": [
                {
                  "gamePk": 2017020851,
                  "link": "/api/v1/game/2017020851/feed/live",
                  "gameType": "R",
                  "season": "20172018",
                  "gameDate": "2018-02-11T03:00:00Z",
                  "status": {
                    "abstractGameState": "Live",
                    "codedGameState": "3",
                    "detailedState": "In Progress",
                    "statusCode": "2",
                    "startTimeTBD": true
                  },
                  "teams": {
                    "away": {},
                    "home": {}
                  },
                  "venue": {
                    "name": "SAP Center at San Jose",
                    "link": "/api/v1/venues/null"
                  },
                  "content": {
                    "link": "/api/v1/game/2017020851/content"
                  }
                }
              ],
              "events": [
                {}
              ],
              "matches": [
                {}
              ]
            }
          ]
        },
        "shortName": "San Jose",
        "officialSiteUrl": "http://www.sjsharks.com",
        "franchiseId": 29,
        "active": true
      },
      "home": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "venue": {
          "name": "SAP Center at San Jose",
          "link": "/api/v1/venues/null",
          "city": "San Jose",
          "timeZone": {
            "id": "America/Los_Angeles",
            "offset": -8,
            "tz": "PST"
          }
        },
        "abbreviation": "SJS",
        "triCode": "SJS",
        "teamName": "Sharks",
        "locationName": "San Jose",
        "firstYearOfPlay": 1990,
        "division": {
          "id": 15,
          "name": "Pacific",
          "link": "/api/v1/divisions/15"
        },
        "conference": {
          "id": 5,
          "name": "Western",
          "link": "/api/v1/conferences/5"
        },
        "franchise": {
          "id": 29,
          "name": "Sharks",
          "link": "/api/v1/franchises/29"
        },
        "roster": {
          "roster": [
            {
              "person": {
                "id": 8466138,
                "fullName": "Joe Thornton",
                "link": "/api/v1/people/8466138"
              },
              "jerseyNumber": 19,
              "position": {
                "code": "C",
                "name": "Center",
                "type": "Forward",
                "abbreviation": "C"
              }
            }
          ]
        },
        "nextGameSchedule": {
          "totalItems": 1,
          "totalEvents": 0,
          "totalGames": 1,
          "totalMatches": 0,
          "dates": [
            {
              "date": "2018-02-10",
              "totalItems": 1,
              "totalEvents": 0,
              "totalGames": 1,
              "totalMatches": 0,
              "games": [
                {
                  "gamePk": 2017020851,
                  "link": "/api/v1/game/2017020851/feed/live",
                  "gameType": "R",
                  "season": "20172018",
                  "gameDate": "2018-02-11T03:00:00Z",
                  "status": {
                    "abstractGameState": "Live",
                    "codedGameState": "3",
                    "detailedState": "In Progress",
                    "statusCode": "2",
                    "startTimeTBD": true
                  },
                  "teams": {
                    "away": {},
                    "home": {}
                  },
                  "venue": {
                    "name": "SAP Center at San Jose",
                    "link": "/api/v1/venues/null"
                  },
                  "content": {
                    "link": "/api/v1/game/2017020851/content"
                  }
                }
              ],
              "events": [
                {}
              ],
              "matches": [
                {}
              ]
            }
          ]
        },
        "shortName": "San Jose",
        "officialSiteUrl": "http://www.sjsharks.com",
        "franchiseId": 29,
        "active": true
      }
    },
    "players": {
      "id": 8466138,
      "fullName": "Joe Thornton",
      "link": "/api/v1/people/8466138",
      "firstName": "Joe",
      "lastName": "Thornton",
      "primaryNumber": "19",
      "birthDate": "1979-07-02",
      "currentAge": 38,
      "birthCity": "London",
      "birthStateProvince": "ON",
      "birthCountry": "CAN",
      "nationality": "CAN",
      "height": "6' 4\"",
      "weight": 220,
      "active": true,
      "alternateCaptain": true,
      "captain": true,
      "rookie": true,
      "shootsCatches": "L",
      "rosterStatus": "I",
      "currentTeam": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28"
      },
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      }
    },
    "venue": {
      "name": "SAP Center at San Jose",
      "link": "/api/v1/venues/null"
    }
  },
  "liveData": {
    "plays": {
      "allPlays": [
        {
          "players": [
            {
              "player": {
                "id": 8476881,
                "fullName": "Tomas Hertl",
                "link": "/api/v1/people/8476881"
              },
              "playerType": "Winner"
            }
          ],
          "result": {
            "event": "Game End",
            "eventCode": "SJS505",
            "eventTypeId": "GAME_END",
            "description": "Game End"
          },
          "about": {
            "eventIdx": 315,
            "eventId": 505,
            "period": 3,
            "periodType": "REGULAR",
            "ordinalNum": "3rd",
            "periodTime": "20:00",
            "periodTimeRemaining": "00:00",
            "dateTime": "2018-02-11T05:30:42Z",
            "goals": {
              "away": 4,
              "home": 6
            }
          },
          "coordinates": {
            "x": 0,
            "y": 0
          },
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "triCode": "SJS"
          }
        }
      ],
      "scoringPlays": [
        0
      ],
      "penaltyPlays": [
        0
      ],
      "playsByPeriod": [
        {
          "startIndex": 0,
          "plays": [
            0
          ],
          "endIndex": 114
        }
      ],
      "currentPlay": {
        "players": [
          {
            "player": {
              "id": 8476881,
              "fullName": "Tomas Hertl",
              "link": "/api/v1/people/8476881"
            },
            "playerType": "Winner"
          }
        ],
        "result": {
          "event": "Game End",
          "eventCode": "SJS505",
          "eventTypeId": "GAME_END",
          "description": "Game End"
        },
        "about": {
          "eventIdx": 315,
          "eventId": 505,
          "period": 3,
          "periodType": "REGULAR",
          "ordinalNum": "3rd",
          "periodTime": "20:00",
          "periodTimeRemaining": "00:00",
          "dateTime": "2018-02-11T05:30:42Z",
          "goals": {
            "away": 4,
            "home": 6
          }
        },
        "coordinates": {
          "x": 0,
          "y": 0
        },
        "team": {
          "id": 28,
          "name": "San Jose Sharks",
          "link": "/api/v1/teams/28",
          "triCode": "SJS"
        }
      }
    },
    "linescore": {
      "currentPeriod": 3,
      "currentPeriodOrdinal": "3rd",
      "currentPeriodTimeRemaining": "Final",
      "periods": [
        {
          "periodType": "REGULAR",
          "startTime": "2018-02-11T03:09:50Z",
          "endTime": "2018-02-11T03:44:47Z",
          "num": 1,
          "ordinalNum": "1st",
          "home": {
            "goals": 2,
            "shotsOnGoal": 14,
            "rinkSide": "left"
          },
          "away": {
            "goals": 0,
            "shotsOnGoal": 9,
            "rinkSide": "right"
          }
        }
      ],
      "shootoutInfo": {
        "away": {
          "scores": 0,
          "attempts": 0
        },
        "home": {
          "scores": 0,
          "attempts": 0
        }
      },
      "teams": {
        "home": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "goals": 6,
          "shotsOnGoal": 30,
          "goaliePulled": true,
          "numSkaters": 5,
          "powerPlay": true
        },
        "away": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "goals": 6,
          "shotsOnGoal": 30,
          "goaliePulled": true,
          "numSkaters": 5,
          "powerPlay": true
        }
      },
      "powerPlayStrength": "Even",
      "hasShootout": true,
      "intermissionInfo": {
        "intermissionTimeRemaining": 0,
        "intermissionTimeElapsed": 0,
        "inIntermission": true
      },
      "powerPlayInfo": {
        "situationTimeRemaining": 0,
        "situationTimeElapsed": 72,
        "inSituation": true
      }
    },
    "boxscore": {
      "teams": {
        "away": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "teamStats": {
            "teamSkaterStats": {
              "goals": 6,
              "pim": 6,
              "shots": 30,
              "powerPlayPercentage": "0.0",
              "powerPlayGoals": 0,
              "powerPlayOpportunities": 1,
              "faceOffWinPercentage": "59.3",
              "blocked": 21,
              "takeaways": 9,
              "giveaways": 6,
              "hits": 15
            }
          },
          "players": {
            "person": {
              "id": 8471709,
              "fullName": "Marc-Edouard Vlasic",
              "link": "/api/v1/people/8471709",
              "shootsCatches": "L",
              "rosterStatus": "Y"
            },
            "jerseyNumber": "44",
            "position": {
              "code": "D",
              "name": "Defenseman",
              "type": "Defenseman",
              "abbreviation": "D"
            },
            "stats": {
              "skaterStats": {
                "timeOnIce": "23:04",
                "assists": 0,
                "goals": 0,
                "shots": 2,
                "hits": 0,
                "powerPlayGoals": 0,
                "powerPlayAssists": 0,
                "penaltyMinutes": 0,
                "faceOffWins": 0,
                "faceoffTaken": 0,
                "takeaways": 0,
                "giveaways": 1,
                "shortHandedGoals": 0,
                "shortHandedAssists": 0,
                "blocked": 0,
                "plusMinus": 1,
                "evenTimeOnIce": "18:12",
                "powerPlayTimeOnIce": "1:07",
                "shortHandedTimeOnIce": "3:45"
              }
            }
          },
          "goalies": [
            0
          ],
          "skaters": [
            0
          ],
          "onIce": [
            0
          ],
          "onIcePlus": [
            {
              "playerId": 8477180,
              "shiftDuration": 458,
              "stamina": 33
            }
          ],
          "scratches": [
            0
          ],
          "penaltyBox": [
            0
          ],
          "coaches": [
            {
              "person": {
                "fullName": "Peter DeBoer",
                "link": "/api/v1/people/null"
              },
              "position": {
                "code": "HC",
                "name": "Head Coach",
                "type": "Head Coach",
                "abbreviation": "Head Coach"
              }
            }
          ]
        },
        "home": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "teamStats": {
            "teamSkaterStats": {
              "goals": 6,
              "pim": 6,
              "shots": 30,
              "powerPlayPercentage": "0.0",
              "powerPlayGoals": 0,
              "powerPlayOpportunities": 1,
              "faceOffWinPercentage": "59.3",
              "blocked": 21,
              "takeaways": 9,
              "giveaways": 6,
              "hits": 15
            }
          },
          "players": {
            "person": {
              "id": 8471709,
              "fullName": "Marc-Edouard Vlasic",
              "link": "/api/v1/people/8471709",
              "shootsCatches": "L",
              "rosterStatus": "Y"
            },
            "jerseyNumber": "44",
            "position": {
              "code": "D",
              "name": "Defenseman",
              "type": "Defenseman",
              "abbreviation": "D"
            },
            "stats": {
              "skaterStats": {
                "timeOnIce": "23:04",
                "assists": 0,
                "goals": 0,
                "shots": 2,
                "hits": 0,
                "powerPlayGoals": 0,
                "powerPlayAssists": 0,
                "penaltyMinutes": 0,
                "faceOffWins": 0,
                "faceoffTaken": 0,
                "takeaways": 0,
                "giveaways": 1,
                "shortHandedGoals": 0,
                "shortHandedAssists": 0,
                "blocked": 0,
                "plusMinus": 1,
                "evenTimeOnIce": "18:12",
                "powerPlayTimeOnIce": "1:07",
                "shortHandedTimeOnIce": "3:45"
              }
            }
          },
          "goalies": [
            0
          ],
          "skaters": [
            0
          ],
          "onIce": [
            0
          ],
          "onIcePlus": [
            {
              "playerId": 8477180,
              "shiftDuration": 458,
              "stamina": 33
            }
          ],
          "scratches": [
            0
          ],
          "penaltyBox": [
            0
          ],
          "coaches": [
            {
              "person": {
                "fullName": "Peter DeBoer",
                "link": "/api/v1/people/null"
              },
              "position": {
                "code": "HC",
                "name": "Head Coach",
                "type": "Head Coach",
                "abbreviation": "Head Coach"
              }
            }
          ]
        }
      },
      "officials": [
        {
          "official": {
            "id": 2071,
            "fullName": "Tim Peel",
            "link": "/api/v1/people/2071"
          },
          "officialType": "Linesman"
        }
      ]
    },
    "decisions": {
      "winner": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "loser": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "firstStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "secondStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "thirdStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      }
    }
  }
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getGame-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Game](#schemagame)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getGameDiff

<a id="opIdgetGameDiff"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch?startTimeCode=20180210_0900 \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch?startTimeCode=20180210_0900 HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch',
  method: 'get',
  data: '?startTimeCode=20180210_0900',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch?startTimeCode=20180210_0900',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch',
  params: {
  'startTimeCode' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch', params={
  'startTimeCode': '20180210_0900'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch?startTimeCode=20180210_0900");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/game/{id}/feed/live/diffPatch", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /game/{id}/feed/live/diffPatch`

*Get all available data for an NHL game after a specific time.*

You can use this to return a small subset of data relating to game.

<h3 id="getGameDiff-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the game. The first 4 digits identify the season of the game (ie. 2017 for the 2017-2018 season). The next 2 digits give the type of game, where 01 = preseason, 02 = regular season, 03 = playoffs, 04 = all-star. The final 4 digits identify the specific game number. For regular season and preseason games, this ranges from 0001 to the number of games played. (1271 for seasons with 31 teams (2017 and onwards) and 1230 for seasons with 30 teams). For playoff games, the 2nd digit of the specific number gives the round of the playoffs, the 3rd digit specifies the matchup, and the 4th digit specifies the game (out of 7).|
|startTimeCode|query|string|true|The prospect ID.|

> Example responses

```json
{
  "copyright": "string",
  "gamePk": 2017020851,
  "link": "/api/v1/game/2017020851/feed/live",
  "metaData": {
    "wait": 10,
    "timeStamp": "20180211_054345"
  },
  "gameData": {
    "game": {
      "pk": 2017020851,
      "season": "20172018",
      "type": "R"
    },
    "datetime": {
      "dateTime": "2018-02-11T03:00:00Z",
      "endDateTime": "2018-02-11T05:30:42Z"
    },
    "status": {
      "abstractGameState": "Final",
      "codedGameState": "7",
      "detailedState": "Final",
      "statusCode": "7",
      "startTimeTBD": true
    },
    "teams": {
      "away": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "venue": {
          "name": "SAP Center at San Jose",
          "link": "/api/v1/venues/null",
          "city": "San Jose",
          "timeZone": {
            "id": "America/Los_Angeles",
            "offset": -8,
            "tz": "PST"
          }
        },
        "abbreviation": "SJS",
        "triCode": "SJS",
        "teamName": "Sharks",
        "locationName": "San Jose",
        "firstYearOfPlay": 1990,
        "division": {
          "id": 15,
          "name": "Pacific",
          "link": "/api/v1/divisions/15"
        },
        "conference": {
          "id": 5,
          "name": "Western",
          "link": "/api/v1/conferences/5"
        },
        "franchise": {
          "id": 29,
          "name": "Sharks",
          "link": "/api/v1/franchises/29"
        },
        "roster": {
          "roster": [
            {
              "person": {
                "id": 8466138,
                "fullName": "Joe Thornton",
                "link": "/api/v1/people/8466138"
              },
              "jerseyNumber": 19,
              "position": {
                "code": "C",
                "name": "Center",
                "type": "Forward",
                "abbreviation": "C"
              }
            }
          ]
        },
        "nextGameSchedule": {
          "totalItems": 1,
          "totalEvents": 0,
          "totalGames": 1,
          "totalMatches": 0,
          "dates": [
            {
              "date": "2018-02-10",
              "totalItems": 1,
              "totalEvents": 0,
              "totalGames": 1,
              "totalMatches": 0,
              "games": [
                {
                  "gamePk": 2017020851,
                  "link": "/api/v1/game/2017020851/feed/live",
                  "gameType": "R",
                  "season": "20172018",
                  "gameDate": "2018-02-11T03:00:00Z",
                  "status": {
                    "abstractGameState": "Live",
                    "codedGameState": "3",
                    "detailedState": "In Progress",
                    "statusCode": "2",
                    "startTimeTBD": true
                  },
                  "teams": {
                    "away": {},
                    "home": {}
                  },
                  "venue": {
                    "name": "SAP Center at San Jose",
                    "link": "/api/v1/venues/null"
                  },
                  "content": {
                    "link": "/api/v1/game/2017020851/content"
                  }
                }
              ],
              "events": [
                {}
              ],
              "matches": [
                {}
              ]
            }
          ]
        },
        "shortName": "San Jose",
        "officialSiteUrl": "http://www.sjsharks.com",
        "franchiseId": 29,
        "active": true
      },
      "home": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "venue": {
          "name": "SAP Center at San Jose",
          "link": "/api/v1/venues/null",
          "city": "San Jose",
          "timeZone": {
            "id": "America/Los_Angeles",
            "offset": -8,
            "tz": "PST"
          }
        },
        "abbreviation": "SJS",
        "triCode": "SJS",
        "teamName": "Sharks",
        "locationName": "San Jose",
        "firstYearOfPlay": 1990,
        "division": {
          "id": 15,
          "name": "Pacific",
          "link": "/api/v1/divisions/15"
        },
        "conference": {
          "id": 5,
          "name": "Western",
          "link": "/api/v1/conferences/5"
        },
        "franchise": {
          "id": 29,
          "name": "Sharks",
          "link": "/api/v1/franchises/29"
        },
        "roster": {
          "roster": [
            {
              "person": {
                "id": 8466138,
                "fullName": "Joe Thornton",
                "link": "/api/v1/people/8466138"
              },
              "jerseyNumber": 19,
              "position": {
                "code": "C",
                "name": "Center",
                "type": "Forward",
                "abbreviation": "C"
              }
            }
          ]
        },
        "nextGameSchedule": {
          "totalItems": 1,
          "totalEvents": 0,
          "totalGames": 1,
          "totalMatches": 0,
          "dates": [
            {
              "date": "2018-02-10",
              "totalItems": 1,
              "totalEvents": 0,
              "totalGames": 1,
              "totalMatches": 0,
              "games": [
                {
                  "gamePk": 2017020851,
                  "link": "/api/v1/game/2017020851/feed/live",
                  "gameType": "R",
                  "season": "20172018",
                  "gameDate": "2018-02-11T03:00:00Z",
                  "status": {
                    "abstractGameState": "Live",
                    "codedGameState": "3",
                    "detailedState": "In Progress",
                    "statusCode": "2",
                    "startTimeTBD": true
                  },
                  "teams": {
                    "away": {},
                    "home": {}
                  },
                  "venue": {
                    "name": "SAP Center at San Jose",
                    "link": "/api/v1/venues/null"
                  },
                  "content": {
                    "link": "/api/v1/game/2017020851/content"
                  }
                }
              ],
              "events": [
                {}
              ],
              "matches": [
                {}
              ]
            }
          ]
        },
        "shortName": "San Jose",
        "officialSiteUrl": "http://www.sjsharks.com",
        "franchiseId": 29,
        "active": true
      }
    },
    "players": {
      "id": 8466138,
      "fullName": "Joe Thornton",
      "link": "/api/v1/people/8466138",
      "firstName": "Joe",
      "lastName": "Thornton",
      "primaryNumber": "19",
      "birthDate": "1979-07-02",
      "currentAge": 38,
      "birthCity": "London",
      "birthStateProvince": "ON",
      "birthCountry": "CAN",
      "nationality": "CAN",
      "height": "6' 4\"",
      "weight": 220,
      "active": true,
      "alternateCaptain": true,
      "captain": true,
      "rookie": true,
      "shootsCatches": "L",
      "rosterStatus": "I",
      "currentTeam": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28"
      },
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      }
    },
    "venue": {
      "name": "SAP Center at San Jose",
      "link": "/api/v1/venues/null"
    }
  },
  "liveData": {
    "plays": {
      "allPlays": [
        {
          "players": [
            {
              "player": {
                "id": 8476881,
                "fullName": "Tomas Hertl",
                "link": "/api/v1/people/8476881"
              },
              "playerType": "Winner"
            }
          ],
          "result": {
            "event": "Game End",
            "eventCode": "SJS505",
            "eventTypeId": "GAME_END",
            "description": "Game End"
          },
          "about": {
            "eventIdx": 315,
            "eventId": 505,
            "period": 3,
            "periodType": "REGULAR",
            "ordinalNum": "3rd",
            "periodTime": "20:00",
            "periodTimeRemaining": "00:00",
            "dateTime": "2018-02-11T05:30:42Z",
            "goals": {
              "away": 4,
              "home": 6
            }
          },
          "coordinates": {
            "x": 0,
            "y": 0
          },
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "triCode": "SJS"
          }
        }
      ],
      "scoringPlays": [
        0
      ],
      "penaltyPlays": [
        0
      ],
      "playsByPeriod": [
        {
          "startIndex": 0,
          "plays": [
            0
          ],
          "endIndex": 114
        }
      ],
      "currentPlay": {
        "players": [
          {
            "player": {
              "id": 8476881,
              "fullName": "Tomas Hertl",
              "link": "/api/v1/people/8476881"
            },
            "playerType": "Winner"
          }
        ],
        "result": {
          "event": "Game End",
          "eventCode": "SJS505",
          "eventTypeId": "GAME_END",
          "description": "Game End"
        },
        "about": {
          "eventIdx": 315,
          "eventId": 505,
          "period": 3,
          "periodType": "REGULAR",
          "ordinalNum": "3rd",
          "periodTime": "20:00",
          "periodTimeRemaining": "00:00",
          "dateTime": "2018-02-11T05:30:42Z",
          "goals": {
            "away": 4,
            "home": 6
          }
        },
        "coordinates": {
          "x": 0,
          "y": 0
        },
        "team": {
          "id": 28,
          "name": "San Jose Sharks",
          "link": "/api/v1/teams/28",
          "triCode": "SJS"
        }
      }
    },
    "linescore": {
      "currentPeriod": 3,
      "currentPeriodOrdinal": "3rd",
      "currentPeriodTimeRemaining": "Final",
      "periods": [
        {
          "periodType": "REGULAR",
          "startTime": "2018-02-11T03:09:50Z",
          "endTime": "2018-02-11T03:44:47Z",
          "num": 1,
          "ordinalNum": "1st",
          "home": {
            "goals": 2,
            "shotsOnGoal": 14,
            "rinkSide": "left"
          },
          "away": {
            "goals": 0,
            "shotsOnGoal": 9,
            "rinkSide": "right"
          }
        }
      ],
      "shootoutInfo": {
        "away": {
          "scores": 0,
          "attempts": 0
        },
        "home": {
          "scores": 0,
          "attempts": 0
        }
      },
      "teams": {
        "home": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "goals": 6,
          "shotsOnGoal": 30,
          "goaliePulled": true,
          "numSkaters": 5,
          "powerPlay": true
        },
        "away": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "goals": 6,
          "shotsOnGoal": 30,
          "goaliePulled": true,
          "numSkaters": 5,
          "powerPlay": true
        }
      },
      "powerPlayStrength": "Even",
      "hasShootout": true,
      "intermissionInfo": {
        "intermissionTimeRemaining": 0,
        "intermissionTimeElapsed": 0,
        "inIntermission": true
      },
      "powerPlayInfo": {
        "situationTimeRemaining": 0,
        "situationTimeElapsed": 72,
        "inSituation": true
      }
    },
    "boxscore": {
      "teams": {
        "away": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "teamStats": {
            "teamSkaterStats": {
              "goals": 6,
              "pim": 6,
              "shots": 30,
              "powerPlayPercentage": "0.0",
              "powerPlayGoals": 0,
              "powerPlayOpportunities": 1,
              "faceOffWinPercentage": "59.3",
              "blocked": 21,
              "takeaways": 9,
              "giveaways": 6,
              "hits": 15
            }
          },
          "players": {
            "person": {
              "id": 8471709,
              "fullName": "Marc-Edouard Vlasic",
              "link": "/api/v1/people/8471709",
              "shootsCatches": "L",
              "rosterStatus": "Y"
            },
            "jerseyNumber": "44",
            "position": {
              "code": "D",
              "name": "Defenseman",
              "type": "Defenseman",
              "abbreviation": "D"
            },
            "stats": {
              "skaterStats": {
                "timeOnIce": "23:04",
                "assists": 0,
                "goals": 0,
                "shots": 2,
                "hits": 0,
                "powerPlayGoals": 0,
                "powerPlayAssists": 0,
                "penaltyMinutes": 0,
                "faceOffWins": 0,
                "faceoffTaken": 0,
                "takeaways": 0,
                "giveaways": 1,
                "shortHandedGoals": 0,
                "shortHandedAssists": 0,
                "blocked": 0,
                "plusMinus": 1,
                "evenTimeOnIce": "18:12",
                "powerPlayTimeOnIce": "1:07",
                "shortHandedTimeOnIce": "3:45"
              }
            }
          },
          "goalies": [
            0
          ],
          "skaters": [
            0
          ],
          "onIce": [
            0
          ],
          "onIcePlus": [
            {
              "playerId": 8477180,
              "shiftDuration": 458,
              "stamina": 33
            }
          ],
          "scratches": [
            0
          ],
          "penaltyBox": [
            0
          ],
          "coaches": [
            {
              "person": {
                "fullName": "Peter DeBoer",
                "link": "/api/v1/people/null"
              },
              "position": {
                "code": "HC",
                "name": "Head Coach",
                "type": "Head Coach",
                "abbreviation": "Head Coach"
              }
            }
          ]
        },
        "home": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "teamStats": {
            "teamSkaterStats": {
              "goals": 6,
              "pim": 6,
              "shots": 30,
              "powerPlayPercentage": "0.0",
              "powerPlayGoals": 0,
              "powerPlayOpportunities": 1,
              "faceOffWinPercentage": "59.3",
              "blocked": 21,
              "takeaways": 9,
              "giveaways": 6,
              "hits": 15
            }
          },
          "players": {
            "person": {
              "id": 8471709,
              "fullName": "Marc-Edouard Vlasic",
              "link": "/api/v1/people/8471709",
              "shootsCatches": "L",
              "rosterStatus": "Y"
            },
            "jerseyNumber": "44",
            "position": {
              "code": "D",
              "name": "Defenseman",
              "type": "Defenseman",
              "abbreviation": "D"
            },
            "stats": {
              "skaterStats": {
                "timeOnIce": "23:04",
                "assists": 0,
                "goals": 0,
                "shots": 2,
                "hits": 0,
                "powerPlayGoals": 0,
                "powerPlayAssists": 0,
                "penaltyMinutes": 0,
                "faceOffWins": 0,
                "faceoffTaken": 0,
                "takeaways": 0,
                "giveaways": 1,
                "shortHandedGoals": 0,
                "shortHandedAssists": 0,
                "blocked": 0,
                "plusMinus": 1,
                "evenTimeOnIce": "18:12",
                "powerPlayTimeOnIce": "1:07",
                "shortHandedTimeOnIce": "3:45"
              }
            }
          },
          "goalies": [
            0
          ],
          "skaters": [
            0
          ],
          "onIce": [
            0
          ],
          "onIcePlus": [
            {
              "playerId": 8477180,
              "shiftDuration": 458,
              "stamina": 33
            }
          ],
          "scratches": [
            0
          ],
          "penaltyBox": [
            0
          ],
          "coaches": [
            {
              "person": {
                "fullName": "Peter DeBoer",
                "link": "/api/v1/people/null"
              },
              "position": {
                "code": "HC",
                "name": "Head Coach",
                "type": "Head Coach",
                "abbreviation": "Head Coach"
              }
            }
          ]
        }
      },
      "officials": [
        {
          "official": {
            "id": 2071,
            "fullName": "Tim Peel",
            "link": "/api/v1/people/2071"
          },
          "officialType": "Linesman"
        }
      ]
    },
    "decisions": {
      "winner": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "loser": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "firstStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "secondStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "thirdStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      }
    }
  }
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getGameDiff-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Game](#schemagame)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-players">players</h1>

## getPlayer

<a id="opIdgetPlayer"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/people/{id} \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/people/{id} HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/people/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/people/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/people/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/people/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/people/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/people/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /people/{id}`

*Get an NHL player.*

<h3 id="getPlayer-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the player.|

> Example responses

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 8466138,
      "fullName": "Joe Thornton",
      "link": "/api/v1/people/8466138",
      "firstName": "Joe",
      "lastName": "Thornton",
      "primaryNumber": "19",
      "birthDate": "1979-07-02",
      "currentAge": 38,
      "birthCity": "London",
      "birthStateProvince": "ON",
      "birthCountry": "CAN",
      "nationality": "CAN",
      "height": "6' 4\"",
      "weight": 220,
      "active": true,
      "alternateCaptain": true,
      "captain": true,
      "rookie": true,
      "shootsCatches": "L",
      "rosterStatus": "I",
      "currentTeam": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28"
      },
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      }
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getPlayer-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Players](#schemaplayers)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getPlayerStats

<a id="opIdgetPlayerStats"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/people/{id}/stats?stats=homeAndAway \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/people/{id}/stats?stats=homeAndAway HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/people/{id}/stats',
  method: 'get',
  data: '?stats=homeAndAway',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/people/{id}/stats?stats=homeAndAway',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/people/{id}/stats',
  params: {
  'stats' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/people/{id}/stats', params={
  'stats': 'homeAndAway'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/people/{id}/stats?stats=homeAndAway");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/people/{id}/stats", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /people/{id}/stats`

*Get specific statistics for an NHL player.*

<h3 id="getPlayerStats-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the player.|
|stats|query|string|true|Stats explanations:|
|season|query|number|false|Return a team's specific season.|

#### Detailed descriptions

**stats**: Stats explanations:
  * `homeAndAway` - Provides a split between home and away games.
  * `byMonth` - Monthly split of stats.
  * `byDayOfWeek` - Split done by day of the week.
  * `goalsByGameSituation` - Shows number on when goals for a player happened like how many in the shootout, how many in each period, etc.
  * `onPaceRegularSeason` - This only works with the current in-progress season and shows projected totals based on current onPaceRegularSeason.
  * `regularSeasonStatRankings` - Returns where someone stands vs the rest of the league for a specific regularSeasonStatRankings
  * `statsSingleSeason` - Obtains single season statistics for a player.
  * `vsConference` - Conference stats split.
  * `vsDivision` - Division stats split.
  * `vsTeam` - Conference stats split.
  * `winLoss` - Very similar to the previous modifier except it provides the W/L/OT split instead of Home and Away.

#### Enumerated Values

|Parameter|Value|
|---|---|
|stats|homeAndAway|
|stats|byDayOfWeek|
|stats|byMonth|
|stats|goalsByGameSituation|
|stats|onPaceRegularSeason|
|stats|regularSeasonStatRankings|
|stats|statsSingleSeason|
|stats|vsConference|
|stats|vsDivision|
|stats|vsTeam|
|stats|winLoss|

> Example responses

```json
{
  "copyright": "string",
  "stats": [
    {
      "type": {
        "displayName": "byDayOfWeek"
      },
      "splits": [
        {
          "season": "20172018",
          "stat": {
            "timeOnIce": "862:13",
            "assists": 23,
            "goals": 13,
            "pim": 38,
            "shots": 75,
            "games": 47,
            "hits": 32,
            "powerPlayGoals": 7,
            "powerPlayPoints": 18,
            "powerPlayTimeOnIce": "168:28",
            "evenTimeOnIce": "692:50",
            "penaltyMinutes": "38",
            "faceOffPct": 52.04,
            "shotPct": 17.3,
            "gameWinningGoals": 1,
            "overTimeGoals": 0,
            "shortHandedGoals": 0,
            "shortHandedPoints": 0,
            "shortHandedTimeOnIce": "00:55",
            "blocked": 18,
            "plusMinus": -9,
            "points": 36,
            "shifts": 1077,
            "timeOnIcePerGame": "18:20",
            "evenTimeOnIcePerGame": "14:44",
            "shortHandedTimeOnIcePerGame": "00:01",
            "powerPlayTimeOnIcePerGame": "03:35",
            "rankPowerPlayGoals": "1st",
            "rankBlockedShots": "405th",
            "rankAssists": "51st",
            "rankShotPct": "246th",
            "rankGoals": "13th",
            "rankHits": "19th",
            "rankPenaltyMinutes": "111th",
            "rankShortHandedGoals": "133rd",
            "rankPlusMinus": "176th",
            "rankShots": "2nd",
            "rankPoints": "20th",
            "rankOvertimeGoals": "9th",
            "rankGamesPlayed": "1st",
            "goalsInFirstPeriod": 6,
            "goalsInSecondPeriod": 3,
            "goalsInThirdPeriod": 4,
            "goalsTrailingByOne": 2,
            "goalsTrailingByTwo": 1,
            "goalsTrailingByThreePlus": 1,
            "goalsWhenTied": 4,
            "goalsLeadingByOne": 2,
            "goalsLeadingByTwo": 3
          },
          "isHome": true,
          "isWin": true,
          "isOT": true,
          "month": 1,
          "dayOfWeek": 1,
          "opponent": {
            "id": 1,
            "name": "New Jersey Devils",
            "link": "/api/v1/teams/1"
          },
          "opponentDivision": {
            "id": 16,
            "name": "Central",
            "link": "/api/v1/divisions/16"
          },
          "opponentConference": {
            "id": 5,
            "name": "Western",
            "link": "/api/v1/conferences/5"
          }
        }
      ]
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getPlayerStats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[PlayerStats](#schemaplayerstats)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-schedule">schedule</h1>

## getSchedule

<a id="opIdgetSchedule"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/schedule \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/schedule HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/schedule',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/schedule',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/schedule',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/schedule', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/schedule");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/schedule", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /schedule`

*Get the NHL game schedule.*

<h3 id="getSchedule-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|expand|query|string|false|Expand explanations:|
|teamId|query|string|false|Limit results to a specific team. Team ids can be found through the teams endpoint|
|startDate|query|string(date)|false|Start date for the search.|
|endDate|query|string(date)|false|End date for the search.|

#### Detailed descriptions

**expand**: Expand explanations:
  * `schedule.brodcasts` - Shows the broadcasts of the game.
  * `schedule.linescore` - Linescore for completed games.
  * `schedule.ticket` - Provides the different places to buy tickets for the upcoming games.
  * `team.schedule.previous` - Same as above but for the last game played.

#### Enumerated Values

|Parameter|Value|
|---|---|
|expand|schedule.brodcasts|
|expand|schedule.linescore|
|expand|schedule.ticket|
|expand|team.schedule.previous|

> Example responses

```json
{
  "copyright": "string",
  "totalItems": 9,
  "totalEvents": 0,
  "totalGames": 9,
  "totalMatches": 0,
  "wait": 10,
  "dates": [
    {
      "date": "2018-02-10",
      "totalItems": 9,
      "totalEvents": 0,
      "totalGames": 9,
      "totalMatches": 0,
      "games": [
        {
          "gamePk": 2017020851,
          "link": "/api/v1/game/2017020851/feed/live",
          "gameType": "R",
          "season": "20172018",
          "gameDate": "2018-02-11T03:00:00Z",
          "status": {
            "abstractGameState": "Final",
            "codedGameState": "7",
            "detailedState": "Final",
            "statusCode": "7",
            "startTimeTBD": true
          },
          "teams": {
            "away": {
              "leagueRecord": {
                "wins": 23,
                "losses": 27,
                "ot": 4,
                "type": "league"
              },
              "score": 4,
              "team": {
                "id": 22,
                "name": "Edmonton Oilers",
                "link": "/api/v1/teams/22"
              }
            },
            "home": {
              "leagueRecord": {
                "wins": 29,
                "losses": 18,
                "ot": 8,
                "type": "league"
              },
              "score": 6,
              "team": {
                "id": 28,
                "name": "San Jose Sharks",
                "link": "/api/v1/teams/28"
              }
            }
          },
          "linescore": {
            "currentPeriod": 3,
            "currentPeriodOrdinal": "3rd",
            "currentPeriodTimeRemaining": "Final",
            "periods": [
              {
                "periodType": "REGULAR",
                "startTime": "2018-02-11T03:09:50Z",
                "endTime": "2018-02-11T03:44:47Z",
                "num": 1,
                "ordinalNum": "1st",
                "home": {
                  "goals": 2,
                  "shotsOnGoal": 14,
                  "rinkSide": "left"
                },
                "away": {
                  "goals": 0,
                  "shotsOnGoal": 9,
                  "rinkSide": "right"
                }
              }
            ],
            "shootoutInfo": {
              "away": {
                "scores": 0,
                "attempts": 0
              },
              "home": {
                "scores": 0,
                "attempts": 0
              }
            },
            "teams": {
              "home": {
                "team": {
                  "id": 28,
                  "name": "San Jose Sharks",
                  "link": "/api/v1/teams/28",
                  "abbreviation": "SJS",
                  "triCode": "SJS"
                },
                "goals": 6,
                "shotsOnGoal": 30,
                "goaliePulled": true,
                "numSkaters": 5,
                "powerPlay": true
              },
              "away": {
                "team": {
                  "id": 28,
                  "name": "San Jose Sharks",
                  "link": "/api/v1/teams/28",
                  "abbreviation": "SJS",
                  "triCode": "SJS"
                },
                "goals": 6,
                "shotsOnGoal": 30,
                "goaliePulled": true,
                "numSkaters": 5,
                "powerPlay": true
              }
            },
            "powerPlayStrength": "Even",
            "hasShootout": true,
            "intermissionInfo": {
              "intermissionTimeRemaining": 0,
              "intermissionTimeElapsed": 0,
              "inIntermission": true
            },
            "powerPlayInfo": {
              "situationTimeRemaining": 0,
              "situationTimeElapsed": 72,
              "inSituation": true
            }
          },
          "venue": {
            "name": "SAP Center at San Jose",
            "link": "/api/v1/venues/null"
          },
          "tickets": [
            {
              "ticketType": "buysell",
              "ticketLink": "http://www.ticketmaster.com/event/090052DD92E620B4?BRAND=ducks&extcmp=tm208344&utm_source=NHL.com&utm_medium=client&utm_campaign=NHL_LEAGUE_ANA&utm_content=SCHEDULE_PAGE&camefrom=CFC_DUCKS_1718_Web_DucksSchedule"
            }
          ],
          "content": {
            "link": "/api/v1/game/2017020851/content"
          }
        }
      ],
      "events": [
        {}
      ],
      "matches": [
        {}
      ]
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getSchedule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Schedule](#schemaschedule)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-standings">standings</h1>

## getStandings

<a id="opIdgetStandings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/standings \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/standings HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/standings',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/standings',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/standings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/standings', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/standings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/standings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /standings`

*Get NHL division standings.*

<h3 id="getStandings-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|season|query|string(date)|false|Standings for a specified season.|
|date|query|string(date)|false|Standings on a specified date.|

> Example responses

```json
{
  "copyright": "string",
  "records": [
    {
      "standingsType": "regularSeason",
      "league": {
        "id": 133,
        "name": "National Hockey League",
        "link": "/api/v1/league/133"
      },
      "division": {
        "id": 15,
        "name": "Pacific",
        "link": "/api/v1/divisions/15"
      },
      "conference": {
        "id": 5,
        "name": "Western",
        "link": "/api/v1/conferences/5"
      },
      "teamRecords": [
        {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28"
          },
          "leagueRecord": {
            "wins": 29,
            "losses": 18,
            "ot": 8,
            "type": "league"
          },
          "goalsAgainst": 154,
          "goalsScored": 162,
          "points": 66,
          "divisionRank": "2",
          "conferenceRank": "7",
          "leagueRank": "11",
          "wildCardRank": "0",
          "row": 26,
          "gamesPlayed": 55,
          "streak": {
            "streakType": "wins",
            "streakNumber": 1,
            "streakCode": "W1"
          },
          "lastUpdated": "2018-02-11T00:57:18Z"
        }
      ]
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getStandings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Standings](#schemastandings)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getStandingsByType

<a id="opIdgetStandingsByType"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/standings/{type} \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/standings/{type} HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/standings/{type}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/standings/{type}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/standings/{type}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/standings/{type}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/standings/{type}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/standings/{type}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /standings/{type}`

*Get NHL standings for a specific standing type.*

<h3 id="getStandingsByType-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|type|path|string|true|Standing types:|

#### Detailed descriptions

**type**: Standing types:
  * `byConference` - Standings by Conference
  * `byDivision` - Standings by Division
  * `byLeague` - Standings by League
  * `divisionLeaders` - Division Leader standings
  * `postseason` - Postseason Standings
  * `preseason` - Preseason Standings
  * `regularSeason` - Regular Season Standings
  * `wildCard` - Wild card standings
  * `wildCardWithLeaders` - Wild card standings with Division Leaders

#### Enumerated Values

|Parameter|Value|
|---|---|
|type|byConference|
|type|byDivision|
|type|byLeague|
|type|divisionLeaders|
|type|postseason|
|type|preseason|
|type|regularSeason|
|type|wildCard|
|type|wildCardWithLeaders|

> Example responses

```json
{
  "copyright": "string",
  "records": [
    {
      "standingsType": "regularSeason",
      "league": {
        "id": 133,
        "name": "National Hockey League",
        "link": "/api/v1/league/133"
      },
      "division": {
        "id": 15,
        "name": "Pacific",
        "link": "/api/v1/divisions/15"
      },
      "conference": {
        "id": 5,
        "name": "Western",
        "link": "/api/v1/conferences/5"
      },
      "teamRecords": [
        {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28"
          },
          "leagueRecord": {
            "wins": 29,
            "losses": 18,
            "ot": 8,
            "type": "league"
          },
          "goalsAgainst": 154,
          "goalsScored": 162,
          "points": 66,
          "divisionRank": "2",
          "conferenceRank": "7",
          "leagueRank": "11",
          "wildCardRank": "0",
          "row": 26,
          "gamesPlayed": 55,
          "streak": {
            "streakType": "wins",
            "streakNumber": 1,
            "streakCode": "W1"
          },
          "lastUpdated": "2018-02-11T00:57:18Z"
        }
      ]
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getStandingsByType-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Standings](#schemastandings)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getStandingTypes

<a id="opIdgetStandingTypes"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/standingsTypes \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/standingsTypes HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/standingsTypes',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/standingsTypes',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/standingsTypes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/standingsTypes', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/standingsTypes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/standingsTypes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /standingsTypes`

*Get all available NHL standing types.*

> Example responses

```json
[
  {
    "name": "regularSeason",
    "description": "Regular Season Standings"
  }
]
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getStandingTypes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[StandingTypes](#schemastandingtypes)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-stats">stats</h1>

## getStatTypes

<a id="opIdgetStatTypes"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/statTypes \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/statTypes HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/statTypes',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/statTypes',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/statTypes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/statTypes', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/statTypes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/statTypes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /statTypes`

*Get all available NHL statistic types.*

> Example responses

```json
[
  {
    "displayName": "byDayOfWeek"
  }
]
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getStatTypes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[StatTypes](#schemastattypes)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="NHL-API-teams">teams</h1>

## getTeams

<a id="opIdgetTeams"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/teams \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/teams HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/teams',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/teams',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/teams',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/teams', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/teams");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/teams", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /teams`

*Get all NHL teams.*

<h3 id="getTeams-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|expand|query|string|false|Expand your response for some additional data.|
|season|query|number|false|Return a team's specific season.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|expand|team.roster|
|expand|team.schedule.next|
|expand|team.schedule.previous|

> Example responses

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 28,
      "name": "San Jose Sharks",
      "link": "/api/v1/teams/28",
      "venue": {
        "name": "SAP Center at San Jose",
        "link": "/api/v1/venues/null",
        "city": "San Jose",
        "timeZone": {
          "id": "America/Los_Angeles",
          "offset": -8,
          "tz": "PST"
        }
      },
      "abbreviation": "SJS",
      "triCode": "SJS",
      "teamName": "Sharks",
      "locationName": "San Jose",
      "firstYearOfPlay": 1990,
      "division": {
        "id": 15,
        "name": "Pacific",
        "link": "/api/v1/divisions/15"
      },
      "conference": {
        "id": 5,
        "name": "Western",
        "link": "/api/v1/conferences/5"
      },
      "franchise": {
        "id": 29,
        "name": "Sharks",
        "link": "/api/v1/franchises/29"
      },
      "roster": {
        "roster": [
          {
            "person": {
              "id": 8466138,
              "fullName": "Joe Thornton",
              "link": "/api/v1/people/8466138"
            },
            "jerseyNumber": 19,
            "position": {
              "code": "C",
              "name": "Center",
              "type": "Forward",
              "abbreviation": "C"
            }
          }
        ]
      },
      "nextGameSchedule": {
        "totalItems": 1,
        "totalEvents": 0,
        "totalGames": 1,
        "totalMatches": 0,
        "dates": [
          {
            "date": "2018-02-10",
            "totalItems": 1,
            "totalEvents": 0,
            "totalGames": 1,
            "totalMatches": 0,
            "games": [
              {
                "gamePk": 2017020851,
                "link": "/api/v1/game/2017020851/feed/live",
                "gameType": "R",
                "season": "20172018",
                "gameDate": "2018-02-11T03:00:00Z",
                "status": {
                  "abstractGameState": "Live",
                  "codedGameState": "3",
                  "detailedState": "In Progress",
                  "statusCode": "2",
                  "startTimeTBD": true
                },
                "teams": {
                  "away": {
                    "leagueRecord": {},
                    "score": 0,
                    "team": {}
                  },
                  "home": {
                    "leagueRecord": {},
                    "score": 2,
                    "team": {}
                  }
                },
                "venue": {
                  "name": "SAP Center at San Jose",
                  "link": "/api/v1/venues/null"
                },
                "content": {
                  "link": "/api/v1/game/2017020851/content"
                }
              }
            ],
            "events": [
              {}
            ],
            "matches": [
              {}
            ]
          }
        ]
      },
      "shortName": "San Jose",
      "officialSiteUrl": "http://www.sjsharks.com",
      "franchiseId": 29,
      "active": true
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getTeams-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Teams](#schemateams)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getTeam

<a id="opIdgetTeam"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/teams/{id} \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/teams/{id} HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/teams/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/teams/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/teams/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/teams/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/teams/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/teams/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /teams/{id}`

*Get an NHL team.*

<h3 id="getTeam-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the team.|
|expand|query|string|false|Expand your response for some additional data.|
|season|query|number|false|Return a team's specific season.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|expand|team.roster|
|expand|team.schedule.next|
|expand|team.schedule.previous|

> Example responses

```json
{
  "id": 28,
  "name": "San Jose Sharks",
  "link": "/api/v1/teams/28",
  "venue": {
    "name": "SAP Center at San Jose",
    "link": "/api/v1/venues/null",
    "city": "San Jose",
    "timeZone": {
      "id": "America/Los_Angeles",
      "offset": -8,
      "tz": "PST"
    }
  },
  "abbreviation": "SJS",
  "triCode": "SJS",
  "teamName": "Sharks",
  "locationName": "San Jose",
  "firstYearOfPlay": 1990,
  "division": {
    "id": 15,
    "name": "Pacific",
    "link": "/api/v1/divisions/15"
  },
  "conference": {
    "id": 5,
    "name": "Western",
    "link": "/api/v1/conferences/5"
  },
  "franchise": {
    "id": 29,
    "name": "Sharks",
    "link": "/api/v1/franchises/29"
  },
  "roster": {
    "roster": [
      {
        "person": {
          "id": 8466138,
          "fullName": "Joe Thornton",
          "link": "/api/v1/people/8466138"
        },
        "jerseyNumber": 19,
        "position": {
          "code": "C",
          "name": "Center",
          "type": "Forward",
          "abbreviation": "C"
        }
      }
    ]
  },
  "nextGameSchedule": {
    "totalItems": 1,
    "totalEvents": 0,
    "totalGames": 1,
    "totalMatches": 0,
    "dates": [
      {
        "date": "2018-02-10",
        "totalItems": 1,
        "totalEvents": 0,
        "totalGames": 1,
        "totalMatches": 0,
        "games": [
          {
            "gamePk": 2017020851,
            "link": "/api/v1/game/2017020851/feed/live",
            "gameType": "R",
            "season": "20172018",
            "gameDate": "2018-02-11T03:00:00Z",
            "status": {
              "abstractGameState": "Live",
              "codedGameState": "3",
              "detailedState": "In Progress",
              "statusCode": "2",
              "startTimeTBD": true
            },
            "teams": {
              "away": {
                "leagueRecord": {
                  "wins": 23,
                  "losses": 26,
                  "ot": 4,
                  "type": "league"
                },
                "score": 0,
                "team": {
                  "id": 22,
                  "name": "Edmonton Oilers",
                  "link": "/api/v1/teams/22"
                }
              },
              "home": {
                "leagueRecord": {
                  "wins": 28,
                  "losses": 18,
                  "ot": 8,
                  "type": "league"
                },
                "score": 2,
                "team": {
                  "id": 28,
                  "name": "San Jose Sharks",
                  "link": "/api/v1/teams/28"
                }
              }
            },
            "venue": {
              "name": "SAP Center at San Jose",
              "link": "/api/v1/venues/null"
            },
            "content": {
              "link": "/api/v1/game/2017020851/content"
            }
          }
        ],
        "events": [
          {}
        ],
        "matches": [
          {}
        ]
      }
    ]
  },
  "shortName": "San Jose",
  "officialSiteUrl": "http://www.sjsharks.com",
  "franchiseId": 29,
  "active": true
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getTeam-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Team](#schemateam)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getTeamRoster

<a id="opIdgetTeamRoster"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/teams/{id}/roster \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/teams/{id}/roster HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/teams/{id}/roster',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/teams/{id}/roster',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/teams/{id}/roster',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/teams/{id}/roster', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/teams/{id}/roster");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/teams/{id}/roster", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /teams/{id}/roster`

*Get an NHL team's roster.*

<h3 id="getTeamRoster-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the team.|
|season|query|number|false|Return a team's specific season.|

> Example responses

```json
{
  "copyright": "string",
  "teams": [
    {
      "person": {
        "id": 8466138,
        "fullName": "Joe Thornton",
        "link": "/api/v1/people/8466138"
      },
      "jerseyNumber": 19,
      "position": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      }
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getTeamRoster-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Rosters](#schemarosters)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getTeamStats

<a id="opIdgetTeamStats"></a>

> Code samples

```shell
# You can also use wget
curl -X GET https://statsapi.web.nhl.com/api/v1/teams/{id}/stats \
  -H 'Accept: application/json'

```

```http
GET https://statsapi.web.nhl.com/api/v1/teams/{id}/stats HTTP/1.1
Host: statsapi.web.nhl.com

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://statsapi.web.nhl.com/api/v1/teams/{id}/stats',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://statsapi.web.nhl.com/api/v1/teams/{id}/stats',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://statsapi.web.nhl.com/api/v1/teams/{id}/stats',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://statsapi.web.nhl.com/api/v1/teams/{id}/stats', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://statsapi.web.nhl.com/api/v1/teams/{id}/stats");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://statsapi.web.nhl.com/api/v1/teams/{id}/stats", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /teams/{id}/stats`

*Get all statistics for an NHL team.*

<h3 id="getTeamStats-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|number|true|The ID of the team.|

> Example responses

```json
{
  "copyright": "string",
  "stats": [
    {
      "type": {
        "displayName": "statsSingleSeason"
      },
      "splits": [
        {
          "stat": {
            "gamesPlayed": 55,
            "wins": 29,
            "losses": 18,
            "ot": 8,
            "pts": 66,
            "ptPctg": "60.0",
            "goalsPerGame": 2.891,
            "goalsAgainstPerGame": 2.745,
            "evGGARatio": 0.8532,
            "powerPlayPercentage": "23.9",
            "powerPlayGoals": 44,
            "powerPlayGoalsAgainst": 26,
            "powerPlayOpportunities": 184,
            "penaltyKillPercentage": "84.6",
            "shotsPerGame": 32.8,
            "shotsAllowed": 30.2182,
            "winScoreFirst": 0.679,
            "winOppScoreFirst": 0.37,
            "winLeadFirstPer": 0.85,
            "winLeadSecondPer": 0.952,
            "winOutshootOpp": 0.467,
            "winOutshotByOpp": 0.6,
            "faceOffsTaken": 3300,
            "faceOffsWon": 1675,
            "faceOffsLost": 1625,
            "faceOffWinPercentage": "50.8",
            "shootingPctg": 8.8,
            "savePctg": 0.909
          },
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28"
          }
        }
      ]
    }
  ]
}
```

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

<h3 id="getTeamStats-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[TeamStats](#schemateamstats)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSconference">Conference</h2>

<a id="schemaconference"></a>

```json
{
  "id": 5,
  "name": "Eastern",
  "link": "/api/v1/conferences/5",
  "abbreviation": "E",
  "shortName": "East",
  "active": true
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|id|number|false|No description|
|name|string|false|No description|
|link|string(uri)|false|No description|
|abbreviation|string|false|No description|
|shortName|string|false|No description|
|active|boolean|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|name|Eastern|
|name|Western|
|name|World Cup of Hockey|
|abbreviation|E|
|abbreviation|W|
|abbreviation|WCH|
|shortName|East|
|shortName|West|
|shortName|WCup|

<h2 id="tocSconferences">Conferences</h2>

<a id="schemaconferences"></a>

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 5,
      "name": "Eastern",
      "link": "/api/v1/conferences/5",
      "abbreviation": "E",
      "shortName": "East",
      "active": true
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|teams|[[Conference](#schemaconference)]|false|No description|

<h2 id="tocSdivision">Division</h2>

<a id="schemadivision"></a>

```json
{
  "id": 15,
  "name": "Pacific",
  "link": "/api/v1/divisions/15",
  "abbreviation": "P",
  "conference": {
    "id": 5,
    "name": "Western",
    "link": "/api/v1/conferences/5"
  },
  "active": true
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|id|number|false|No description|
|name|string|false|No description|
|link|string(uri)|false|No description|
|abbreviation|string|false|No description|
|conference|object|false|No description|
|» id|number|false|No description|
|» name|string|false|No description|
|» link|string(uri)|false|No description|
|active|boolean|false|No description|

<h2 id="tocSdivisions">Divisions</h2>

<a id="schemadivisions"></a>

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 15,
      "name": "Pacific",
      "link": "/api/v1/divisions/15",
      "abbreviation": "P",
      "conference": {
        "id": 5,
        "name": "Western",
        "link": "/api/v1/conferences/5"
      },
      "active": true
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|teams|[[Division](#schemadivision)]|false|No description|

<h2 id="tocSdraft">Draft</h2>

<a id="schemadraft"></a>

```json
{
  "copyright": "string",
  "drafts": [
    {
      "draftYear": 2017,
      "rounds": [
        {
          "roundNumber": 1,
          "round": "1",
          "picks": [
            {
              "year": 2017,
              "round": "1",
              "pickOverall": 1,
              "pickInRound": 1,
              "team": {
                "id": 1,
                "name": "New Jersey Devils",
                "link": "/api/v1/teams/1"
              },
              "prospect": {
                "id": 65242,
                "fullName": "Nico Hischier",
                "link": "/api/v1/draft/prospects/65242"
              }
            }
          ]
        }
      ]
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|drafts|[object]|false|No description|
|» draftYear|number|false|No description|
|» rounds|[object]|false|No description|
|»» roundNumber|number|false|No description|
|»» round|number|false|No description|
|»» picks|[object]|false|No description|
|»»» year|number|false|No description|
|»»» round|string|false|No description|
|»»» pickOverall|number|false|No description|
|»»» pickInRound|number|false|No description|
|»»» team|object|false|No description|
|»»»» id|number|false|No description|
|»»»» name|string|false|No description|
|»»»» link|string(uri)|false|No description|
|»»» prospect|object|false|No description|
|»»»» id|number|false|No description|
|»»»» fullName|string|false|No description|
|»»»» link|string(uri)|false|No description|

<h2 id="tocSdraftprospect">DraftProspect</h2>

<a id="schemadraftprospect"></a>

```json
{
  "id": 65242,
  "fullName": "Nico Hischier",
  "link": "/api/v1/draft/prospects/65242",
  "firstName": "Nico",
  "lastName": "Hischier",
  "birthDate": "1999-01-04",
  "birthCity": "Naters",
  "birthCountry": "CHE",
  "nationality": "CHE",
  "height": "6' 2\"",
  "weight": 179,
  "shootsCatches": "L",
  "primaryPosition": {
    "code": "C",
    "name": "Center",
    "type": "Forward",
    "abbreviation": "C"
  },
  "prospectCategory": {
    "id": 1,
    "shortName": "NA Skater",
    "name": "North American Skater"
  },
  "amateurTeam": {
    "link": "/api/v1/teams/null"
  },
  "amateurLeague": {
    "link": "/api/v1/league/null"
  },
  "ranks": {}
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|id|number|false|No description|
|fullName|string|false|No description|
|link|string(uri)|false|No description|
|firstName|string|false|No description|
|lastName|string|false|No description|
|birthDate|string(date)|false|No description|
|birthCity|string|false|No description|
|birthCountry|string|false|No description|
|nationality|string|false|No description|
|height|string|false|No description|
|weight|number|false|No description|
|shootsCatches|string|false|No description|
|primaryPosition|object|false|No description|
|» code|string|false|No description|
|» name|string|false|No description|
|» type|string|false|No description|
|» abbreviation|string|false|No description|
|prospectCategory|object|false|No description|
|» id|number|false|No description|
|» shortName|string|false|No description|
|» name|string|false|No description|
|amateurTeam|object|false|No description|
|» link|string(uri)|false|No description|
|amateurLeague|object|false|No description|
|» link|string(uri)|false|No description|
|ranks|object|false|No description|

<h2 id="tocSdraftprospects">DraftProspects</h2>

<a id="schemadraftprospects"></a>

```json
{
  "copyright": "string",
  "prospects": [
    {
      "id": 65242,
      "fullName": "Nico Hischier",
      "link": "/api/v1/draft/prospects/65242",
      "firstName": "Nico",
      "lastName": "Hischier",
      "birthDate": "1999-01-04",
      "birthCity": "Naters",
      "birthCountry": "CHE",
      "nationality": "CHE",
      "height": "6' 2\"",
      "weight": 179,
      "shootsCatches": "L",
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      },
      "prospectCategory": {
        "id": 1,
        "shortName": "NA Skater",
        "name": "North American Skater"
      },
      "amateurTeam": {
        "link": "/api/v1/teams/null"
      },
      "amateurLeague": {
        "link": "/api/v1/league/null"
      },
      "ranks": {}
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|prospects|[[DraftProspect](#schemadraftprospect)]|false|No description|

<h2 id="tocSerror">Error</h2>

<a id="schemaerror"></a>

```json
{
  "messageNumber": 10,
  "message": "Object not found"
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|messageNumber|number|false|No description|
|message|string|false|No description|

<h2 id="tocSfranchise">Franchise</h2>

<a id="schemafranchise"></a>

```json
{
  "id": 29,
  "name": "Sharks",
  "link": "/api/v1/franchises/29"
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|id|number|false|No description|
|name|string|false|No description|
|link|string(uri)|false|No description|

<h2 id="tocSgame">Game</h2>

<a id="schemagame"></a>

```json
{
  "copyright": "string",
  "gamePk": 2017020851,
  "link": "/api/v1/game/2017020851/feed/live",
  "metaData": {
    "wait": 10,
    "timeStamp": "20180211_054345"
  },
  "gameData": {
    "game": {
      "pk": 2017020851,
      "season": "20172018",
      "type": "R"
    },
    "datetime": {
      "dateTime": "2018-02-11T03:00:00Z",
      "endDateTime": "2018-02-11T05:30:42Z"
    },
    "status": {
      "abstractGameState": "Final",
      "codedGameState": "7",
      "detailedState": "Final",
      "statusCode": "7",
      "startTimeTBD": true
    },
    "teams": {
      "away": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "venue": {
          "name": "SAP Center at San Jose",
          "link": "/api/v1/venues/null",
          "city": "San Jose",
          "timeZone": {
            "id": "America/Los_Angeles",
            "offset": -8,
            "tz": "PST"
          }
        },
        "abbreviation": "SJS",
        "triCode": "SJS",
        "teamName": "Sharks",
        "locationName": "San Jose",
        "firstYearOfPlay": 1990,
        "division": {
          "id": 15,
          "name": "Pacific",
          "link": "/api/v1/divisions/15"
        },
        "conference": {
          "id": 5,
          "name": "Western",
          "link": "/api/v1/conferences/5"
        },
        "franchise": {
          "id": 29,
          "name": "Sharks",
          "link": "/api/v1/franchises/29"
        },
        "roster": {
          "roster": [
            {
              "person": {
                "id": 8466138,
                "fullName": "Joe Thornton",
                "link": "/api/v1/people/8466138"
              },
              "jerseyNumber": 19,
              "position": {
                "code": "C",
                "name": "Center",
                "type": "Forward",
                "abbreviation": "C"
              }
            }
          ]
        },
        "nextGameSchedule": {
          "totalItems": 1,
          "totalEvents": 0,
          "totalGames": 1,
          "totalMatches": 0,
          "dates": [
            {
              "date": "2018-02-10",
              "totalItems": 1,
              "totalEvents": 0,
              "totalGames": 1,
              "totalMatches": 0,
              "games": [
                {
                  "gamePk": 2017020851,
                  "link": "/api/v1/game/2017020851/feed/live",
                  "gameType": "R",
                  "season": "20172018",
                  "gameDate": "2018-02-11T03:00:00Z",
                  "status": {
                    "abstractGameState": "Live",
                    "codedGameState": "3",
                    "detailedState": "In Progress",
                    "statusCode": "2",
                    "startTimeTBD": true
                  },
                  "teams": {
                    "away": {},
                    "home": {}
                  },
                  "venue": {
                    "name": "SAP Center at San Jose",
                    "link": "/api/v1/venues/null"
                  },
                  "content": {
                    "link": "/api/v1/game/2017020851/content"
                  }
                }
              ],
              "events": [
                {}
              ],
              "matches": [
                {}
              ]
            }
          ]
        },
        "shortName": "San Jose",
        "officialSiteUrl": "http://www.sjsharks.com",
        "franchiseId": 29,
        "active": true
      },
      "home": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "venue": {
          "name": "SAP Center at San Jose",
          "link": "/api/v1/venues/null",
          "city": "San Jose",
          "timeZone": {
            "id": "America/Los_Angeles",
            "offset": -8,
            "tz": "PST"
          }
        },
        "abbreviation": "SJS",
        "triCode": "SJS",
        "teamName": "Sharks",
        "locationName": "San Jose",
        "firstYearOfPlay": 1990,
        "division": {
          "id": 15,
          "name": "Pacific",
          "link": "/api/v1/divisions/15"
        },
        "conference": {
          "id": 5,
          "name": "Western",
          "link": "/api/v1/conferences/5"
        },
        "franchise": {
          "id": 29,
          "name": "Sharks",
          "link": "/api/v1/franchises/29"
        },
        "roster": {
          "roster": [
            {
              "person": {
                "id": 8466138,
                "fullName": "Joe Thornton",
                "link": "/api/v1/people/8466138"
              },
              "jerseyNumber": 19,
              "position": {
                "code": "C",
                "name": "Center",
                "type": "Forward",
                "abbreviation": "C"
              }
            }
          ]
        },
        "nextGameSchedule": {
          "totalItems": 1,
          "totalEvents": 0,
          "totalGames": 1,
          "totalMatches": 0,
          "dates": [
            {
              "date": "2018-02-10",
              "totalItems": 1,
              "totalEvents": 0,
              "totalGames": 1,
              "totalMatches": 0,
              "games": [
                {
                  "gamePk": 2017020851,
                  "link": "/api/v1/game/2017020851/feed/live",
                  "gameType": "R",
                  "season": "20172018",
                  "gameDate": "2018-02-11T03:00:00Z",
                  "status": {
                    "abstractGameState": "Live",
                    "codedGameState": "3",
                    "detailedState": "In Progress",
                    "statusCode": "2",
                    "startTimeTBD": true
                  },
                  "teams": {
                    "away": {},
                    "home": {}
                  },
                  "venue": {
                    "name": "SAP Center at San Jose",
                    "link": "/api/v1/venues/null"
                  },
                  "content": {
                    "link": "/api/v1/game/2017020851/content"
                  }
                }
              ],
              "events": [
                {}
              ],
              "matches": [
                {}
              ]
            }
          ]
        },
        "shortName": "San Jose",
        "officialSiteUrl": "http://www.sjsharks.com",
        "franchiseId": 29,
        "active": true
      }
    },
    "players": {
      "id": 8466138,
      "fullName": "Joe Thornton",
      "link": "/api/v1/people/8466138",
      "firstName": "Joe",
      "lastName": "Thornton",
      "primaryNumber": "19",
      "birthDate": "1979-07-02",
      "currentAge": 38,
      "birthCity": "London",
      "birthStateProvince": "ON",
      "birthCountry": "CAN",
      "nationality": "CAN",
      "height": "6' 4\"",
      "weight": 220,
      "active": true,
      "alternateCaptain": true,
      "captain": true,
      "rookie": true,
      "shootsCatches": "L",
      "rosterStatus": "I",
      "currentTeam": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28"
      },
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      }
    },
    "venue": {
      "name": "SAP Center at San Jose",
      "link": "/api/v1/venues/null"
    }
  },
  "liveData": {
    "plays": {
      "allPlays": [
        {
          "players": [
            {
              "player": {
                "id": 8476881,
                "fullName": "Tomas Hertl",
                "link": "/api/v1/people/8476881"
              },
              "playerType": "Winner"
            }
          ],
          "result": {
            "event": "Game End",
            "eventCode": "SJS505",
            "eventTypeId": "GAME_END",
            "description": "Game End"
          },
          "about": {
            "eventIdx": 315,
            "eventId": 505,
            "period": 3,
            "periodType": "REGULAR",
            "ordinalNum": "3rd",
            "periodTime": "20:00",
            "periodTimeRemaining": "00:00",
            "dateTime": "2018-02-11T05:30:42Z",
            "goals": {
              "away": 4,
              "home": 6
            }
          },
          "coordinates": {
            "x": 0,
            "y": 0
          },
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "triCode": "SJS"
          }
        }
      ],
      "scoringPlays": [
        0
      ],
      "penaltyPlays": [
        0
      ],
      "playsByPeriod": [
        {
          "startIndex": 0,
          "plays": [
            0
          ],
          "endIndex": 114
        }
      ],
      "currentPlay": {
        "players": [
          {
            "player": {
              "id": 8476881,
              "fullName": "Tomas Hertl",
              "link": "/api/v1/people/8476881"
            },
            "playerType": "Winner"
          }
        ],
        "result": {
          "event": "Game End",
          "eventCode": "SJS505",
          "eventTypeId": "GAME_END",
          "description": "Game End"
        },
        "about": {
          "eventIdx": 315,
          "eventId": 505,
          "period": 3,
          "periodType": "REGULAR",
          "ordinalNum": "3rd",
          "periodTime": "20:00",
          "periodTimeRemaining": "00:00",
          "dateTime": "2018-02-11T05:30:42Z",
          "goals": {
            "away": 4,
            "home": 6
          }
        },
        "coordinates": {
          "x": 0,
          "y": 0
        },
        "team": {
          "id": 28,
          "name": "San Jose Sharks",
          "link": "/api/v1/teams/28",
          "triCode": "SJS"
        }
      }
    },
    "linescore": {
      "currentPeriod": 3,
      "currentPeriodOrdinal": "3rd",
      "currentPeriodTimeRemaining": "Final",
      "periods": [
        {
          "periodType": "REGULAR",
          "startTime": "2018-02-11T03:09:50Z",
          "endTime": "2018-02-11T03:44:47Z",
          "num": 1,
          "ordinalNum": "1st",
          "home": {
            "goals": 2,
            "shotsOnGoal": 14,
            "rinkSide": "left"
          },
          "away": {
            "goals": 0,
            "shotsOnGoal": 9,
            "rinkSide": "right"
          }
        }
      ],
      "shootoutInfo": {
        "away": {
          "scores": 0,
          "attempts": 0
        },
        "home": {
          "scores": 0,
          "attempts": 0
        }
      },
      "teams": {
        "home": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "goals": 6,
          "shotsOnGoal": 30,
          "goaliePulled": true,
          "numSkaters": 5,
          "powerPlay": true
        },
        "away": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "goals": 6,
          "shotsOnGoal": 30,
          "goaliePulled": true,
          "numSkaters": 5,
          "powerPlay": true
        }
      },
      "powerPlayStrength": "Even",
      "hasShootout": true,
      "intermissionInfo": {
        "intermissionTimeRemaining": 0,
        "intermissionTimeElapsed": 0,
        "inIntermission": true
      },
      "powerPlayInfo": {
        "situationTimeRemaining": 0,
        "situationTimeElapsed": 72,
        "inSituation": true
      }
    },
    "boxscore": {
      "teams": {
        "away": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "teamStats": {
            "teamSkaterStats": {
              "goals": 6,
              "pim": 6,
              "shots": 30,
              "powerPlayPercentage": "0.0",
              "powerPlayGoals": 0,
              "powerPlayOpportunities": 1,
              "faceOffWinPercentage": "59.3",
              "blocked": 21,
              "takeaways": 9,
              "giveaways": 6,
              "hits": 15
            }
          },
          "players": {
            "person": {
              "id": 8471709,
              "fullName": "Marc-Edouard Vlasic",
              "link": "/api/v1/people/8471709",
              "shootsCatches": "L",
              "rosterStatus": "Y"
            },
            "jerseyNumber": "44",
            "position": {
              "code": "D",
              "name": "Defenseman",
              "type": "Defenseman",
              "abbreviation": "D"
            },
            "stats": {
              "skaterStats": {
                "timeOnIce": "23:04",
                "assists": 0,
                "goals": 0,
                "shots": 2,
                "hits": 0,
                "powerPlayGoals": 0,
                "powerPlayAssists": 0,
                "penaltyMinutes": 0,
                "faceOffWins": 0,
                "faceoffTaken": 0,
                "takeaways": 0,
                "giveaways": 1,
                "shortHandedGoals": 0,
                "shortHandedAssists": 0,
                "blocked": 0,
                "plusMinus": 1,
                "evenTimeOnIce": "18:12",
                "powerPlayTimeOnIce": "1:07",
                "shortHandedTimeOnIce": "3:45"
              }
            }
          },
          "goalies": [
            0
          ],
          "skaters": [
            0
          ],
          "onIce": [
            0
          ],
          "onIcePlus": [
            {
              "playerId": 8477180,
              "shiftDuration": 458,
              "stamina": 33
            }
          ],
          "scratches": [
            0
          ],
          "penaltyBox": [
            0
          ],
          "coaches": [
            {
              "person": {
                "fullName": "Peter DeBoer",
                "link": "/api/v1/people/null"
              },
              "position": {
                "code": "HC",
                "name": "Head Coach",
                "type": "Head Coach",
                "abbreviation": "Head Coach"
              }
            }
          ]
        },
        "home": {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28",
            "abbreviation": "SJS",
            "triCode": "SJS"
          },
          "teamStats": {
            "teamSkaterStats": {
              "goals": 6,
              "pim": 6,
              "shots": 30,
              "powerPlayPercentage": "0.0",
              "powerPlayGoals": 0,
              "powerPlayOpportunities": 1,
              "faceOffWinPercentage": "59.3",
              "blocked": 21,
              "takeaways": 9,
              "giveaways": 6,
              "hits": 15
            }
          },
          "players": {
            "person": {
              "id": 8471709,
              "fullName": "Marc-Edouard Vlasic",
              "link": "/api/v1/people/8471709",
              "shootsCatches": "L",
              "rosterStatus": "Y"
            },
            "jerseyNumber": "44",
            "position": {
              "code": "D",
              "name": "Defenseman",
              "type": "Defenseman",
              "abbreviation": "D"
            },
            "stats": {
              "skaterStats": {
                "timeOnIce": "23:04",
                "assists": 0,
                "goals": 0,
                "shots": 2,
                "hits": 0,
                "powerPlayGoals": 0,
                "powerPlayAssists": 0,
                "penaltyMinutes": 0,
                "faceOffWins": 0,
                "faceoffTaken": 0,
                "takeaways": 0,
                "giveaways": 1,
                "shortHandedGoals": 0,
                "shortHandedAssists": 0,
                "blocked": 0,
                "plusMinus": 1,
                "evenTimeOnIce": "18:12",
                "powerPlayTimeOnIce": "1:07",
                "shortHandedTimeOnIce": "3:45"
              }
            }
          },
          "goalies": [
            0
          ],
          "skaters": [
            0
          ],
          "onIce": [
            0
          ],
          "onIcePlus": [
            {
              "playerId": 8477180,
              "shiftDuration": 458,
              "stamina": 33
            }
          ],
          "scratches": [
            0
          ],
          "penaltyBox": [
            0
          ],
          "coaches": [
            {
              "person": {
                "fullName": "Peter DeBoer",
                "link": "/api/v1/people/null"
              },
              "position": {
                "code": "HC",
                "name": "Head Coach",
                "type": "Head Coach",
                "abbreviation": "Head Coach"
              }
            }
          ]
        }
      },
      "officials": [
        {
          "official": {
            "id": 2071,
            "fullName": "Tim Peel",
            "link": "/api/v1/people/2071"
          },
          "officialType": "Linesman"
        }
      ]
    },
    "decisions": {
      "winner": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "loser": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "firstStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "secondStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      },
      "thirdStar": {
        "id": 8477180,
        "fullName": "Aaron Dell",
        "link": "/api/v1/people/8477180"
      }
    }
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|gamePk|number|false|No description|
|link|string(uri)|false|No description|
|metaData|object|false|No description|
|» wait|number|false|No description|
|» timeStamp|string|false|No description|
|gameData|object|false|No description|
|» game|object|false|No description|
|»» pk|number|false|No description|
|»» season|string|false|No description|
|»» type|string|false|No description|
|» datetime|object|false|No description|
|»» dateTime|string(date-time)|false|No description|
|»» endDateTime|string(date-time)|false|No description|
|» status|object|false|No description|
|»» abstractGameState|string|false|No description|
|»» codedGameState|string|false|No description|
|»» detailedState|string|false|No description|
|»» statusCode|string|false|No description|
|»» startTimeTBD|boolean|false|No description|
|» teams|object|false|No description|
|»» away|[Team](#schemateam)|false|No description|
|»» home|[Team](#schemateam)|false|No description|
|» players|[Player](#schemaplayer)|false|No description|
|» venue|object|false|No description|
|»» name|string|false|No description|
|»» link|string(uri)|false|No description|
|» liveData|object|false|No description|
|»» plays|object|false|No description|
|»»» allPlays|[[GamePlay](#schemagameplay)]|false|No description|
|»»» scoringPlays|[number]|false|No description|
|»»» penaltyPlays|[number]|false|No description|
|»»» playsByPeriod|[object]|false|No description|
|»»»» startIndex|number|false|No description|
|»»»» plays|[number]|false|No description|
|»»»» endIndex|number|false|No description|
|»»» currentPlay|[GamePlay](#schemagameplay)|false|No description|
|»» linescore|[GameLinescore](#schemagamelinescore)|false|No description|
|»» boxscore|[GameBoxscore](#schemagameboxscore)|false|No description|
|»» decisions|object|false|No description|
|»»» winner|[GameDecisionPlayer](#schemagamedecisionplayer)|false|No description|
|»»» loser|[GameDecisionPlayer](#schemagamedecisionplayer)|false|No description|
|»»» firstStar|[GameDecisionPlayer](#schemagamedecisionplayer)|false|No description|
|»»» secondStar|[GameDecisionPlayer](#schemagamedecisionplayer)|false|No description|
|»»» thirdStar|[GameDecisionPlayer](#schemagamedecisionplayer)|false|No description|

<h2 id="tocSgameboxscore">GameBoxscore</h2>

<a id="schemagameboxscore"></a>

```json
{
  "teams": {
    "away": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "teamStats": {
        "teamSkaterStats": {
          "goals": 6,
          "pim": 6,
          "shots": 30,
          "powerPlayPercentage": "0.0",
          "powerPlayGoals": 0,
          "powerPlayOpportunities": 1,
          "faceOffWinPercentage": "59.3",
          "blocked": 21,
          "takeaways": 9,
          "giveaways": 6,
          "hits": 15
        }
      },
      "players": {
        "person": {
          "id": 8471709,
          "fullName": "Marc-Edouard Vlasic",
          "link": "/api/v1/people/8471709",
          "shootsCatches": "L",
          "rosterStatus": "Y"
        },
        "jerseyNumber": "44",
        "position": {
          "code": "D",
          "name": "Defenseman",
          "type": "Defenseman",
          "abbreviation": "D"
        },
        "stats": {
          "skaterStats": {
            "timeOnIce": "23:04",
            "assists": 0,
            "goals": 0,
            "shots": 2,
            "hits": 0,
            "powerPlayGoals": 0,
            "powerPlayAssists": 0,
            "penaltyMinutes": 0,
            "faceOffWins": 0,
            "faceoffTaken": 0,
            "takeaways": 0,
            "giveaways": 1,
            "shortHandedGoals": 0,
            "shortHandedAssists": 0,
            "blocked": 0,
            "plusMinus": 1,
            "evenTimeOnIce": "18:12",
            "powerPlayTimeOnIce": "1:07",
            "shortHandedTimeOnIce": "3:45"
          }
        }
      },
      "goalies": [
        0
      ],
      "skaters": [
        0
      ],
      "onIce": [
        0
      ],
      "onIcePlus": [
        {
          "playerId": 8477180,
          "shiftDuration": 458,
          "stamina": 33
        }
      ],
      "scratches": [
        0
      ],
      "penaltyBox": [
        0
      ],
      "coaches": [
        {
          "person": {
            "fullName": "Peter DeBoer",
            "link": "/api/v1/people/null"
          },
          "position": {
            "code": "HC",
            "name": "Head Coach",
            "type": "Head Coach",
            "abbreviation": "Head Coach"
          }
        }
      ]
    },
    "home": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "teamStats": {
        "teamSkaterStats": {
          "goals": 6,
          "pim": 6,
          "shots": 30,
          "powerPlayPercentage": "0.0",
          "powerPlayGoals": 0,
          "powerPlayOpportunities": 1,
          "faceOffWinPercentage": "59.3",
          "blocked": 21,
          "takeaways": 9,
          "giveaways": 6,
          "hits": 15
        }
      },
      "players": {
        "person": {
          "id": 8471709,
          "fullName": "Marc-Edouard Vlasic",
          "link": "/api/v1/people/8471709",
          "shootsCatches": "L",
          "rosterStatus": "Y"
        },
        "jerseyNumber": "44",
        "position": {
          "code": "D",
          "name": "Defenseman",
          "type": "Defenseman",
          "abbreviation": "D"
        },
        "stats": {
          "skaterStats": {
            "timeOnIce": "23:04",
            "assists": 0,
            "goals": 0,
            "shots": 2,
            "hits": 0,
            "powerPlayGoals": 0,
            "powerPlayAssists": 0,
            "penaltyMinutes": 0,
            "faceOffWins": 0,
            "faceoffTaken": 0,
            "takeaways": 0,
            "giveaways": 1,
            "shortHandedGoals": 0,
            "shortHandedAssists": 0,
            "blocked": 0,
            "plusMinus": 1,
            "evenTimeOnIce": "18:12",
            "powerPlayTimeOnIce": "1:07",
            "shortHandedTimeOnIce": "3:45"
          }
        }
      },
      "goalies": [
        0
      ],
      "skaters": [
        0
      ],
      "onIce": [
        0
      ],
      "onIcePlus": [
        {
          "playerId": 8477180,
          "shiftDuration": 458,
          "stamina": 33
        }
      ],
      "scratches": [
        0
      ],
      "penaltyBox": [
        0
      ],
      "coaches": [
        {
          "person": {
            "fullName": "Peter DeBoer",
            "link": "/api/v1/people/null"
          },
          "position": {
            "code": "HC",
            "name": "Head Coach",
            "type": "Head Coach",
            "abbreviation": "Head Coach"
          }
        }
      ]
    }
  },
  "officials": [
    {
      "official": {
        "id": 2071,
        "fullName": "Tim Peel",
        "link": "/api/v1/people/2071"
      },
      "officialType": "Linesman"
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|teams|object|false|No description|
|» away|[GameBoxscoreTeam](#schemagameboxscoreteam)|false|No description|
|» home|[GameBoxscoreTeam](#schemagameboxscoreteam)|false|No description|
|officials|[[GameOfficial](#schemagameofficial)]|false|No description|

<h2 id="tocSgameboxscores">GameBoxscores</h2>

<a id="schemagameboxscores"></a>

```json
{
  "copyright": "string",
  "teams": {
    "away": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "teamStats": {
        "teamSkaterStats": {
          "goals": 6,
          "pim": 6,
          "shots": 30,
          "powerPlayPercentage": "0.0",
          "powerPlayGoals": 0,
          "powerPlayOpportunities": 1,
          "faceOffWinPercentage": "59.3",
          "blocked": 21,
          "takeaways": 9,
          "giveaways": 6,
          "hits": 15
        }
      },
      "players": {
        "person": {
          "id": 8471709,
          "fullName": "Marc-Edouard Vlasic",
          "link": "/api/v1/people/8471709",
          "shootsCatches": "L",
          "rosterStatus": "Y"
        },
        "jerseyNumber": "44",
        "position": {
          "code": "D",
          "name": "Defenseman",
          "type": "Defenseman",
          "abbreviation": "D"
        },
        "stats": {
          "skaterStats": {
            "timeOnIce": "23:04",
            "assists": 0,
            "goals": 0,
            "shots": 2,
            "hits": 0,
            "powerPlayGoals": 0,
            "powerPlayAssists": 0,
            "penaltyMinutes": 0,
            "faceOffWins": 0,
            "faceoffTaken": 0,
            "takeaways": 0,
            "giveaways": 1,
            "shortHandedGoals": 0,
            "shortHandedAssists": 0,
            "blocked": 0,
            "plusMinus": 1,
            "evenTimeOnIce": "18:12",
            "powerPlayTimeOnIce": "1:07",
            "shortHandedTimeOnIce": "3:45"
          }
        }
      },
      "goalies": [
        0
      ],
      "skaters": [
        0
      ],
      "onIce": [
        0
      ],
      "onIcePlus": [
        {
          "playerId": 8477180,
          "shiftDuration": 458,
          "stamina": 33
        }
      ],
      "scratches": [
        0
      ],
      "penaltyBox": [
        0
      ],
      "coaches": [
        {
          "person": {
            "fullName": "Peter DeBoer",
            "link": "/api/v1/people/null"
          },
          "position": {
            "code": "HC",
            "name": "Head Coach",
            "type": "Head Coach",
            "abbreviation": "Head Coach"
          }
        }
      ]
    },
    "home": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "teamStats": {
        "teamSkaterStats": {
          "goals": 6,
          "pim": 6,
          "shots": 30,
          "powerPlayPercentage": "0.0",
          "powerPlayGoals": 0,
          "powerPlayOpportunities": 1,
          "faceOffWinPercentage": "59.3",
          "blocked": 21,
          "takeaways": 9,
          "giveaways": 6,
          "hits": 15
        }
      },
      "players": {
        "person": {
          "id": 8471709,
          "fullName": "Marc-Edouard Vlasic",
          "link": "/api/v1/people/8471709",
          "shootsCatches": "L",
          "rosterStatus": "Y"
        },
        "jerseyNumber": "44",
        "position": {
          "code": "D",
          "name": "Defenseman",
          "type": "Defenseman",
          "abbreviation": "D"
        },
        "stats": {
          "skaterStats": {
            "timeOnIce": "23:04",
            "assists": 0,
            "goals": 0,
            "shots": 2,
            "hits": 0,
            "powerPlayGoals": 0,
            "powerPlayAssists": 0,
            "penaltyMinutes": 0,
            "faceOffWins": 0,
            "faceoffTaken": 0,
            "takeaways": 0,
            "giveaways": 1,
            "shortHandedGoals": 0,
            "shortHandedAssists": 0,
            "blocked": 0,
            "plusMinus": 1,
            "evenTimeOnIce": "18:12",
            "powerPlayTimeOnIce": "1:07",
            "shortHandedTimeOnIce": "3:45"
          }
        }
      },
      "goalies": [
        0
      ],
      "skaters": [
        0
      ],
      "onIce": [
        0
      ],
      "onIcePlus": [
        {
          "playerId": 8477180,
          "shiftDuration": 458,
          "stamina": 33
        }
      ],
      "scratches": [
        0
      ],
      "penaltyBox": [
        0
      ],
      "coaches": [
        {
          "person": {
            "fullName": "Peter DeBoer",
            "link": "/api/v1/people/null"
          },
          "position": {
            "code": "HC",
            "name": "Head Coach",
            "type": "Head Coach",
            "abbreviation": "Head Coach"
          }
        }
      ]
    }
  },
  "officials": [
    {
      "official": {
        "id": 2071,
        "fullName": "Tim Peel",
        "link": "/api/v1/people/2071"
      },
      "officialType": "Linesman"
    }
  ]
}
```

### Properties

*allOf*

|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|object|false|No description|
|» copyright|string|false|No description|

*and*

|Name|Type|Required|Description|
|---|---|---|---|
|*anonymous*|[GameBoxscore](#schemagameboxscore)|false|No description|

<h2 id="tocSgameboxscoreteam">GameBoxscoreTeam</h2>

<a id="schemagameboxscoreteam"></a>

```json
{
  "team": {
    "id": 28,
    "name": "San Jose Sharks",
    "link": "/api/v1/teams/28",
    "abbreviation": "SJS",
    "triCode": "SJS"
  },
  "teamStats": {
    "teamSkaterStats": {
      "goals": 6,
      "pim": 6,
      "shots": 30,
      "powerPlayPercentage": "0.0",
      "powerPlayGoals": 0,
      "powerPlayOpportunities": 1,
      "faceOffWinPercentage": "59.3",
      "blocked": 21,
      "takeaways": 9,
      "giveaways": 6,
      "hits": 15
    }
  },
  "players": {
    "person": {
      "id": 8471709,
      "fullName": "Marc-Edouard Vlasic",
      "link": "/api/v1/people/8471709",
      "shootsCatches": "L",
      "rosterStatus": "Y"
    },
    "jerseyNumber": "44",
    "position": {
      "code": "D",
      "name": "Defenseman",
      "type": "Defenseman",
      "abbreviation": "D"
    },
    "stats": {
      "skaterStats": {
        "timeOnIce": "23:04",
        "assists": 0,
        "goals": 0,
        "shots": 2,
        "hits": 0,
        "powerPlayGoals": 0,
        "powerPlayAssists": 0,
        "penaltyMinutes": 0,
        "faceOffWins": 0,
        "faceoffTaken": 0,
        "takeaways": 0,
        "giveaways": 1,
        "shortHandedGoals": 0,
        "shortHandedAssists": 0,
        "blocked": 0,
        "plusMinus": 1,
        "evenTimeOnIce": "18:12",
        "powerPlayTimeOnIce": "1:07",
        "shortHandedTimeOnIce": "3:45"
      }
    }
  },
  "goalies": [
    0
  ],
  "skaters": [
    0
  ],
  "onIce": [
    0
  ],
  "onIcePlus": [
    {
      "playerId": 8477180,
      "shiftDuration": 458,
      "stamina": 33
    }
  ],
  "scratches": [
    0
  ],
  "penaltyBox": [
    0
  ],
  "coaches": [
    {
      "person": {
        "fullName": "Peter DeBoer",
        "link": "/api/v1/people/null"
      },
      "position": {
        "code": "HC",
        "name": "Head Coach",
        "type": "Head Coach",
        "abbreviation": "Head Coach"
      }
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|team|object|false|No description|
|» id|number|false|No description|
|» name|string|false|No description|
|» link|string(uri)|false|No description|
|» abbreviation|string|false|No description|
|» triCode|string|false|No description|
|teamStats|object|false|No description|
|» teamSkaterStats|object|false|No description|
|»» goals|number|false|No description|
|»» pim|number|false|No description|
|»» shots|number|false|No description|
|»» powerPlayPercentage|string|false|No description|
|»» powerPlayGoals|number|false|No description|
|»» powerPlayOpportunities|number|false|No description|
|»» faceOffWinPercentage|string|false|No description|
|»» blocked|number|false|No description|
|»» takeaways|number|false|No description|
|»» giveaways|number|false|No description|
|»» hits|number|false|No description|
|» players|object|false|No description|
|»» person|object|false|No description|
|»»» id|number|false|No description|
|»»» fullName|string|false|No description|
|»»» link|string(uri)|false|No description|
|»»» shootsCatches|string|false|No description|
|»»» rosterStatus|string|false|No description|
|»» jerseyNumber|string|false|No description|
|»» position|object|false|No description|
|»»» code|string|false|No description|
|»»» name|string|false|No description|
|»»» type|string|false|No description|
|»»» abbreviation|string|false|No description|
|»» stats|object|false|No description|
|»»» skaterStats|object|false|No description|
|»»»» timeOnIce|string|false|No description|
|»»»» assists|number|false|No description|
|»»»» goals|number|false|No description|
|»»»» shots|number|false|No description|
|»»»» hits|number|false|No description|
|»»»» powerPlayGoals|number|false|No description|
|»»»» powerPlayAssists|number|false|No description|
|»»»» penaltyMinutes|number|false|No description|
|»»»» faceOffWins|number|false|No description|
|»»»» faceoffTaken|number|false|No description|
|»»»» takeaways|number|false|No description|
|»»»» giveaways|number|false|No description|
|»»»» shortHandedGoals|number|false|No description|
|»»»» shortHandedAssists|number|false|No description|
|»»»» blocked|number|false|No description|
|»»»» plusMinus|number|false|No description|
|»»»» evenTimeOnIce|string|false|No description|
|»»»» powerPlayTimeOnIce|string|false|No description|
|»»»» shortHandedTimeOnIce|string|false|No description|
|»»» goalies|[number]|false|No description|
|»»» skaters|[number]|false|No description|
|»»» onIce|[number]|false|No description|
|»»» onIcePlus|[object]|false|No description|
|»»»» playerId|number|false|No description|
|»»»» shiftDuration|number|false|No description|
|»»»» stamina|number|false|No description|
|»»» scratches|[number]|false|No description|
|»»» penaltyBox|[number]|false|No description|
|»»» coaches|[object]|false|No description|
|»»»» person|object|false|No description|
|»»»»» fullName|string|false|No description|
|»»»»» link|string(uri)|false|No description|
|»»»» position|object|false|No description|
|»»»»» code|string|false|No description|
|»»»»» name|string|false|No description|
|»»»»» type|string|false|No description|
|»»»»» abbreviation|string|false|No description|

<h2 id="tocSgamecontent">GameContent</h2>

<a id="schemagamecontent"></a>

```json
{
  "copyright": "string",
  "link": "/api/v1/game/2017020851/content",
  "editorial": {
    "preview": {
      "title": "Preview",
      "topicList": "string",
      "items": [
        {
          "type": "article",
          "state": "A",
          "date": "2018-02-10T16:57:06-0500",
          "id": "295823824",
          "headline": "Oilers at Sharks preview",
          "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
          "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
          "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
          "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
          "slug": "edmonton-oilers-san-jose-sharks-game-preview",
          "commenting": true,
          "tagline": "string",
          "tokenData": {
            "tokenGUID": "token-EBDA2F0039BF4445D2C91",
            "type": "hyperLink",
            "id": "8471709",
            "teamId": "28",
            "name": "Marc-Edouard Vlasic",
            "seoName": "marc-edouard-vlasic",
            "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
            "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
          },
          "contributor": {
            "contributors": [
              {
                "name": "Eric Gilmore",
                "twitter": "string"
              }
            ],
            "source": "NHL.com Correspondent"
          },
          "keywordsDisplay": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "keywordsAll": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "approval": "string",
          "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
          "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
          "primaryKeyword": {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          },
          "media": {
            "type": "photo",
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            }
          },
          "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
        }
      ]
    },
    "articles": {
      "title": "Preview",
      "topicList": "string",
      "items": [
        {
          "type": "article",
          "state": "A",
          "date": "2018-02-10T16:57:06-0500",
          "id": "295823824",
          "headline": "Oilers at Sharks preview",
          "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
          "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
          "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
          "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
          "slug": "edmonton-oilers-san-jose-sharks-game-preview",
          "commenting": true,
          "tagline": "string",
          "tokenData": {
            "tokenGUID": "token-EBDA2F0039BF4445D2C91",
            "type": "hyperLink",
            "id": "8471709",
            "teamId": "28",
            "name": "Marc-Edouard Vlasic",
            "seoName": "marc-edouard-vlasic",
            "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
            "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
          },
          "contributor": {
            "contributors": [
              {
                "name": "Eric Gilmore",
                "twitter": "string"
              }
            ],
            "source": "NHL.com Correspondent"
          },
          "keywordsDisplay": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "keywordsAll": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "approval": "string",
          "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
          "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
          "primaryKeyword": {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          },
          "media": {
            "type": "photo",
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            }
          },
          "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
        }
      ]
    },
    "recap": {
      "title": "Preview",
      "topicList": "string",
      "items": [
        {
          "type": "article",
          "state": "A",
          "date": "2018-02-10T16:57:06-0500",
          "id": "295823824",
          "headline": "Oilers at Sharks preview",
          "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
          "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
          "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
          "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
          "slug": "edmonton-oilers-san-jose-sharks-game-preview",
          "commenting": true,
          "tagline": "string",
          "tokenData": {
            "tokenGUID": "token-EBDA2F0039BF4445D2C91",
            "type": "hyperLink",
            "id": "8471709",
            "teamId": "28",
            "name": "Marc-Edouard Vlasic",
            "seoName": "marc-edouard-vlasic",
            "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
            "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
          },
          "contributor": {
            "contributors": [
              {
                "name": "Eric Gilmore",
                "twitter": "string"
              }
            ],
            "source": "NHL.com Correspondent"
          },
          "keywordsDisplay": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "keywordsAll": [
            {
              "type": "bodyParagraphCount",
              "value": "en",
              "displayName": "English"
            }
          ],
          "approval": "string",
          "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
          "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
          "primaryKeyword": {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          },
          "media": {
            "type": "photo",
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            }
          },
          "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
        }
      ]
    }
  },
  "media": {
    "epg": [
      {
        "title": "NHLTV",
        "platform": "web",
        "items": [
          {
            "guid": "dbb39fa8-6679-4b22-a8c5-71eb5e39b462",
            "mediaState": "MEDIA_ARCHIVE",
            "mediaPlaybackId": "57463703",
            "mediaFeedType": "HOME",
            "callLetters": "NBCS-CA",
            "eventId": "221-1007449",
            "language": "eng",
            "freeGame": true,
            "feedName": "string",
            "gamePlus": true
          }
        ]
      }
    ],
    "milestones": {
      "title": "Milestones",
      "streamStart": "2018-02-11T03:04:32+0000",
      "items": [
        {
          "title": "Broadcast Start",
          "description": "Broadcast Start",
          "type": "BROADCAST_START",
          "timeAbsolute": "2018-02-11T03:04:36+0000",
          "timeOffset": "4",
          "period": "1",
          "statsEventId": "10",
          "teamId": "28",
          "playerId": "8477046",
          "periodTime": "01:15",
          "ordinalNum": "1st",
          "highlight": {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        }
      ]
    }
  },
  "highlights": {
    "scoreboard": {
      "scoreboard": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      },
      "gameCenter": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      }
    },
    "gameCenter": {
      "scoreboard": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      },
      "gameCenter": {
        "title": "Highlights",
        "topicList": "293642378",
        "items": [
          {
            "type": "video",
            "id": "57602103",
            "date": "2018-02-10T22:00:00-0500",
            "title": "Goodrow buries Hansen's pass",
            "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
            "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
            "duration": "00:51",
            "authFlow": true,
            "mediaPlaybackId": "57602103",
            "mediaState": "MEDIA_ARCHIVE",
            "keywords": [
              {
                "type": "bodyParagraphCount",
                "value": "en",
                "displayName": "English"
              }
            ],
            "image": {
              "title": "string",
              "altText": "string",
              "cuts": {
                "aspectRatio": "16:9",
                "width": 2568,
                "height": 1444,
                "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
                "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
              }
            },
            "playbacks": [
              {
                "name": "FLASH_192K_320X180",
                "width": "960",
                "height": "540",
                "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
              }
            ]
          }
        ]
      }
    }
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|link|string(uri)|false|No description|
|editorial|object|false|No description|
|» preview|[GameEditorials](#schemagameeditorials)|false|No description|
|» articles|[GameEditorials](#schemagameeditorials)|false|No description|
|» recap|[GameEditorials](#schemagameeditorials)|false|No description|
|media|object|false|No description|
|» epg|[anyOf]|false|No description|

*anyOf*

|Name|Type|Required|Description|
|---|---|---|---|
|»» *anonymous*|[GameMediaNHLTV](#schemagamemedianhltv)|false|No description|

*or*

|Name|Type|Required|Description|
|---|---|---|---|
|»» *anonymous*|[GameMediaAudio](#schemagamemediaaudio)|false|No description|

*or*

|Name|Type|Required|Description|
|---|---|---|---|
|»» *anonymous*|[GameHighlightType](#schemagamehighlighttype)|false|No description|

*continued*

|Name|Type|Required|Description|
|---|---|---|---|
|» milestones|object|false|No description|
|»» title|string|false|No description|
|»» streamStart|string(date-time)|false|No description|
|»» items|[object]|false|No description|
|»»» title|string|false|No description|
|»»» description|string|false|No description|
|»»» type|string|false|No description|
|»»» timeAbsolute|string(date-time)|false|No description|
|»»» timeOffset|string|false|No description|
|»»» period|string|false|No description|
|»»» statsEventId|string|false|No description|
|»»» teamId|string|false|No description|
|»»» playerId|string|false|No description|
|»»» periodTime|string|false|No description|
|»»» ordinalNum|string|false|No description|
|»»» highlight|[GameHighlight](#schemagamehighlight)|false|No description|
|»» highlights|object|false|No description|
|»»» scoreboard|[GameHighlights](#schemagamehighlights)|false|No description|
|»»» gameCenter|[GameHighlights](#schemagamehighlights)|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|title|Milestones|
|type|BROADCAST_START|
|type|BROADCAST_END|
|type|GOAL|
|type|PERIOD_END|
|type|PERIOD_START|
|type|SHOT|

<h2 id="tocSgameeditorial">GameEditorial</h2>

<a id="schemagameeditorial"></a>

```json
{
  "type": "article",
  "state": "A",
  "date": "2018-02-10T16:57:06-0500",
  "id": "295823824",
  "headline": "Oilers at Sharks preview",
  "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
  "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
  "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
  "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
  "slug": "edmonton-oilers-san-jose-sharks-game-preview",
  "commenting": true,
  "tagline": "string",
  "tokenData": {
    "tokenGUID": "token-EBDA2F0039BF4445D2C91",
    "type": "hyperLink",
    "id": "8471709",
    "teamId": "28",
    "name": "Marc-Edouard Vlasic",
    "seoName": "marc-edouard-vlasic",
    "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
    "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
  },
  "contributor": {
    "contributors": [
      {
        "name": "Eric Gilmore",
        "twitter": "string"
      }
    ],
    "source": "NHL.com Correspondent"
  },
  "keywordsDisplay": [
    {
      "type": "bodyParagraphCount",
      "value": "en",
      "displayName": "English"
    }
  ],
  "keywordsAll": [
    {
      "type": "bodyParagraphCount",
      "value": "en",
      "displayName": "English"
    }
  ],
  "approval": "string",
  "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
  "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
  "primaryKeyword": {
    "type": "bodyParagraphCount",
    "value": "en",
    "displayName": "English"
  },
  "media": {
    "type": "photo",
    "image": {
      "title": "string",
      "altText": "string",
      "cuts": {
        "aspectRatio": "16:9",
        "width": 2568,
        "height": 1444,
        "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
        "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
        "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
      }
    }
  },
  "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|type|string|false|No description|
|state|string|false|No description|
|date|string(date-time)|false|No description|
|id|string|false|No description|
|headline|string|false|No description|
|subhead|string|false|No description|
|seoTitle|string|false|No description|
|seoDescription|string|false|No description|
|seoKeywords|string|false|No description|
|slug|string|false|No description|
|commenting|boolean|false|No description|
|tagline|string|false|No description|
|tokenData|object|false|No description|
|» tokenGUID|string|false|No description|
|» type|string|false|No description|
|» id|string|false|No description|
|» teamId|string|false|No description|
|» name|string|false|No description|
|» seoName|string|false|No description|
|» href|string|false|No description|
|» hrefMobile|string|false|No description|
|contributor|object|false|No description|
|» contributors|[object]|false|No description|
|»» name|string|false|No description|
|»» twitter|string|false|No description|
|» source|string|false|No description|
|keywordsDisplay|[[GameEditorialKeyword](#schemagameeditorialkeyword)]|false|No description|
|keywordsAll|[[GameEditorialKeyword](#schemagameeditorialkeyword)]|false|No description|
|approval|string|false|No description|
|url|string|false|No description|
|dataURI|string|false|No description|
|primaryKeyword|[GameEditorialKeyword](#schemagameeditorialkeyword)|false|No description|
|media|object|false|No description|
|» type|string|false|No description|
|» image|[Photo](#schemaphoto)|false|No description|
|preview|string(html)|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|type|hyperLink|
|type|playerCard|

<h2 id="tocSgameeditorialkeyword">GameEditorialKeyword</h2>

<a id="schemagameeditorialkeyword"></a>

```json
{
  "type": "bodyParagraphCount",
  "value": "en",
  "displayName": "English"
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|type|string|false|No description|
|value|string|false|No description|
|displayName|string|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|type|bodyParagraphCount|
|type|bodyWordCount|
|type|clob_autoTagSkip_playerCards|
|type|content|
|type|embeddable|
|type|gameId|
|type|language|
|type|playerId|
|type|previewParagraphCount|
|type|primaryTag|
|type|previewWordCount|
|type|shareable|
|type|statsEventId|
|type|teamFileCode|
|type|teamId|

<h2 id="tocSgameeditorials">GameEditorials</h2>

<a id="schemagameeditorials"></a>

```json
{
  "title": "Preview",
  "topicList": "string",
  "items": [
    {
      "type": "article",
      "state": "A",
      "date": "2018-02-10T16:57:06-0500",
      "id": "295823824",
      "headline": "Oilers at Sharks preview",
      "subhead": "Backups Montoya, Dell to start for Edmonton, San Jose",
      "seoTitle": "Edmonton Oilers San Jose Sharks game preview",
      "seoDescription": "Backup goaltender Aaron Dell will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.",
      "seoKeywords": "Game preview, Edmonton Oilers, San Jose Sharks, Aaron Dell, Al Montoya, Feb 10",
      "slug": "edmonton-oilers-san-jose-sharks-game-preview",
      "commenting": true,
      "tagline": "string",
      "tokenData": {
        "tokenGUID": "token-EBDA2F0039BF4445D2C91",
        "type": "hyperLink",
        "id": "8471709",
        "teamId": "28",
        "name": "Marc-Edouard Vlasic",
        "seoName": "marc-edouard-vlasic",
        "href": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018",
        "hrefMobile": "https://www.nhl.com/player/keegan-lowe-8476397?season=20172018"
      },
      "contributor": {
        "contributors": [
          {
            "name": "Eric Gilmore",
            "twitter": "string"
          }
        ],
        "source": "NHL.com Correspondent"
      },
      "keywordsDisplay": [
        {
          "type": "bodyParagraphCount",
          "value": "en",
          "displayName": "English"
        }
      ],
      "keywordsAll": [
        {
          "type": "bodyParagraphCount",
          "value": "en",
          "displayName": "English"
        }
      ],
      "approval": "string",
      "url": "/news/edmonton-oilers-san-jose-sharks-game-preview/c-295823824?game_pk=2017020851",
      "dataURI": "/nhl/id/v1/295823824/details/web-v1.json",
      "primaryKeyword": {
        "type": "bodyParagraphCount",
        "value": "en",
        "displayName": "English"
      },
      "media": {
        "type": "photo",
        "image": {
          "title": "string",
          "altText": "string",
          "cuts": {
            "aspectRatio": "16:9",
            "width": 2568,
            "height": 1444,
            "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
            "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
            "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
          }
        }
      },
      "preview": "<p><b>OILERS (23-26-4) at SHARKS (28-18-8)</b></p><p><b>10 p.m. ET; NBCSCA, CITY, SN360, SN, NHL.TV</b></p><p>&nbsp;</p><h5><b>The Game</b></h5><p>Backup goaltender <span class=\"token token-playerCard\" id=\"token-B36CCB71E81996298E792\">Aaron Dell</span> will make his 19th start of the season when the San Jose Sharks play the Edmonton Oilers at SAP Center on Saturday in the first of back-to-back games.</p>"
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|title|string|false|No description|
|topicList|string|false|No description|
|items|[[GameEditorial](#schemagameeditorial)]|false|No description|

<h2 id="tocSgamehighlight">GameHighlight</h2>

<a id="schemagamehighlight"></a>

```json
{
  "type": "video",
  "id": "57602103",
  "date": "2018-02-10T22:00:00-0500",
  "title": "Goodrow buries Hansen's pass",
  "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
  "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
  "duration": "00:51",
  "authFlow": true,
  "mediaPlaybackId": "57602103",
  "mediaState": "MEDIA_ARCHIVE",
  "keywords": [
    {
      "type": "bodyParagraphCount",
      "value": "en",
      "displayName": "English"
    }
  ],
  "image": {
    "title": "string",
    "altText": "string",
    "cuts": {
      "aspectRatio": "16:9",
      "width": 2568,
      "height": 1444,
      "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
      "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
      "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
    }
  },
  "playbacks": [
    {
      "name": "FLASH_192K_320X180",
      "width": "960",
      "height": "540",
      "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|type|string|false|No description|
|id|string|false|No description|
|date|string(date-time)|false|No description|
|title|string|false|No description|
|blurb|string|false|No description|
|description|string|false|No description|
|duration|string|false|No description|
|authFlow|boolean|false|No description|
|mediaPlaybackId|string|false|No description|
|mediaState|string|false|No description|
|keywords|[[GameEditorialKeyword](#schemagameeditorialkeyword)]|false|No description|
|image|[Photo](#schemaphoto)|false|No description|
|playbacks|[object]|false|No description|
|» name|string|false|No description|
|» width|string|false|No description|
|» height|string|false|No description|
|» url|string(video)|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|type|video|
|name|FLASH_192K_320X180|
|name|FLASH_450K_400X224|
|name|FLASH_1200K_640X360|
|name|FLASH_1800K_960X540|
|name|HTTP_CLOUD_MOBILE|
|name|HTTP_CLOUD_TABLET|
|name|HTTP_CLOUD_TABLET_60|
|name|HTTP_CLOUD_WIRED|
|name|HTTP_CLOUD_WIRED_60|
|name|HTTP_CLOUD_WIRED_WEB|

<h2 id="tocSgamehighlights">GameHighlights</h2>

<a id="schemagamehighlights"></a>

```json
{
  "scoreboard": {
    "title": "Highlights",
    "topicList": "293642378",
    "items": [
      {
        "type": "video",
        "id": "57602103",
        "date": "2018-02-10T22:00:00-0500",
        "title": "Goodrow buries Hansen's pass",
        "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
        "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
        "duration": "00:51",
        "authFlow": true,
        "mediaPlaybackId": "57602103",
        "mediaState": "MEDIA_ARCHIVE",
        "keywords": [
          {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          }
        ],
        "image": {
          "title": "string",
          "altText": "string",
          "cuts": {
            "aspectRatio": "16:9",
            "width": 2568,
            "height": 1444,
            "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
            "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
            "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
          }
        },
        "playbacks": [
          {
            "name": "FLASH_192K_320X180",
            "width": "960",
            "height": "540",
            "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
          }
        ]
      }
    ]
  },
  "gameCenter": {
    "title": "Highlights",
    "topicList": "293642378",
    "items": [
      {
        "type": "video",
        "id": "57602103",
        "date": "2018-02-10T22:00:00-0500",
        "title": "Goodrow buries Hansen's pass",
        "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
        "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
        "duration": "00:51",
        "authFlow": true,
        "mediaPlaybackId": "57602103",
        "mediaState": "MEDIA_ARCHIVE",
        "keywords": [
          {
            "type": "bodyParagraphCount",
            "value": "en",
            "displayName": "English"
          }
        ],
        "image": {
          "title": "string",
          "altText": "string",
          "cuts": {
            "aspectRatio": "16:9",
            "width": 2568,
            "height": 1444,
            "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
            "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
            "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
          }
        },
        "playbacks": [
          {
            "name": "FLASH_192K_320X180",
            "width": "960",
            "height": "540",
            "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
          }
        ]
      }
    ]
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|scoreboard|[GameHighlightType](#schemagamehighlighttype)|false|No description|
|gameCenter|[GameHighlightType](#schemagamehighlighttype)|false|No description|

<h2 id="tocSgamehighlighttype">GameHighlightType</h2>

<a id="schemagamehighlighttype"></a>

```json
{
  "title": "Highlights",
  "topicList": "293642378",
  "items": [
    {
      "type": "video",
      "id": "57602103",
      "date": "2018-02-10T22:00:00-0500",
      "title": "Goodrow buries Hansen's pass",
      "blurb": "EDM@SJS: Goodrow snaps Hansen's pass by Montoya",
      "description": "Barclay Goodrow takes a drop pass from Jannik Hansen and whips a quick wrist shot past Al Montoya to give the Sharks a 3-0 lead in the 2nd",
      "duration": "00:51",
      "authFlow": true,
      "mediaPlaybackId": "57602103",
      "mediaState": "MEDIA_ARCHIVE",
      "keywords": [
        {
          "type": "bodyParagraphCount",
          "value": "en",
          "displayName": "English"
        }
      ],
      "image": {
        "title": "string",
        "altText": "string",
        "cuts": {
          "aspectRatio": "16:9",
          "width": 2568,
          "height": 1444,
          "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
          "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
          "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
        }
      },
      "playbacks": [
        {
          "name": "FLASH_192K_320X180",
          "width": "960",
          "height": "540",
          "url": "http://md-akc.med.nhl.com/mp4/nhl/2018/02/11/ddec1fcc-3772-4769-a547-314de76c6c11/1518322152840/asset_1800k.mp4"
        }
      ]
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|title|string|false|No description|
|topicList|string|false|No description|
|items|[[GameHighlight](#schemagamehighlight)]|false|No description|

<h2 id="tocSgameperiod">GamePeriod</h2>

<a id="schemagameperiod"></a>

```json
{
  "periodType": "REGULAR",
  "startTime": "2018-02-11T03:09:50Z",
  "endTime": "2018-02-11T03:44:47Z",
  "num": 1,
  "ordinalNum": "1st",
  "home": {
    "goals": 2,
    "shotsOnGoal": 14,
    "rinkSide": "left"
  },
  "away": {
    "goals": 0,
    "shotsOnGoal": 9,
    "rinkSide": "right"
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|periodType|string|false|No description|
|startTime|string(date-time)|false|No description|
|endTime|string(date-time)|false|No description|
|num|number|false|No description|
|ordinalNum|string|false|No description|
|home|object|false|No description|
|» goals|number|false|No description|
|» shotsOnGoal|number|false|No description|
|» rinkSide|string|false|No description|
|away|object|false|No description|
|» goals|number|false|No description|
|» shotsOnGoal|number|false|No description|
|» rinkSide|string|false|No description|

<h2 id="tocSgamedecisionplayer">GameDecisionPlayer</h2>

<a id="schemagamedecisionplayer"></a>

```json
{
  "id": 8477180,
  "fullName": "Aaron Dell",
  "link": "/api/v1/people/8477180"
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|id|number|false|No description|
|fullName|string|false|No description|
|link|string(uri)|false|No description|

<h2 id="tocSgamelinescore">GameLinescore</h2>

<a id="schemagamelinescore"></a>

```json
{
  "currentPeriod": 3,
  "currentPeriodOrdinal": "3rd",
  "currentPeriodTimeRemaining": "Final",
  "periods": [
    {
      "periodType": "REGULAR",
      "startTime": "2018-02-11T03:09:50Z",
      "endTime": "2018-02-11T03:44:47Z",
      "num": 1,
      "ordinalNum": "1st",
      "home": {
        "goals": 2,
        "shotsOnGoal": 14,
        "rinkSide": "left"
      },
      "away": {
        "goals": 0,
        "shotsOnGoal": 9,
        "rinkSide": "right"
      }
    }
  ],
  "shootoutInfo": {
    "away": {
      "scores": 0,
      "attempts": 0
    },
    "home": {
      "scores": 0,
      "attempts": 0
    }
  },
  "teams": {
    "home": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "goals": 6,
      "shotsOnGoal": 30,
      "goaliePulled": true,
      "numSkaters": 5,
      "powerPlay": true
    },
    "away": {
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28",
        "abbreviation": "SJS",
        "triCode": "SJS"
      },
      "goals": 6,
      "shotsOnGoal": 30,
      "goaliePulled": true,
      "numSkaters": 5,
      "powerPlay": true
    }
  },
  "powerPlayStrength": "Even",
  "hasShootout": true,
  "intermissionInfo": {
    "intermissionTimeRemaining": 0,
    "intermissionTimeElapsed": 0,
    "inIntermission": true
  },
  "powerPlayInfo": {
    "situationTimeRemaining": 0,
    "situationTimeElapsed": 72,
    "inSituation": true
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|currentPeriod|number|false|No description|
|currentPeriodOrdinal|string|false|No description|
|currentPeriodTimeRemaining|string|false|No description|
|periods|[[GamePeriod](#schemagameperiod)]|false|No description|
|shootoutInfo|object|false|No description|
|» away|object|false|No description|
|»» scores|number|false|No description|
|»» attempts|number|false|No description|
|» home|object|false|No description|
|»» scores|number|false|No description|
|»» attempts|number|false|No description|
|» teams|object|false|No description|
|»» home|[GameLinescoreTeam](#schemagamelinescoreteam)|false|No description|
|»» away|[GameLinescoreTeam](#schemagamelinescoreteam)|false|No description|
|» powerPlayStrength|string|false|No description|
|» hasShootout|boolean|false|No description|
|» intermissionInfo|object|false|No description|
|»» intermissionTimeRemaining|number|false|No description|
|»» intermissionTimeElapsed|number|false|No description|
|»» inIntermission|boolean|false|No description|
|» powerPlayInfo|object|false|No description|
|»» situationTimeRemaining|number|false|No description|
|»» situationTimeElapsed|number|false|No description|
|»» inSituation|boolean|false|No description|

<h2 id="tocSgamelinescoreteam">GameLinescoreTeam</h2>

<a id="schemagamelinescoreteam"></a>

```json
{
  "team": {
    "id": 28,
    "name": "San Jose Sharks",
    "link": "/api/v1/teams/28",
    "abbreviation": "SJS",
    "triCode": "SJS"
  },
  "goals": 6,
  "shotsOnGoal": 30,
  "goaliePulled": true,
  "numSkaters": 5,
  "powerPlay": true
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|team|object|false|No description|
|» id|number|false|No description|
|» name|string|false|No description|
|» link|string(uri)|false|No description|
|» abbreviation|string|false|No description|
|» triCode|string|false|No description|
|goals|number|false|No description|
|shotsOnGoal|number|false|No description|
|goaliePulled|boolean|false|No description|
|numSkaters|number|false|No description|
|powerPlay|boolean|false|No description|

<h2 id="tocSgamemediaaudio">GameMediaAudio</h2>

<a id="schemagamemediaaudio"></a>

```json
{
  "title": "Audio",
  "items": [
    {
      "mediaState": "MEDIA_DONE",
      "mediaPlaybackId": "57463903",
      "mediaFeedType": "HOME",
      "callLetters": "KFOX",
      "eventId": "221-1007449",
      "language": "eng",
      "freeGame": true,
      "feedName": "string",
      "gamePlus": true
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|title|string|false|No description|
|items|[object]|false|No description|
|» mediaState|string|false|No description|
|» mediaPlaybackId|string|false|No description|
|» mediaFeedType|string|false|No description|
|» callLetters|string|false|No description|
|» eventId|string|false|No description|
|» language|string|false|No description|
|» freeGame|boolean|false|No description|
|» feedName|string|false|No description|
|» gamePlus|boolean|false|No description|

<h2 id="tocSgamemedianhltv">GameMediaNHLTV</h2>

<a id="schemagamemedianhltv"></a>

```json
{
  "title": "NHLTV",
  "platform": "web",
  "items": [
    {
      "guid": "dbb39fa8-6679-4b22-a8c5-71eb5e39b462",
      "mediaState": "MEDIA_ARCHIVE",
      "mediaPlaybackId": "57463703",
      "mediaFeedType": "HOME",
      "callLetters": "NBCS-CA",
      "eventId": "221-1007449",
      "language": "eng",
      "freeGame": true,
      "feedName": "string",
      "gamePlus": true
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|title|string|false|No description|
|platform|string|false|No description|
|items|[object]|false|No description|
|» guid|string|false|No description|
|» mediaState|string|false|No description|
|» mediaPlaybackId|string|false|No description|
|» mediaFeedType|string|false|No description|
|» callLetters|string|false|No description|
|» eventId|string|false|No description|
|» language|string|false|No description|
|» freeGame|boolean|false|No description|
|» feedName|string|false|No description|
|» gamePlus|boolean|false|No description|

<h2 id="tocSgameofficial">GameOfficial</h2>

<a id="schemagameofficial"></a>

```json
{
  "official": {
    "id": 2071,
    "fullName": "Tim Peel",
    "link": "/api/v1/people/2071"
  },
  "officialType": "Linesman"
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|official|object|false|No description|
|» id|number|false|No description|
|» fullName|string|false|No description|
|» link|string(uri)|false|No description|
|officialType|string|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|officialType|Linesman|
|officialType|Referee|

<h2 id="tocSgameplay">GamePlay</h2>

<a id="schemagameplay"></a>

```json
{
  "players": [
    {
      "player": {
        "id": 8476881,
        "fullName": "Tomas Hertl",
        "link": "/api/v1/people/8476881"
      },
      "playerType": "Winner"
    }
  ],
  "result": {
    "event": "Game End",
    "eventCode": "SJS505",
    "eventTypeId": "GAME_END",
    "description": "Game End"
  },
  "about": {
    "eventIdx": 315,
    "eventId": 505,
    "period": 3,
    "periodType": "REGULAR",
    "ordinalNum": "3rd",
    "periodTime": "20:00",
    "periodTimeRemaining": "00:00",
    "dateTime": "2018-02-11T05:30:42Z",
    "goals": {
      "away": 4,
      "home": 6
    }
  },
  "coordinates": {
    "x": 0,
    "y": 0
  },
  "team": {
    "id": 28,
    "name": "San Jose Sharks",
    "link": "/api/v1/teams/28",
    "triCode": "SJS"
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|players|[object]|false|No description|
|» player|object|false|No description|
|»» id|number|false|No description|
|»» fullName|string|false|No description|
|»» link|string(uri)|false|No description|
|» playerType|string|false|No description|
|result|object|false|No description|
|» event|string|false|No description|
|» eventCode|string|false|No description|
|» eventTypeId|string|false|No description|
|» description|string|false|No description|
|about|object|false|No description|
|» eventIdx|number|false|No description|
|» eventId|number|false|No description|
|» period|number|false|No description|
|» periodType|string|false|No description|
|» ordinalNum|string|false|No description|
|» periodTime|string|false|No description|
|» periodTimeRemaining|string|false|No description|
|» dateTime|string(date-time)|false|No description|
|» goals|object|false|No description|
|»» away|number|false|No description|
|»» home|number|false|No description|
|» coordinates|object|false|No description|
|»» x|number|false|No description|
|»» y|number|false|No description|
|» team|object|false|No description|
|»» id|number|false|No description|
|»» name|string|false|No description|
|»» link|string(uri)|false|No description|
|»» triCode|string|false|No description|

<h2 id="tocSphoto">Photo</h2>

<a id="schemaphoto"></a>

```json
{
  "title": "string",
  "altText": "string",
  "cuts": {
    "aspectRatio": "16:9",
    "width": 2568,
    "height": 1444,
    "src": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
    "at2x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg",
    "at3x": "https://nhl.bamcontent.com/images/photos/295824704/2568x1444/cut.jpg"
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|title|string|false|No description|
|altText|string|false|No description|
|cuts|object|false|No description|
|» aspectRatio|string|false|No description|
|» width|number|false|No description|
|» height|number|false|No description|
|» src|string(url)|false|No description|
|» at2x|string(url)|false|No description|
|» at3x|string(url)|false|No description|

<h2 id="tocSplayer">Player</h2>

<a id="schemaplayer"></a>

```json
{
  "id": 8466138,
  "fullName": "Joe Thornton",
  "link": "/api/v1/people/8466138",
  "firstName": "Joe",
  "lastName": "Thornton",
  "primaryNumber": "19",
  "birthDate": "1979-07-02",
  "currentAge": 38,
  "birthCity": "London",
  "birthStateProvince": "ON",
  "birthCountry": "CAN",
  "nationality": "CAN",
  "height": "6' 4\"",
  "weight": 220,
  "active": true,
  "alternateCaptain": true,
  "captain": true,
  "rookie": true,
  "shootsCatches": "L",
  "rosterStatus": "I",
  "currentTeam": {
    "id": 28,
    "name": "San Jose Sharks",
    "link": "/api/v1/teams/28"
  },
  "primaryPosition": {
    "code": "C",
    "name": "Center",
    "type": "Forward",
    "abbreviation": "C"
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|id|number|false|No description|
|fullName|string|false|No description|
|link|string(uri)|false|No description|
|firstName|string|false|No description|
|lastName|string|false|No description|
|primaryNumber|string|false|No description|
|birthDate|string(date)|false|No description|
|currentAge|number|false|No description|
|birthCity|string|false|No description|
|birthStateProvince|string|false|No description|
|birthCountry|string|false|No description|
|nationality|string|false|No description|
|height|string|false|No description|
|weight|number|false|No description|
|active|boolean|false|No description|
|alternateCaptain|boolean|false|No description|
|captain|boolean|false|No description|
|rookie|boolean|false|No description|
|shootsCatches|string|false|No description|
|rosterStatus|string|false|No description|
|currentTeam|object|false|No description|
|» id|number|false|No description|
|» name|string|false|No description|
|» link|string(uri)|false|No description|
|primaryPosition|object|false|No description|
|» code|string|false|No description|
|» name|string|false|No description|
|» type|string|false|No description|
|» abbreviation|string|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|shootsCatches|L|
|shootsCatches|R|

<h2 id="tocSplayers">Players</h2>

<a id="schemaplayers"></a>

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 8466138,
      "fullName": "Joe Thornton",
      "link": "/api/v1/people/8466138",
      "firstName": "Joe",
      "lastName": "Thornton",
      "primaryNumber": "19",
      "birthDate": "1979-07-02",
      "currentAge": 38,
      "birthCity": "London",
      "birthStateProvince": "ON",
      "birthCountry": "CAN",
      "nationality": "CAN",
      "height": "6' 4\"",
      "weight": 220,
      "active": true,
      "alternateCaptain": true,
      "captain": true,
      "rookie": true,
      "shootsCatches": "L",
      "rosterStatus": "I",
      "currentTeam": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28"
      },
      "primaryPosition": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      }
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|true|No description|
|teams|[[Player](#schemaplayer)]|false|No description|

<h2 id="tocSplayerstats">PlayerStats</h2>

<a id="schemaplayerstats"></a>

```json
{
  "copyright": "string",
  "stats": [
    {
      "type": {
        "displayName": "byDayOfWeek"
      },
      "splits": [
        {
          "season": "20172018",
          "stat": {
            "timeOnIce": "862:13",
            "assists": 23,
            "goals": 13,
            "pim": 38,
            "shots": 75,
            "games": 47,
            "hits": 32,
            "powerPlayGoals": 7,
            "powerPlayPoints": 18,
            "powerPlayTimeOnIce": "168:28",
            "evenTimeOnIce": "692:50",
            "penaltyMinutes": "38",
            "faceOffPct": 52.04,
            "shotPct": 17.3,
            "gameWinningGoals": 1,
            "overTimeGoals": 0,
            "shortHandedGoals": 0,
            "shortHandedPoints": 0,
            "shortHandedTimeOnIce": "00:55",
            "blocked": 18,
            "plusMinus": -9,
            "points": 36,
            "shifts": 1077,
            "timeOnIcePerGame": "18:20",
            "evenTimeOnIcePerGame": "14:44",
            "shortHandedTimeOnIcePerGame": "00:01",
            "powerPlayTimeOnIcePerGame": "03:35",
            "rankPowerPlayGoals": "1st",
            "rankBlockedShots": "405th",
            "rankAssists": "51st",
            "rankShotPct": "246th",
            "rankGoals": "13th",
            "rankHits": "19th",
            "rankPenaltyMinutes": "111th",
            "rankShortHandedGoals": "133rd",
            "rankPlusMinus": "176th",
            "rankShots": "2nd",
            "rankPoints": "20th",
            "rankOvertimeGoals": "9th",
            "rankGamesPlayed": "1st",
            "goalsInFirstPeriod": 6,
            "goalsInSecondPeriod": 3,
            "goalsInThirdPeriod": 4,
            "goalsTrailingByOne": 2,
            "goalsTrailingByTwo": 1,
            "goalsTrailingByThreePlus": 1,
            "goalsWhenTied": 4,
            "goalsLeadingByOne": 2,
            "goalsLeadingByTwo": 3
          },
          "isHome": true,
          "isWin": true,
          "isOT": true,
          "month": 1,
          "dayOfWeek": 1,
          "opponent": {
            "id": 1,
            "name": "New Jersey Devils",
            "link": "/api/v1/teams/1"
          },
          "opponentDivision": {
            "id": 16,
            "name": "Central",
            "link": "/api/v1/divisions/16"
          },
          "opponentConference": {
            "id": 5,
            "name": "Western",
            "link": "/api/v1/conferences/5"
          }
        }
      ]
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|stats|[object]|false|No description|
|» type|object|false|No description|
|»» displayName|string|false|No description|
|» splits|[object]|false|No description|
|»» season|string|false|No description|
|»» stat|object|false|No description|
|»»» timeOnIce|string|false|No description|
|»»» assists|string|false|No description|
|»»» goals|number|false|No description|
|»»» pim|number|false|No description|
|»»» shots|number|false|No description|
|»»» games|number|false|No description|
|»»» hits|number|false|No description|
|»»» powerPlayGoals|number|false|No description|
|»»» powerPlayPoints|number|false|No description|
|»»» powerPlayTimeOnIce|number|false|No description|
|»»» evenTimeOnIce|number|false|No description|
|»»» penaltyMinutes|number|false|No description|
|»»» faceOffPct|number(double)|false|No description|
|»»» shotPct|number(float)|false|No description|
|»»» gameWinningGoals|number|false|No description|
|»»» overTimeGoals|number|false|No description|
|»»» shortHandedGoals|number|false|No description|
|»»» shortHandedPoints|number|false|No description|
|»»» shortHandedTimeOnIce|string|false|No description|
|»»» blocked|number|false|No description|
|»»» plusMinus|number|false|No description|
|»»» points|number|false|No description|
|»»» shifts|number|false|No description|
|»»» timeOnIcePerGame|string|false|No description|
|»»» evenTimeOnIcePerGame|string|false|No description|
|»»» shortHandedTimeOnIcePerGame|string|false|No description|
|»»» powerPlayTimeOnIcePerGame|string|false|No description|
|»»» rankPowerPlayGoals|string|false|No description|
|»»» rankBlockedShots|string|false|No description|
|»»» rankAssists|string|false|No description|
|»»» rankShotPct|string|false|No description|
|»»» rankGoals|string|false|No description|
|»»» rankHits|string|false|No description|
|»»» rankPenaltyMinutes|string|false|No description|
|»»» rankShortHandedGoals|string|false|No description|
|»»» rankPlusMinus|string|false|No description|
|»»» rankShots|string|false|No description|
|»»» rankPoints|string|false|No description|
|»»» rankOvertimeGoals|string|false|No description|
|»»» rankGamesPlayed|string|false|No description|
|»»» goalsInFirstPeriod|number|false|No description|
|»»» goalsInSecondPeriod|number|false|No description|
|»»» goalsInThirdPeriod|number|false|No description|
|»»» goalsTrailingByOne|number|false|No description|
|»»» goalsTrailingByTwo|number|false|No description|
|»»» goalsTrailingByThreePlus|number|false|No description|
|»»» goalsWhenTied|number|false|No description|
|»»» goalsLeadingByOne|number|false|No description|
|»»» goalsLeadingByTwo|number|false|No description|
|»» isHome|boolean|false|No description|
|»» isWin|boolean|false|No description|
|»» isOT|boolean|false|No description|
|»» month|number|false|No description|
|»» dayOfWeek|number|false|No description|
|»» opponent|object|false|No description|
|»»» id|number|false|No description|
|»»» name|string|false|No description|
|»»» link|string(uri)|false|No description|
|»» opponentDivision|object|false|No description|
|»»» id|number|false|No description|
|»»» name|string|false|No description|
|»»» link|string(uri)|false|No description|
|»» opponentConference|object|false|No description|
|»»» id|number|false|No description|
|»»» name|string|false|No description|
|»»» link|string(uri)|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|displayName|byDayOfWeek|
|displayName|byMonth|
|displayName|goalsByGameSituation|
|displayName|homeAndAway|
|displayName|onPaceRegularSeason|
|displayName|regularSeasonStatRankings|
|displayName|statsSingleSeason|
|displayName|vsConference|
|displayName|vsDivision|
|displayName|vsTeam|
|displayName|winLoss|

<h2 id="tocSroster">Roster</h2>

<a id="schemaroster"></a>

```json
{
  "person": {
    "id": 8466138,
    "fullName": "Joe Thornton",
    "link": "/api/v1/people/8466138"
  },
  "jerseyNumber": 19,
  "position": {
    "code": "C",
    "name": "Center",
    "type": "Forward",
    "abbreviation": "C"
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|person|object|false|No description|
|» id|number|false|No description|
|» fullName|string|false|No description|
|» link|string(uri)|false|No description|
|jerseyNumber|number|false|No description|
|position|object|false|No description|
|» code|string|false|No description|
|» name|string|false|No description|
|» type|string|false|No description|
|» abbreviation|string|false|No description|

<h2 id="tocSrosters">Rosters</h2>

<a id="schemarosters"></a>

```json
{
  "copyright": "string",
  "teams": [
    {
      "person": {
        "id": 8466138,
        "fullName": "Joe Thornton",
        "link": "/api/v1/people/8466138"
      },
      "jerseyNumber": 19,
      "position": {
        "code": "C",
        "name": "Center",
        "type": "Forward",
        "abbreviation": "C"
      }
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|teams|[[Roster](#schemaroster)]|false|No description|

<h2 id="tocSschedule">Schedule</h2>

<a id="schemaschedule"></a>

```json
{
  "copyright": "string",
  "totalItems": 9,
  "totalEvents": 0,
  "totalGames": 9,
  "totalMatches": 0,
  "wait": 10,
  "dates": [
    {
      "date": "2018-02-10",
      "totalItems": 9,
      "totalEvents": 0,
      "totalGames": 9,
      "totalMatches": 0,
      "games": [
        {
          "gamePk": 2017020851,
          "link": "/api/v1/game/2017020851/feed/live",
          "gameType": "R",
          "season": "20172018",
          "gameDate": "2018-02-11T03:00:00Z",
          "status": {
            "abstractGameState": "Final",
            "codedGameState": "7",
            "detailedState": "Final",
            "statusCode": "7",
            "startTimeTBD": true
          },
          "teams": {
            "away": {
              "leagueRecord": {
                "wins": 23,
                "losses": 27,
                "ot": 4,
                "type": "league"
              },
              "score": 4,
              "team": {
                "id": 22,
                "name": "Edmonton Oilers",
                "link": "/api/v1/teams/22"
              }
            },
            "home": {
              "leagueRecord": {
                "wins": 29,
                "losses": 18,
                "ot": 8,
                "type": "league"
              },
              "score": 6,
              "team": {
                "id": 28,
                "name": "San Jose Sharks",
                "link": "/api/v1/teams/28"
              }
            }
          },
          "linescore": {
            "currentPeriod": 3,
            "currentPeriodOrdinal": "3rd",
            "currentPeriodTimeRemaining": "Final",
            "periods": [
              {
                "periodType": "REGULAR",
                "startTime": "2018-02-11T03:09:50Z",
                "endTime": "2018-02-11T03:44:47Z",
                "num": 1,
                "ordinalNum": "1st",
                "home": {
                  "goals": 2,
                  "shotsOnGoal": 14,
                  "rinkSide": "left"
                },
                "away": {
                  "goals": 0,
                  "shotsOnGoal": 9,
                  "rinkSide": "right"
                }
              }
            ],
            "shootoutInfo": {
              "away": {
                "scores": 0,
                "attempts": 0
              },
              "home": {
                "scores": 0,
                "attempts": 0
              }
            },
            "teams": {
              "home": {
                "team": {
                  "id": 28,
                  "name": "San Jose Sharks",
                  "link": "/api/v1/teams/28",
                  "abbreviation": "SJS",
                  "triCode": "SJS"
                },
                "goals": 6,
                "shotsOnGoal": 30,
                "goaliePulled": true,
                "numSkaters": 5,
                "powerPlay": true
              },
              "away": {
                "team": {
                  "id": 28,
                  "name": "San Jose Sharks",
                  "link": "/api/v1/teams/28",
                  "abbreviation": "SJS",
                  "triCode": "SJS"
                },
                "goals": 6,
                "shotsOnGoal": 30,
                "goaliePulled": true,
                "numSkaters": 5,
                "powerPlay": true
              }
            },
            "powerPlayStrength": "Even",
            "hasShootout": true,
            "intermissionInfo": {
              "intermissionTimeRemaining": 0,
              "intermissionTimeElapsed": 0,
              "inIntermission": true
            },
            "powerPlayInfo": {
              "situationTimeRemaining": 0,
              "situationTimeElapsed": 72,
              "inSituation": true
            }
          },
          "venue": {
            "name": "SAP Center at San Jose",
            "link": "/api/v1/venues/null"
          },
          "tickets": [
            {
              "ticketType": "buysell",
              "ticketLink": "http://www.ticketmaster.com/event/090052DD92E620B4?BRAND=ducks&extcmp=tm208344&utm_source=NHL.com&utm_medium=client&utm_campaign=NHL_LEAGUE_ANA&utm_content=SCHEDULE_PAGE&camefrom=CFC_DUCKS_1718_Web_DucksSchedule"
            }
          ],
          "content": {
            "link": "/api/v1/game/2017020851/content"
          }
        }
      ],
      "events": [
        {}
      ],
      "matches": [
        {}
      ]
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|totalItems|number|false|No description|
|totalEvents|number|false|No description|
|totalGames|number|false|No description|
|totalMatches|number|false|No description|
|wait|number|false|No description|
|dates|[[ScheduleDay](#schemascheduleday)]|false|No description|

<h2 id="tocSscheduleday">ScheduleDay</h2>

<a id="schemascheduleday"></a>

```json
{
  "date": "2018-02-10",
  "totalItems": 9,
  "totalEvents": 0,
  "totalGames": 9,
  "totalMatches": 0,
  "games": [
    {
      "gamePk": 2017020851,
      "link": "/api/v1/game/2017020851/feed/live",
      "gameType": "R",
      "season": "20172018",
      "gameDate": "2018-02-11T03:00:00Z",
      "status": {
        "abstractGameState": "Final",
        "codedGameState": "7",
        "detailedState": "Final",
        "statusCode": "7",
        "startTimeTBD": true
      },
      "teams": {
        "away": {
          "leagueRecord": {
            "wins": 23,
            "losses": 27,
            "ot": 4,
            "type": "league"
          },
          "score": 4,
          "team": {
            "id": 22,
            "name": "Edmonton Oilers",
            "link": "/api/v1/teams/22"
          }
        },
        "home": {
          "leagueRecord": {
            "wins": 29,
            "losses": 18,
            "ot": 8,
            "type": "league"
          },
          "score": 6,
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28"
          }
        }
      },
      "linescore": {
        "currentPeriod": 3,
        "currentPeriodOrdinal": "3rd",
        "currentPeriodTimeRemaining": "Final",
        "periods": [
          {
            "periodType": "REGULAR",
            "startTime": "2018-02-11T03:09:50Z",
            "endTime": "2018-02-11T03:44:47Z",
            "num": 1,
            "ordinalNum": "1st",
            "home": {
              "goals": 2,
              "shotsOnGoal": 14,
              "rinkSide": "left"
            },
            "away": {
              "goals": 0,
              "shotsOnGoal": 9,
              "rinkSide": "right"
            }
          }
        ],
        "shootoutInfo": {
          "away": {
            "scores": 0,
            "attempts": 0
          },
          "home": {
            "scores": 0,
            "attempts": 0
          }
        },
        "teams": {
          "home": {
            "team": {
              "id": 28,
              "name": "San Jose Sharks",
              "link": "/api/v1/teams/28",
              "abbreviation": "SJS",
              "triCode": "SJS"
            },
            "goals": 6,
            "shotsOnGoal": 30,
            "goaliePulled": true,
            "numSkaters": 5,
            "powerPlay": true
          },
          "away": {
            "team": {
              "id": 28,
              "name": "San Jose Sharks",
              "link": "/api/v1/teams/28",
              "abbreviation": "SJS",
              "triCode": "SJS"
            },
            "goals": 6,
            "shotsOnGoal": 30,
            "goaliePulled": true,
            "numSkaters": 5,
            "powerPlay": true
          }
        },
        "powerPlayStrength": "Even",
        "hasShootout": true,
        "intermissionInfo": {
          "intermissionTimeRemaining": 0,
          "intermissionTimeElapsed": 0,
          "inIntermission": true
        },
        "powerPlayInfo": {
          "situationTimeRemaining": 0,
          "situationTimeElapsed": 72,
          "inSituation": true
        }
      },
      "venue": {
        "name": "SAP Center at San Jose",
        "link": "/api/v1/venues/null"
      },
      "tickets": [
        {
          "ticketType": "buysell",
          "ticketLink": "http://www.ticketmaster.com/event/090052DD92E620B4?BRAND=ducks&extcmp=tm208344&utm_source=NHL.com&utm_medium=client&utm_campaign=NHL_LEAGUE_ANA&utm_content=SCHEDULE_PAGE&camefrom=CFC_DUCKS_1718_Web_DucksSchedule"
        }
      ],
      "content": {
        "link": "/api/v1/game/2017020851/content"
      }
    }
  ],
  "events": [
    {}
  ],
  "matches": [
    {}
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|date|string(date)|false|No description|
|totalItems|number|false|No description|
|totalEvents|number|false|No description|
|totalGames|number|false|No description|
|totalMatches|number|false|No description|
|games|[[ScheduleGame](#schemaschedulegame)]|false|No description|
|events|[object]|false|No description|
|matches|[object]|false|No description|

<h2 id="tocSschedulegame">ScheduleGame</h2>

<a id="schemaschedulegame"></a>

```json
{
  "gamePk": 2017020851,
  "link": "/api/v1/game/2017020851/feed/live",
  "gameType": "R",
  "season": "20172018",
  "gameDate": "2018-02-11T03:00:00Z",
  "status": {
    "abstractGameState": "Final",
    "codedGameState": "7",
    "detailedState": "Final",
    "statusCode": "7",
    "startTimeTBD": true
  },
  "teams": {
    "away": {
      "leagueRecord": {
        "wins": 23,
        "losses": 27,
        "ot": 4,
        "type": "league"
      },
      "score": 4,
      "team": {
        "id": 22,
        "name": "Edmonton Oilers",
        "link": "/api/v1/teams/22"
      }
    },
    "home": {
      "leagueRecord": {
        "wins": 29,
        "losses": 18,
        "ot": 8,
        "type": "league"
      },
      "score": 6,
      "team": {
        "id": 28,
        "name": "San Jose Sharks",
        "link": "/api/v1/teams/28"
      }
    }
  },
  "linescore": {
    "currentPeriod": 3,
    "currentPeriodOrdinal": "3rd",
    "currentPeriodTimeRemaining": "Final",
    "periods": [
      {
        "periodType": "REGULAR",
        "startTime": "2018-02-11T03:09:50Z",
        "endTime": "2018-02-11T03:44:47Z",
        "num": 1,
        "ordinalNum": "1st",
        "home": {
          "goals": 2,
          "shotsOnGoal": 14,
          "rinkSide": "left"
        },
        "away": {
          "goals": 0,
          "shotsOnGoal": 9,
          "rinkSide": "right"
        }
      }
    ],
    "shootoutInfo": {
      "away": {
        "scores": 0,
        "attempts": 0
      },
      "home": {
        "scores": 0,
        "attempts": 0
      }
    },
    "teams": {
      "home": {
        "team": {
          "id": 28,
          "name": "San Jose Sharks",
          "link": "/api/v1/teams/28",
          "abbreviation": "SJS",
          "triCode": "SJS"
        },
        "goals": 6,
        "shotsOnGoal": 30,
        "goaliePulled": true,
        "numSkaters": 5,
        "powerPlay": true
      },
      "away": {
        "team": {
          "id": 28,
          "name": "San Jose Sharks",
          "link": "/api/v1/teams/28",
          "abbreviation": "SJS",
          "triCode": "SJS"
        },
        "goals": 6,
        "shotsOnGoal": 30,
        "goaliePulled": true,
        "numSkaters": 5,
        "powerPlay": true
      }
    },
    "powerPlayStrength": "Even",
    "hasShootout": true,
    "intermissionInfo": {
      "intermissionTimeRemaining": 0,
      "intermissionTimeElapsed": 0,
      "inIntermission": true
    },
    "powerPlayInfo": {
      "situationTimeRemaining": 0,
      "situationTimeElapsed": 72,
      "inSituation": true
    }
  },
  "venue": {
    "name": "SAP Center at San Jose",
    "link": "/api/v1/venues/null"
  },
  "tickets": [
    {
      "ticketType": "buysell",
      "ticketLink": "http://www.ticketmaster.com/event/090052DD92E620B4?BRAND=ducks&extcmp=tm208344&utm_source=NHL.com&utm_medium=client&utm_campaign=NHL_LEAGUE_ANA&utm_content=SCHEDULE_PAGE&camefrom=CFC_DUCKS_1718_Web_DucksSchedule"
    }
  ],
  "content": {
    "link": "/api/v1/game/2017020851/content"
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|gamePk|number|false|No description|
|link|string(uri)|false|No description|
|gameType|string|false|No description|
|season|string|false|No description|
|gameDate|string(date-time)|false|No description|
|status|object|false|No description|
|» abstractGameState|string|false|No description|
|» codedGameState|string|false|No description|
|» detailedState|string|false|No description|
|» statusCode|string|false|No description|
|» startTimeTBD|boolean|false|No description|
|teams|object|false|No description|
|» away|object|false|No description|
|»» leagueRecord|object|false|No description|
|»»» wins|number|false|No description|
|»»» losses|number|false|No description|
|»»» ot|number|false|No description|
|»»» type|string|false|No description|
|»» score|number|false|No description|
|»» team|object|false|No description|
|»»» id|number|false|No description|
|»»» name|string|false|No description|
|»»» link|string|false|No description|
|»» home|object|false|No description|
|»»» leagueRecord|object|false|No description|
|»»»» wins|number|false|No description|
|»»»» losses|number|false|No description|
|»»»» ot|number|false|No description|
|»»»» type|string|false|No description|
|»»» score|number|false|No description|
|»»» team|object|false|No description|
|»»»» id|number|false|No description|
|»»»» name|string|false|No description|
|»»»» link|string(uri)|false|No description|
|»»» linescore|[GameLinescore](#schemagamelinescore)|false|No description|
|»»» venue|object|false|No description|
|»»»» name|string|false|No description|
|»»»» link|string(uri)|false|No description|
|»»» tickets|[object]|false|No description|
|»»»» ticketType|string|false|No description|
|»»»» ticketLink|string(url)|false|No description|
|»»» content|object|false|No description|
|»»»» link|string(uri)|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|ticketType|buysell|
|ticketType|club buysell|
|ticketType|club mobile|
|ticketType|club mobile buysell|
|ticketType|club ticket|
|ticketType|mobile app ticket|
|ticketType|mobile buysell|
|ticketType|mobile ticket|
|ticketType|tablet app ticket|
|ticketType|ticket|

<h2 id="tocSstandings">Standings</h2>

<a id="schemastandings"></a>

```json
{
  "copyright": "string",
  "records": [
    {
      "standingsType": "regularSeason",
      "league": {
        "id": 133,
        "name": "National Hockey League",
        "link": "/api/v1/league/133"
      },
      "division": {
        "id": 15,
        "name": "Pacific",
        "link": "/api/v1/divisions/15"
      },
      "conference": {
        "id": 5,
        "name": "Western",
        "link": "/api/v1/conferences/5"
      },
      "teamRecords": [
        {
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28"
          },
          "leagueRecord": {
            "wins": 29,
            "losses": 18,
            "ot": 8,
            "type": "league"
          },
          "goalsAgainst": 154,
          "goalsScored": 162,
          "points": 66,
          "divisionRank": "2",
          "conferenceRank": "7",
          "leagueRank": "11",
          "wildCardRank": "0",
          "row": 26,
          "gamesPlayed": 55,
          "streak": {
            "streakType": "wins",
            "streakNumber": 1,
            "streakCode": "W1"
          },
          "lastUpdated": "2018-02-11T00:57:18Z"
        }
      ]
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|records|[object]|false|No description|
|» standingsType|string|false|No description|
|» league|object|false|No description|
|»» id|number|false|No description|
|»» name|string|false|No description|
|»» link|string(uri)|false|No description|
|» division|object|false|No description|
|»» id|number|false|No description|
|»» name|string|false|No description|
|»» link|string(uri)|false|No description|
|» conference|object|false|No description|
|»» id|number|false|No description|
|»» name|string|false|No description|
|»» link|string(uri)|false|No description|
|» teamRecords|[object]|false|No description|
|»» team|object|false|No description|
|»»» id|number|false|No description|
|»»» name|string|false|No description|
|»»» link|string(uri)|false|No description|
|»» leagueRecord|object|false|No description|
|»»» wins|number|false|No description|
|»»» losses|number|false|No description|
|»»» ot|number|false|No description|
|»»» type|string|false|No description|
|»» goalsAgainst|number|false|No description|
|»» goalsScored|number|false|No description|
|»» points|number|false|No description|
|»» divisionRank|string|false|No description|
|»» conferenceRank|string|false|No description|
|»» leagueRank|string|false|No description|
|»» wildCardRank|string|false|No description|
|»» row|number|false|No description|
|»» gamesPlayed|number|false|No description|
|»» streak|object|false|No description|
|»»» streakType|string|false|No description|
|»»» streakNumber|number|false|No description|
|»»» streakCode|string|false|No description|
|»» lastUpdated|string(date-time)|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|standingsType|regularSeason|

<h2 id="tocSstandingtypes">StandingTypes</h2>

<a id="schemastandingtypes"></a>

```json
[
  {
    "name": "regularSeason",
    "description": "Regular Season Standings"
  }
]
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|name|string|false|No description|
|description|string|false|No description|

<h2 id="tocSstattypes">StatTypes</h2>

<a id="schemastattypes"></a>

```json
[
  {
    "displayName": "byDayOfWeek"
  }
]
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|displayName|string|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|displayName|byDayOfWeek|
|displayName|byDayOfWeekPlayoffs|
|displayName|byMonth|
|displayName|byMonthPlayoffs|
|displayName|careerPlayoffs|
|displayName|careerRegularSeason|
|displayName|gameLog|
|displayName|goalsByGameSituation|
|displayName|goalsByGameSituationPlayoffs|
|displayName|homeAndAway|
|displayName|homeAndAwayPlayoffs|
|displayName|onPaceRegularSeason|
|displayName|playoffGameLog|
|displayName|playoffStatRankings|
|displayName|regularSeasonStatRankings|
|displayName|statsSingleSeason|
|displayName|statsSingleSeasonPlayoffs|
|displayName|vsConference|
|displayName|vsConferencePlayoffs|
|displayName|vsDivision|
|displayName|vsDivisionPlayoffs|
|displayName|vsTeam|
|displayName|vsTeamPlayoffs|
|displayName|winLoss|
|displayName|winLossPlayoffs|
|displayName|yearByYear|
|displayName|yearByYearPlayoffs|
|displayName|yearByYearPlayoffsRank|
|displayName|yearByYearRank|

<h2 id="tocSteam">Team</h2>

<a id="schemateam"></a>

```json
{
  "id": 28,
  "name": "San Jose Sharks",
  "link": "/api/v1/teams/28",
  "venue": {
    "name": "SAP Center at San Jose",
    "link": "/api/v1/venues/null",
    "city": "San Jose",
    "timeZone": {
      "id": "America/Los_Angeles",
      "offset": -8,
      "tz": "PST"
    }
  },
  "abbreviation": "SJS",
  "triCode": "SJS",
  "teamName": "Sharks",
  "locationName": "San Jose",
  "firstYearOfPlay": 1990,
  "division": {
    "id": 15,
    "name": "Pacific",
    "link": "/api/v1/divisions/15"
  },
  "conference": {
    "id": 5,
    "name": "Western",
    "link": "/api/v1/conferences/5"
  },
  "franchise": {
    "id": 29,
    "name": "Sharks",
    "link": "/api/v1/franchises/29"
  },
  "roster": {
    "roster": [
      {
        "person": {
          "id": 8466138,
          "fullName": "Joe Thornton",
          "link": "/api/v1/people/8466138"
        },
        "jerseyNumber": 19,
        "position": {
          "code": "C",
          "name": "Center",
          "type": "Forward",
          "abbreviation": "C"
        }
      }
    ]
  },
  "nextGameSchedule": {
    "totalItems": 1,
    "totalEvents": 0,
    "totalGames": 1,
    "totalMatches": 0,
    "dates": [
      {
        "date": "2018-02-10",
        "totalItems": 1,
        "totalEvents": 0,
        "totalGames": 1,
        "totalMatches": 0,
        "games": [
          {
            "gamePk": 2017020851,
            "link": "/api/v1/game/2017020851/feed/live",
            "gameType": "R",
            "season": "20172018",
            "gameDate": "2018-02-11T03:00:00Z",
            "status": {
              "abstractGameState": "Live",
              "codedGameState": "3",
              "detailedState": "In Progress",
              "statusCode": "2",
              "startTimeTBD": true
            },
            "teams": {
              "away": {
                "leagueRecord": {
                  "wins": 23,
                  "losses": 26,
                  "ot": 4,
                  "type": "league"
                },
                "score": 0,
                "team": {
                  "id": 22,
                  "name": "Edmonton Oilers",
                  "link": "/api/v1/teams/22"
                }
              },
              "home": {
                "leagueRecord": {
                  "wins": 28,
                  "losses": 18,
                  "ot": 8,
                  "type": "league"
                },
                "score": 2,
                "team": {
                  "id": 28,
                  "name": "San Jose Sharks",
                  "link": "/api/v1/teams/28"
                }
              }
            },
            "venue": {
              "name": "SAP Center at San Jose",
              "link": "/api/v1/venues/null"
            },
            "content": {
              "link": "/api/v1/game/2017020851/content"
            }
          }
        ],
        "events": [
          {}
        ],
        "matches": [
          {}
        ]
      }
    ]
  },
  "shortName": "San Jose",
  "officialSiteUrl": "http://www.sjsharks.com",
  "franchiseId": 29,
  "active": true
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|id|number|false|No description|
|name|string|false|No description|
|link|string(uri)|false|No description|
|venue|[Venue](#schemavenue)|false|No description|
|abbreviation|string|false|No description|
|triCode|string|false|No description|
|teamName|string|false|No description|
|locationName|string|false|No description|
|firstYearOfPlay|number|false|No description|
|division|object|false|No description|
|» id|number|false|No description|
|» name|string|false|No description|
|» link|string(uri)|false|No description|
|conference|object|false|No description|
|» id|number|false|No description|
|» name|string|false|No description|
|» link|string(uri)|false|No description|
|franchise|[Franchise](#schemafranchise)|false|No description|
|roster|object|false|No description|
|» roster|[[Roster](#schemaroster)]|false|No description|
|nextGameSchedule|object|false|No description|
|» totalItems|number|false|No description|
|» totalEvents|number|false|No description|
|» totalGames|number|false|No description|
|» totalMatches|number|false|No description|
|» dates|[object]|false|No description|
|»» date|string(date)|false|No description|
|»» totalItems|number|false|No description|
|»» totalEvents|number|false|No description|
|»» totalGames|number|false|No description|
|»» totalMatches|number|false|No description|
|»» games|[object]|false|No description|
|»»» gamePk|number|false|No description|
|»»» link|string(uri)|false|No description|
|»»» gameType|string|false|No description|
|»»» season|string|false|No description|
|»»» gameDate|string(date-time)|false|No description|
|»»» status|object|false|No description|
|»»»» abstractGameState|string|false|No description|
|»»»» codedGameState|string|false|No description|
|»»»» detailedState|string|false|No description|
|»»»» statusCode|string|false|No description|
|»»»» startTimeTBD|boolean|false|No description|
|»»» teams|object|false|No description|
|»»»» away|object|false|No description|
|»»»»» leagueRecord|object|false|No description|
|»»»»»» wins|number|false|No description|
|»»»»»» losses|number|false|No description|
|»»»»»» ot|number|false|No description|
|»»»»»» type|string|false|No description|
|»»»»» score|number|false|No description|
|»»»»» team|object|false|No description|
|»»»»»» id|number|false|No description|
|»»»»»» name|string|false|No description|
|»»»»»» link|string(uri)|false|No description|
|»»»»» home|object|false|No description|
|»»»»»» leagueRecord|object|false|No description|
|»»»»»»» wins|number|false|No description|
|»»»»»»» losses|number|false|No description|
|»»»»»»» ot|number|false|No description|
|»»»»»»» type|string|false|No description|
|»»»»»» score|number|false|No description|
|»»»»»» team|object|false|No description|
|»»»»»»» id|number|false|No description|
|»»»»»»» name|string|false|No description|
|»»»»»»» link|string(uri)|false|No description|
|»»»»»» venue|object|false|No description|
|»»»»»»» name|string|false|No description|
|»»»»»»» link|string(uri)|false|No description|
|»»»»»» content|object|false|No description|
|»»»»»»» link|string(uri)|false|No description|
|»»»»»» events|[object]|false|No description|
|»»»»»» matches|[object]|false|No description|
|»»»»» shortName|string|false|No description|
|»»»»» officialSiteUrl|string(url)|false|No description|
|»»»»» franchiseId|number|false|No description|
|»»»»» active|boolean|false|No description|

#### Enumerated Values

|Property|Value|
|---|---|
|abstractGameState|Live|
|abstractGameState|Preview|
|codedGameState|2|
|codedGameState|3|
|detailedState|In Progress|
|detailedState|Pre-Game|
|statusCode|2|
|statusCode|3|

<h2 id="tocSteams">Teams</h2>

<a id="schemateams"></a>

```json
{
  "copyright": "string",
  "teams": [
    {
      "id": 28,
      "name": "San Jose Sharks",
      "link": "/api/v1/teams/28",
      "venue": {
        "name": "SAP Center at San Jose",
        "link": "/api/v1/venues/null",
        "city": "San Jose",
        "timeZone": {
          "id": "America/Los_Angeles",
          "offset": -8,
          "tz": "PST"
        }
      },
      "abbreviation": "SJS",
      "triCode": "SJS",
      "teamName": "Sharks",
      "locationName": "San Jose",
      "firstYearOfPlay": 1990,
      "division": {
        "id": 15,
        "name": "Pacific",
        "link": "/api/v1/divisions/15"
      },
      "conference": {
        "id": 5,
        "name": "Western",
        "link": "/api/v1/conferences/5"
      },
      "franchise": {
        "id": 29,
        "name": "Sharks",
        "link": "/api/v1/franchises/29"
      },
      "roster": {
        "roster": [
          {
            "person": {
              "id": 8466138,
              "fullName": "Joe Thornton",
              "link": "/api/v1/people/8466138"
            },
            "jerseyNumber": 19,
            "position": {
              "code": "C",
              "name": "Center",
              "type": "Forward",
              "abbreviation": "C"
            }
          }
        ]
      },
      "nextGameSchedule": {
        "totalItems": 1,
        "totalEvents": 0,
        "totalGames": 1,
        "totalMatches": 0,
        "dates": [
          {
            "date": "2018-02-10",
            "totalItems": 1,
            "totalEvents": 0,
            "totalGames": 1,
            "totalMatches": 0,
            "games": [
              {
                "gamePk": 2017020851,
                "link": "/api/v1/game/2017020851/feed/live",
                "gameType": "R",
                "season": "20172018",
                "gameDate": "2018-02-11T03:00:00Z",
                "status": {
                  "abstractGameState": "Live",
                  "codedGameState": "3",
                  "detailedState": "In Progress",
                  "statusCode": "2",
                  "startTimeTBD": true
                },
                "teams": {
                  "away": {
                    "leagueRecord": {},
                    "score": 0,
                    "team": {}
                  },
                  "home": {
                    "leagueRecord": {},
                    "score": 2,
                    "team": {}
                  }
                },
                "venue": {
                  "name": "SAP Center at San Jose",
                  "link": "/api/v1/venues/null"
                },
                "content": {
                  "link": "/api/v1/game/2017020851/content"
                }
              }
            ],
            "events": [
              {}
            ],
            "matches": [
              {}
            ]
          }
        ]
      },
      "shortName": "San Jose",
      "officialSiteUrl": "http://www.sjsharks.com",
      "franchiseId": 29,
      "active": true
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|teams|[[Team](#schemateam)]|false|No description|

<h2 id="tocSteamstats">TeamStats</h2>

<a id="schemateamstats"></a>

```json
{
  "copyright": "string",
  "stats": [
    {
      "type": {
        "displayName": "statsSingleSeason"
      },
      "splits": [
        {
          "stat": {
            "gamesPlayed": 55,
            "wins": 29,
            "losses": 18,
            "ot": 8,
            "pts": 66,
            "ptPctg": "60.0",
            "goalsPerGame": 2.891,
            "goalsAgainstPerGame": 2.745,
            "evGGARatio": 0.8532,
            "powerPlayPercentage": "23.9",
            "powerPlayGoals": 44,
            "powerPlayGoalsAgainst": 26,
            "powerPlayOpportunities": 184,
            "penaltyKillPercentage": "84.6",
            "shotsPerGame": 32.8,
            "shotsAllowed": 30.2182,
            "winScoreFirst": 0.679,
            "winOppScoreFirst": 0.37,
            "winLeadFirstPer": 0.85,
            "winLeadSecondPer": 0.952,
            "winOutshootOpp": 0.467,
            "winOutshotByOpp": 0.6,
            "faceOffsTaken": 3300,
            "faceOffsWon": 1675,
            "faceOffsLost": 1625,
            "faceOffWinPercentage": "50.8",
            "shootingPctg": 8.8,
            "savePctg": 0.909
          },
          "team": {
            "id": 28,
            "name": "San Jose Sharks",
            "link": "/api/v1/teams/28"
          }
        }
      ]
    }
  ]
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|copyright|string|false|No description|
|stats|[object]|false|No description|
|» type|object|false|No description|
|»» displayName|string|false|No description|
|» splits|[object]|false|No description|
|»» stat|object|false|No description|
|»»» gamesPlayed|number|false|No description|
|»»» wins|number|false|No description|
|»»» losses|number|false|No description|
|»»» ot|number|false|No description|
|»»» pts|number|false|No description|
|»»» ptPctg|string|false|No description|
|»»» goalsPerGame|number(float)|false|No description|
|»»» goalsAgainstPerGame|number(float)|false|No description|
|»»» evGGARatio|number(float)|false|No description|
|»»» powerPlayPercentage|string|false|No description|
|»»» powerPlayGoals|number|false|No description|
|»»» powerPlayGoalsAgainst|number|false|No description|
|»»» powerPlayOpportunities|number|false|No description|
|»»» penaltyKillPercentage|string|false|No description|
|»»» shotsPerGame|number(float)|false|No description|
|»»» shotsAllowed|number(float)|false|No description|
|»»» winScoreFirst|number(float)|false|No description|
|»»» winOppScoreFirst|number(float)|false|No description|
|»»» winLeadFirstPer|number(float)|false|No description|
|»»» winLeadSecondPer|number(float)|false|No description|
|»»» winOutshootOpp|number(float)|false|No description|
|»»» winOutshotByOpp|number(float)|false|No description|
|»»» faceOffsTaken|number|false|No description|
|»»» faceOffsWon|number|false|No description|
|»»» faceOffsLost|number|false|No description|
|»»» faceOffWinPercentage|string|false|No description|
|»»» shootingPctg|number(float)|false|No description|
|»»» savePctg|number(float)|false|No description|
|»» team|object|false|No description|
|»»» id|number|false|No description|
|»»» name|string|false|No description|
|»»» link|string(uri)|false|No description|

<h2 id="tocSvenue">Venue</h2>

<a id="schemavenue"></a>

```json
{
  "name": "SAP Center at San Jose",
  "link": "/api/v1/venues/null",
  "city": "San Jose",
  "timeZone": {
    "id": "America/Los_Angeles",
    "offset": -8,
    "tz": "PST"
  }
}
```

### Properties

|Name|Type|Required|Description|
|---|---|---|---|
|name|string|false|No description|
|link|string(uri)|false|No description|
|city|string|false|No description|
|timeZone|object|false|No description|
|» id|string|false|No description|
|» offset|number|false|No description|
|» tz|string|false|No description|


