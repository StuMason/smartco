# Architectural Decision Record 001 - Serverless Laravel

## Context

SmartCo has built an internal application platform using AWS to help teams within the organisation quickly build and deploy applications.

At the moment there are only two types of application, a Laravel application which uses ECS Fargate and a Serverless Python application which uses AWS SAM (Python 3.9, Lambda, APIGateway etc).

As a result of this, all teams are already very familiar with tools like SAM, Lambda, API Gateway, Cloudfront and ECS Fargate, as well as Laravel, PHP and Python.

The teams are also used to using Github Actions as their CI/CD tool.

### Laravel + Lambda

As a team, we would like to experiment with a Laravel application which uses API Gateway + Lambda, rather than ECS Fargate (Docker) to process client requests. _This would be very similar to Laravels “Vapour” offering._

What we are looking for here is a clear explanation from you on how you would approach this, and what the benefits and drawbacks are, as well as any other considerations you would make.

Diagrams, code snippets (pseudo code fine) and the reasoning behind each decision (along with its consequences) are needed to help us decide if we should proceed with this experiment further.

A VPC, Subnets, NAT Gateway, Route Tables, Security Groups, IAM Roles, etc. have all already been created for you. You can use these as you see fit.

Some questions that have already been asked internally are:

* Along with API Gateway and Lambda, what other resources will we need?
* How will we use PHP8.1 as a runtime in Lambda?
* What would the request/response flow look like?
* Would this be a cost effective solution?
* Would this solution scale effectively with high and low traffic applications?
* Would this solution be possible using AWS SAM?
* How would we deploy this application?
* How would we inspect logs?
* What new technologies would the team need to familiarise themselves with, if any?

### Bonus Descisions

* What would the CI/CD pipeline look like?
* Would an SQS/Queue worker be possible here?
* Would we be able to integrate redis cache?
* What store would we use?
* How could we prevent (for example) 3000 Lambda invocations from maxing out our connections in RDS?
* How would we handle database migrations?
* What impact would this have on security vs. using Fargate?

## Decision

(to be filled in by you)
