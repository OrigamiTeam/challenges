# QL-challenge

Welcome to this C++ and Python programming challenge.

We kindly ask you to read all steps below with atention in order to maximize the chances of success.

The task consists of developing a monitoring system that stores some telemtry data coming from devices. The implementation is comprised of two applications:

1) C++ script to collect network data
2) Python script that centralizes and serialize data

## Summary

- [Task](#task)
- [Assessment Criteria](#assessment-criteria)
- [Business Rules](#business-rules)
- [Requirements](#requirements)

## Task

The time available is 5 days to deliver the best software as possible guided by the importance of requirements described in the next section, respecting the 3Cs aspects of a software: consistency, completeness and correctness. Your challenge answser might be delivered through your personal repository account of your choice (GitHub, Gitlab, BitBucket, etc). Please send us the link when you finish.

## Assessment Criteria

The analysis of the code will consider the following facets in decrescent order of importance:

- Lack of bugs
- Responsiveness
- Objectivity (good semantics, readability)
- Decoupling
- Extensibility
- Manutenability
- Nice formatting

### Optionals

The following points are optionals, but we would appreaciate to see some of it:

- Automated tests
- Comments
- Exception handling
- Use of tooling (like lint and CI/CD)

## Business Rules

Our system is aimed to allow devices to send network metrics. As such, each **device** will run a lightweight C++ written program which publishs via MQTT to a specific topic.

Consider that in the first version of the system, each device will be emulated using Docker containers. Also another container will host the MQTT broker.

All data received should be serialized properly by the server side.

## Requirements

### Monitoring

A monitoring application written in C++ already compiled should be placed inside the container and monitor the following metrics using ICMP Ping.

- Packet loss
- Jitter
- Round trip time

The script must send 10 ICMP packets and retrieve their RTT information for analysis. Jitter could be calculated from the average time differences between sequential packets. The payload sent must match the following pattern. The device field must be filled with container hostname.

```json
{
    "packet_loss": float,
    "jitter": float,
    "min_rtt": float,
    "avg_rtt": float,
    "max_rtt": float,
    "device": string
}
```

Metrics should be published to the **/qlnetstats** topic, there is no need to subscribe to it as no data will be send to devices. The broker will run inside a container that exposes port 1883 but will share network with devices, so you can send to **mqtt://ql_broker:1883**

Remember to update **Dockerfile.device** with your program properly

### Backend

A backend application written in Python that subscribes to the metrics topic and stores data received in CSV or PostgreSQL (recommended). Run this application inside a docker container is encouraged but not required as you can point it to port 1883 at localhost. The table or CSV file should be as follows.

| id | device | packet_loss | jitter | min_rtt | avg_rtt | max_rtt | timestamp |
|----|--------|-------------|--------|---------|---------|---------|-----------|
|    |        |             |        |         |         |         |           |
