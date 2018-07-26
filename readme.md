# Verily API Documentation

## Getting Started

### **Create New Feed**
To add a new datafeed you will need to go to the dashboard and select the button to create a new feed. The feed will show under your feeds list however and will be initialised with empty values.

Once you have sent data to the feed it will become available to choose from your feeds list to be visualised.


### **Generate A New Token**
Tokens are used to verify the authenticity of the user submitting the data. You will need to go to the dashboard and select to generate a new token.


Your token can be changed at any time by returning tot he dashboard and re-generating the token however don't forget to update the token on all your feeds otherwise the data will be rejected.

---
## API's
All API's expect data to be sent in json format or they will reject the payload. To do this ensure that head contains the key/value pair Content-Type, application/json.

To test out sending data to your feed we recommend using the application Postman to make a Post request.

### setDataFeed
This is an example of how to set data using the setDataFeed api.

The setDataFeed API endpoint is: https://us-central1-verily-3d1a5.cloudfunctions.net/setDataFeed

The end points may change in future but we will keep you updated through your dashboard. 


i. data types
```javascript
token: <string>,
email: <string>,
data: <object> {
    feed-id: <object> {
        timeStamp: <string>,
        value: <object> {
            mock-data: <string>
        }
    }
},
```

ii. example of data structure
```javascript
{
    "token": "put-your-token-here",
    "email": "google-registered-email-address",
    "data": {
        "put-feed-id-here": {
            "timeStamp": "13-digit-unix-time-goes-here",
            "value": {
                "mock-data": "mock-value",
            }
        }
    }
}

```

iii. this is an example of how a completed submission would look with some mocked data
```javascript
{
    "token": "e7c33c10-90f1-11e8-9fe6-9db991fb5148",
    "email": "test@test.com",
    "data": {
        "33d08000-8ff2-11e8-9316-294f6c95a832": {
            "timeStamp": "1532624512107",
            "value": {
                "temperature": "28.8",
                "humidity": "13.5"
            }
        }
    }
}
```