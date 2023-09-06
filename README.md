## Description 
A rate conversion application which finds the value of given amount in one currency into another currency

## Ports Standardization 
- Spring Cloud Config Server: 8888 
- Currency Exchange Microservice: 8000, 8001, 8002, .. 
- Currency Conversion Microservice: 8100, 8101, 8102, ... 
- Netflix Eureka Naming Server: 8761 
- API Gateway: 8765

## Currency Exchange Microservice
- What is the exchange rate of one currency in another?
[http://localhost:8000/currency-exchange/from/USD/to/INR ](http://localhost:8000/currency-exchange/from/USD/to/INR) 
```json
{ "id":10001, "from":"USD", "to":"INR", "conversionMultiple":65.00, "environment":"8000 instance-id" } 
```
## Currency Conversion Microservice
- Convert 10 USD into INR
[http://localhost:8100/currency-conversion/from/USD/to/INR/quantity/10](http://localhost:8100/currency-conversion/from/USD/to/INR/quantity/10) 
```json
{ "id":10001, "from":"USD", "to":"INR", "conversionMultiple":65.00, "environment":"8000 instance-id" } 
```
## Spring Cloud Config Microservice
- Centralized Configuration Management

## Naming Server Microservice
- Load balancer(Eureka is used here, which finally uses Spring cloud load balancer)
  
## API Gateway Microservice
- Simple, yet effective way to route to APIs
- Provide cross cutting concerns: Security Monitoring/metrics
- Built on top of Spring WebFlux (Reactive Approach)
- Features:
  - Match routes on any request attribute
  - Define Predicates and Filters
  - Integrates with Spring Cloud Discovery Client (Load Balancing)
  - Path Rewriting
