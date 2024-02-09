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

Sample Use cases :
Hoverfly is designed to cater for two high-level use cases.

Capturing real HTTP(S) traffic between an application and an external service for re-use in testing or development.
If the external service you want to simulate already exists, you can put Hoverfly in between your client application and the external service. Hoverfly can then capture every request from the client application and every matching response from the external service (capture mode).

These request/response pairs are persisted in Hoverfly, and can be exported to a service data JSON file. The service data file can be stored elsewhere (a Git repository, for example), modified as required, then imported back into Hoverfly (or into another Hoverfly instance).

Hoverfly can then act as a "surrogate" for the external service, returning a matched response for every request it received (simulate mode).

This is useful if you want to create a portable, self-contained version of an external service to develop and test against.

This could allow you to get around the problem of rate-limiting (which can be frustrating when working with a public API).

You can write Hoverfly extensions to manipulate the data in pre-recorded responses, or to simulate network latency.

You could work while offline, or you could speed up your workflow by replacing a slow dependency with a fast Hoverfly "surrogate".

More information on these use-cases is available here:

Creating fast versions of slow dependencies
Virtualizing the Meetup API
Creating simulated services for use in a testing or development.
In some cases, the external service you want to simulate might not exist yet.

You can create service simulations by writing service data JSON files. This is in line with the principle of design by contract development.

Service data files can be created by each developer, then stored in a Git repository. Other developers can then import the service data directly from the repository URL, providing them with a Hoverfly "surrogate" to work with.

Instead of writing a service data file, you could write a "middleware" script for Hoverfly that generates a response "on the fly", based on the request it receives (synthesize mode).


