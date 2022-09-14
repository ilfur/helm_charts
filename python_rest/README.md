<!--- app-name: Apache Kafka -->

# Simple Python REST service

Sample container image written in Python, using "flask" Web Server.
After deployment, check for the created Istio Gateway to see the virtual host name.
The REST service accepts the URI "/vote/<some-name>" to simulate some kind of voting mechanism.
Python and the flask server also allow for creating Metrics to be exported to Prometheus.

All calls to the REST service are logged or scraped by both fluentd/opensearch and prometheus.
This wiring is automated by using Verrazzano's OAM syntax.

There is a Python Grafana Dashboard available that can view the results of the voting,
OpenSearch Dashboards can visualize all calls to the REST service due to its output logs.

## Installation

When installing the chart, please specify the number of containers You would like to have up and running.
Verrazzano's OAM is using a ScalerTrait to start the requested number of containers, and Istio will do the load balancing between them.
The Istio configuration is also automatically created through Verrazzano's OAM logic / OAM operator.

## Copyright

Copyright &copy; 2022 Oracle and/or its affiliates.
