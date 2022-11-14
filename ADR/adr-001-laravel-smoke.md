# Architectural Decision Record 001 - Serverless Laravel

## Context

SmartCo has built an internal application platform using AWS to help teams within the organisation quickly build and deploy applications.

At the moment there are only two types of application, a Laravel application which uses ECS Fargate and a Serverless Python application which uses AWS SAM.

This means that the teams are already very familiar with both SAM, Lambda, API Gateway, Cloudfront and ECS Fargate, as well as Laravel, PHP and Python.

The teams are also used to using Github Actions as their CI/CD tool.

At a team, we would like to experiment with a Laravel application which uses Lambda, rather than Docker (ECS Fargate) to process client requests.  This would be very similar to Laravels “Vapour” offering.

What we are looking for here is a series of decisions on how we could serve a default Laravel install over API Gateway and Lambda. Diagrams, code snippets (pseudo code fine) and the reasoning behind each decision (along with its consequences) are needed help us decide if we should proceed with this experiment further.

Some questions that have been asked internally are:

* Along with API Gateway and Lambda, what other resources will we need?
* How will we use PHP8.1 as a runtime in Lambda?
* What would the request/response flow look like?
* Would this be a cost effective solution?
* Would this solution scale effectively with high and low traffic applications?
* Would this solution be possible using AWS SAM?
* What assumptions have been made?
* Would an SQS/Queue worker be possible here?
* Would we be able to integrate redis cache?
* What store would we use?
* How could we prevent (for example) 3000 Lambda invocations from maxing out our connections in RDS?
* What new technologies would the team need to familiarise themselves with, if any?

## Decisions

...