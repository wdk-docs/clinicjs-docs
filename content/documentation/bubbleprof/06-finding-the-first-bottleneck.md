---
title: "找到第一个瓶颈"
priority: 6

# SEO
metaData:
  titleParts:
    - Finding the first bottleneck
    - Bubbleprof
    - Documentation
---

# 找到第一个瓶颈

![First screen](03-A.png)

A few things we notice by looking at this first diagram are:

1. A lot of time is spent inside the mongodb bubble on the left.
1. Similar amount of time is spent querying in the query bubble at the bottom.
1. The timeline is sparse indicating low throughput.

This seems like a throughput problem, likely related to mongodb.

If we investigate the database setup we notice that the server is using a
collection that doesn't contain an index.

This means the database has to iterate all the data every time to answer our query,
which creates a lot of database latency.

We can reduce this overhead by adding an index on the properties we use.

---

## 下一个

[Improving our latency](/documentation/bubbleprof/07-improving-our-latency/)
