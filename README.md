# dotnet-logging-benchmark

## Console



docker-compose -f fooapi-nologging\docker-compose.yml up --build -d 
docker-compose -f fooapi-nologging\docker-compose.yml down

```text
Running 20s test @ http://api/weatherforecast
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    15.14ms   21.33ms 427.60ms   96.06%
    Req/Sec     2.57k   747.78     4.60k    77.98%
  Latency Distribution
     50%   11.21ms
     75%   15.73ms
     90%   23.49ms
     99%   67.10ms
  589054 requests in 20.08s, 371.47MB read
Requests/sec:  29333.89
Transfer/sec:     18.50MB


```

docker-compose -f fooapi-console\docker-compose.yml up --build -d 
docker-compose -f fooapi-console\docker-compose.yml down

```text
Running 20s test @ http://api/weatherforecast
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    25.36ms   28.50ms 538.35ms   95.46%
    Req/Sec     1.47k   426.86     3.56k    78.91%
  Latency Distribution
     50%   20.32ms
     75%   27.51ms
     90%   39.06ms
     99%  111.33ms
  337869 requests in 20.08s, 213.07MB read
Requests/sec:  16825.91
Transfer/sec:     10.61MB


```


docker-compose -f fooapi-serilog\docker-compose.yml up --build -d 
docker-compose -f fooapi-serilog\docker-compose.yml down

```text
Running 20s test @ http://api/weatherforecast
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    47.84ms   44.68ms 800.53ms   96.54%
    Req/Sec   739.82    224.97     1.91k    70.88%
  Latency Distribution
     50%   41.46ms
     75%   53.07ms
     90%   67.91ms
     99%  167.46ms
  168059 requests in 20.10s, 105.98MB read
Requests/sec:   8361.59
Transfer/sec:      5.27MB

```
docker-compose -f .\fooapi-logstash\docker-compose-elk.yml up

docker-compose -f fooapi-logstash\docker-compose.yml up --build -d 
docker-compose -f fooapi-logstash\docker-compose.yml down

```text
Running 20s test @ http://api/weatherforecast
  12 threads and 400 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency    82.79ms   57.47ms 902.07ms   91.72%
    Req/Sec   416.39    160.58     1.08k    68.49%
  Latency Distribution
     50%   71.10ms
     75%   90.46ms
     90%  123.12ms
     99%  240.96ms
  93733 requests in 20.07s, 59.11MB read
Requests/sec:   4670.94
Transfer/sec:      2.95MB

```