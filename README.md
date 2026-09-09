# API Gateway Frontend

Front door for Jamuna Bank PLC channel apps. The browser calls one origin. The gateway forwards to the middleware that owns the job: onboarding, payments, identity, or documents.

This repository is a sanitized public sample.

## What I owned

I built the dashboard and the routing layer the channels see. A channel team should not collect base URLs for NID, OCR, payments, and core. They call the gateway. Downstream hosts stay on the server.

## Technologies

- React dashboard for the gateway
- Server-side route table
- Request identity forwarded to the downstream service
- Secrets and partner hosts not forwarded to the browser

## Features

- One entry for several middleware services
- A dashboard so operations can see which route is live
- Failure from one downstream service returns an error, not that service's host
- Correlation of the caller so the owning API can audit the source app

## Why a gateway

The bank has many small APIs. If each React app stored those hosts, a network change would be a front-end release, and a leaked bundle would name internal services. The gateway is the only public name.

Portfolio: https://rafiimam.github.io/rafi_portfolio/
