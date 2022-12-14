# api-gateway-as-both-resourceserver-and-oauth-client-redis-session
This service is an implementation of an API gateway which also acts as a OAuth client and Resource server. Supports both authrorization_code flow for UI flow and token in Authorization header for API calls from 3rd party.

Sequence to start services:
---------------------------
1. Start redis on docker
2. Start KeyCloak server
3. Start DiscoveryService
4. Start api-gateway-as-both-resourceserver-and-oauth-client-redis-session
5. Start ResourceServer
6. Start albums
7. Start photos
8. Start spa-example

There are three API gateway implementations :
---------------------------
1. spring-cloud-gateway-as-oauth2-client - Implementation of Spring Cloud API Gateway and its acting as oauth client for authorization_code flow
2. api-gateway-as-both-resourceserver-and-oauth-client-redis-session - Implementation of Spring Cloud API Gateway which also acts as a OAuth client and Resource server. Supports both authrorization_code flow for UI flow and token in Authorization header for API calls from 3rd party.
3. ApiGateway - Implementation of Spring Cloud API Gateway and just doing routing 

Few test URLS to test both UI and API flows:
--------------------------------------------------
 - http://localhost:8087/index.html
 - http://localhost:8087/ui/albums
 - http://localhost:8087/ui/users/status/check
 - http://localhost:8087/ui/users/status/check/unprotected
 - http://localhost:8087/users/status/check/unprotected
 - http://localhost:8087/index-cookie-domain
 - http://localhost:8087/index-cookie-localhost

 - http://127.0.0.1:8087/api/users/status/check
 - http://127.0.0.1:8087/api/albums
 - http://127.0.0.1:8087/api/users/status/check/unprotected
