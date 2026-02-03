# Sensitive Data Exposure
## Exposed Metrics
Exposed metrics is system or applications metrics that are publicly accessible when they shouldn't be. Metrics are internal measurements 
like number of requests, reponse time, error counts and others.
Common endpoints as below:
/metrics
/actuator
/actuator/metrics
/status
/health
/debug
/prometheus
Based on a video there is a website that shows about the endpoint and I just need to change the url to /metrics. https://prometheus.io/docs/prometheus/latest/getting_started/

## Exposed Credentials
Exposed credentials is people manage to see usernames, passwords and other credentials information that sould not be visible to them.
I inspect the page and search for keywords like username or password. Then, I used the giving username (email) to login with the password given to solve this challenge.
To prevent this from happening, there are several ways as below:
1. never put credentials in frontend code like html, javascript and should store secret side servers only & use backend APIs to handle auth
2. store in .env files that is private
3. remove secrets from logs and errors
4. protect config and debug endpoints (block public access to /debug, /metrics...)

## 
