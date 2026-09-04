# CMPE 273 – Week 1 Lab 1

This project demonstrates a simple distributed system using two independent Python Flask services that communicate over HTTP.

## How to Run Locally

### Service A

Open a terminal and run:

cd python-http/service-a
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python app.py

### Service B
Open a terminal and run:

cd python-http/service-b
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python app.py

## Success Proof – Service A

Service A is running on port `8080`. The `/health` and `/echo` endpoints return `200 OK`.

![Service A Success](docs/service-a-success.png)

## Success Proof — Service B Calling Service A

Service B is running on port `8081` and successfully communicates with Service A.

![Service B Success](docs/service-b-success.png)

## Failure Proof — Service A Stopped

Service A was stopped while Service B remained running. When Service B attempts to call Service A, it returns `503 Service Unavailable`.

![Failure Proof](docs/service-a-failure.png)

What Makes This Distributed?

This application is distributed because Service A and Service B run as separate processes and communicate with each other over HTTP. Each service operates independently, and one service can fail while the other continues running, demonstrating independent failure in a distributed system.
