# gin
gin performance test

https://www.cnblogs.com/zz962/p/14385334.html
https://blog.csdn.net/qq_51701007/article/details/124934130


# benchmark
autocannon -c 500 -d 20 -p 100 http://localhost:8080/ping
Running 20s test @ http://localhost:8080/ping
500 connections with 100 pipelining factor

running [==================  ] 90%
┌─────────┬────────┬────────┬────────┬────────┬───────────┬──────────┬─────────┐
│ Stat    │ 2.5%   │ 50%    │ 97.5%  │ 99%    │ Avg       │ Stdev    │ Max     │
├─────────┼────────┼────────┼────────┼────────┼───────────┼──────────┼─────────┤
│ Latency │ 215 ms │ 238 ms │ 282 ms │ 290 ms │ 243.06 ms │ 37.25 ms │ 1102 ms │
└─────────┴────────┴────────┴────────┴────────┴───────────┴──────────┴─────────┘
┌───────────┬─────────┬─────────┬─────────┬─────────┬─────────┬─────────┬─────────┐
│ Stat      │ 1%      │ 2.5%    │ 50%     │ 97.5%   │ Avg     │ Stdev   │ Min     │
├───────────┼─────────┼─────────┼─────────┼─────────┼─────────┼─────────┼─────────┤
│ Req/Sec   │ 186,623 │ 186,623 │ 250,111 │ 250,111 │ 238,144 │ 22,354  │ 186,595 │
├───────────┼─────────┼─────────┼─────────┼─────────┼─────────┼─────────┼─────────┤
│ Bytes/Sec │ 30.8 MB │ 30.8 MB │ 41.3 MB │ 41.3 MB │ 39.3 MB │ 3.68 MB │ 30.8 MB │
└───────────┴─────────┴─────────┴─────────┴─────────┴─────────┴─────────┴─────────┘

Req/Bytes counts sampled once per second.
# of samples: 18

4336k requests in 21.07s, 707 MB read



# benchmark2
autocannon -c 1000 -d 20 -p 200 http://localhost:8080/ping
Running 20s test @ http://localhost:8080/ping
1000 connections with 200 pipelining factor

running [=============       ] 65%
┌─────────┬────────┬────────┬─────────┬─────────┬───────────┬───────────┬─────────┐
│ Stat    │ 2.5%   │ 50%    │ 97.5%   │ 99%     │ Avg       │ Stdev     │ Max     │
├─────────┼────────┼────────┼─────────┼─────────┼───────────┼───────────┼─────────┤
│ Latency │ 693 ms │ 935 ms │ 1053 ms │ 1808 ms │ 951.09 ms │ 147.13 ms │ 2070 ms │
└─────────┴────────┴────────┴─────────┴─────────┴───────────┴───────────┴─────────┘
┌───────────┬─────────┬─────────┬─────────┬─────────┬────────────┬───────────┬─────────┐
│ Stat      │ 1%      │ 2.5%    │ 50%     │ 97.5%   │ Avg        │ Stdev     │ Min     │
├───────────┼─────────┼─────────┼─────────┼─────────┼────────────┼───────────┼─────────┤
│ Req/Sec   │ 94,207  │ 94,207  │ 400,127 │ 400,127 │ 361,070.77 │ 93,573.13 │ 94,161  │
├───────────┼─────────┼─────────┼─────────┼─────────┼────────────┼───────────┼─────────┤
│ Bytes/Sec │ 15.5 MB │ 15.5 MB │ 66 MB   │ 66 MB   │ 59.6 MB    │ 15.4 MB   │ 15.5 MB │
└───────────┴─────────┴─────────┴─────────┴─────────┴────────────┴───────────┴─────────┘

Req/Bytes counts sampled once per second.
# of samples: 13

4894k requests in 22.95s, 775 MB read


# resource using
|  env   | memory  | cpu  |
|  ----  | ----  | ----  |
| general  | 56m | 0 |
| stress test  | 57m | 230% |

