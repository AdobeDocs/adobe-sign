# Overview
To prevent your API from being overwhelmed by too many requests, Adobe throttles requests to your API. When a request is throttled, the client will receive an HTTP 429 "Too Many Requests" response with an error message appropriate to the request. When a request gets back an HTTP 429 response, it means the user has consumed over the limit of allowed resources in a certain period of time. It could be a violation of per-minute, -hour, or -day limit. The user will be allowed to make more requests in the next minute, hour, or day (depending on which threshold was crossed). 

Each request made to Adobe Sign is evaluated based on the amount of system resources it will consume. Different parameters passed to the same endpoint might contribute a different amount of resource consumption. Your service package (team, business, enterprise) directly influences your transaction rate. Higher tiers of service have higher throttle thresholds.

## REST API Response
>  "code":"THROTTLING_TOO_MANY_REQUESTS",
  "message":"<error_message_with_wait_time> (apiActionId=<api_action_id>)"
  "retryAfter": <wait_time_in_seconds>
>
Also a "Retry-After" HTTP header will also be added into the response (see RFC-7231 Section 7.1.3):

Retry-After: <wait_time_in_seconds>


<wait_time_in_seconds> is the minimum time in seconds the client should wait until it can make the next same request. This means that after the retryAfter time, the client's resource count for the specific request will be reset to 0 for the over-limit period. Therefore, the client can try to send the request again and it should go through without being blocked.

**NOTE: The retryAfter time will be available in Adobe Sign 11.1 release in March 2020**

## Steps to take when throttled
It is recommended that the developers should design workflows that can handle the Http 429 exceptions gracefully and use the retry-time from either the response body or from the "Retry-After" header to recover from such errors.
