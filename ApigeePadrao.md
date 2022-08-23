Pre flow

##Colocaria uma RF de HTTP CODE 405, e 406

# 405
```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<RaiseFault async="false" continueOnError="false" enabled="true" name="RF-MethodNotAllowed-405">
    <DisplayName>RF-MethodNotAllowed-405</DisplayName>
    <Properties/>
    <FaultResponse>
        <Set>
            <Headers>
                <Header name="Content-Type">application/json</Header>
            </Headers>
            <Payload contentType="application/json">
                 {
                  "apiVersion": "1;2021-06-19",
                  "transactionId": "593f33f6-6122-4624-8c1c-6602a14a730e",
                  "error": {
                    "httpCode": "405",
                    "errorCode": "API-RESOURCESEXTENDEDADDRESSES-405",
                    "message": "Method Not Allowed",
                    "detailedMessage": "Unavailable HTTP method.",
                    "link": {
                      "rel": "related",
                      "href": "https://api.claro.com.br/docs"
                    }
                  }
                }
            </Payload>
            <StatusCode>405</StatusCode>
            <ReasonPhrase>Method Not Allowed</ReasonPhrase>
        </Set>
    </FaultResponse>
    <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
</RaiseFault>

```

# 406 

```
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<RaiseFault async="false" continueOnError="false" enabled="true" name="RF-NotAcceptable-406">
    <DisplayName>RF-NotAcceptable-406</DisplayName>
    <Properties/>
    <FaultResponse>
        <Set>
            <Headers>
                <Header name="Content-Type">application/json</Header>
            </Headers>
            <Payload contentType="application/json">
                {
                  "apiVersion": "1;2021-06-19",
                  "transactionId": "593f33f6-6122-4624-8c1c-6602a14a730e",
                  "error": {
                    "httpCode": "406",
                    "errorCode": "API-RESOURCESEXTENDEDADDRESSES-406",
                    "message": "Request Not Acceptable",
                    "detailedMessage": "Requested content type not acceptable.",
                    "link": {
                      "rel": "related",
                      "href": "https://api.claro.com.br/docs"
                    }
                  }
                } 
            </Payload>
            <StatusCode>406</StatusCode>
            <ReasonPhrase>Request Not Acceptable</ReasonPhrase>
        </Set>
    </FaultResponse>
    <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
</RaiseFault>
```

# 415
````
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<RaiseFault async="false" continueOnError="false" enabled="true" name="RF-UnsupportedMediaType-415">
    <DisplayName>RF-UnsupportedMediaType-415</DisplayName>
    <Properties/>
    <FaultResponse>
        <Set>
            <Headers>
                <Header name="Content-Type">application/json</Header>
            </Headers>
            <Payload contentType="application/json">
            {
                "apiVersion": "{apiVersion}",
                "transactionId": "{transactionId}",
                "error": {
                    "httpCode": "415",
                    "errorCode": "API-VTALGPONSERVICESORDERS-415",
                    "message": "Unsupported Media Type",
                    "detailedMessage": "Unsupported request media type.",
                    "link": {
                      "rel": "related",
                      "href": "https://api.claro.com.br/docs"
                    }
                }
            }
            </Payload>
            <StatusCode>415</StatusCode>
            <ReasonPhrase>Unsupported Media Type</ReasonPhrase>
        </Set>
    </FaultResponse>
    <IgnoreUnresolvedVariables>true</IgnoreUnresolvedVariables>
</RaiseFault>
````

![image](https://user-images.githubusercontent.com/80789711/186254690-4cb094fe-2260-44c8-bade-24c07f3fb25c.png)


Nos metodos um
