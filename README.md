# currency-conversion-app

URL and Response Structure for Currency Exchange Service

URL
http://localhost:8000/currency-exchange/from/USD/to/INR



Response Structure
{
   "id":10001,
   "from":"USD",
   "to":"INR",
   "conversionMultiple":65.00,
   "environment":"8000 instance-id"
}



URL and Response Structure for Currency Conversion Service



URL
http://localhost:8100/currency-conversion/from/USD/to/INR/quantity/10



Response Structure
{
  "id": 10001,
  "from": "USD",
  "to": "INR",
  "conversionMultiple": 65.00,
  "quantity": 10,
  "totalCalculatedAmount": 650.00,
  "environment": "8000 instance-id"
}
 
 
 
 Currency Conversion Service:-
  
 http://localhost:8100/currency-conversion/from/AUD/to/INR/quantity/10
 http://localhost:8100/currency-conversion-feign/from/AUD/to/INR/quantity/10

Eureka :-

http://localhost:8761/

API-Gateway:-
http://localhost:8765/




Write this "spring.cloud.gateway.discovery.locator.enabled=true" to call other services through API-GATEWAY

http://localhost:8765/CURRENCY-EXCHANGE/currency-exchange/from/USD/to/INR

http://localhost:8765/CURRENCY-CONVERSION-SERVICE/currency-conversion-feign/from/AUD/to/INR/quantity/10

http://localhost:8765/CURRENCY-CONVERSION-SERVICE/currency-conversion/from/AUD/to/INR/quantity/10




After writing "spring.cloud.gateway.discovery.locator.lowerCaseServiceId=true" in application.properties in API GATEWAY

http://localhost:8765/currency-exchange/currency-exchange/from/USD/to/INR

http://localhost:8765/currency-conversion-service/currency-conversion-feign/from/AUD/to/INR/quantity/10

http://localhost:8765/currency-conversion-service/currency-conversion/from/AUD/to/INR/quantity/10




Custom Routing

http://localhost:8765/currency-exchange/from/AUD/to/INR
http://localhost:8765/currency-conversion/from/AUD/to/INR/quantity/10
http://localhost:8765/currency-conversion-feign/from/AUD/to/INR/quantity/10

http://localhost:8765/currency-conversion-new/from/AUD/to/INR/quantity/10



