# hoverfly
Hoverfly is a lightweight, open source service virtualization tool. Using Hoverfly, you can virtualize your application dependencies to create a self-contained development or test environment.

Hoverfly is a proxy written in Go. It can capture HTTP(s) traffic between an application under test and external services, and then replace the external services. It can also generate synthetic responses on the fly.

1) Capture traffic between a client application and an external service
2) Use captured traffic to create a simulated service
3) Export and import captured traffic
4) Extend and customize with any programming language
5) Dynamically create responses to requests on the fly
6) Manipulate data in requests and responses
7) Simulate network latency, random failures, rate limits...
