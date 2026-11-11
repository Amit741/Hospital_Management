# Hospital Management System

A containerized hospital management application built using Flask, PostgreSQL, Docker, Amazon S3, and Terraform.

## Features

- Patient registration and management
- Doctor and department management
- Appointment booking and status management
- Patient document storage in private Amazon S3
- PostgreSQL relational database
- Docker Compose deployment
- Terraform infrastructure provisioning
- Power BI reporting integration

## Architecture

Browser -> Flask (Gunicorn) -> PostgreSQL
                         |
                         -> Amazon S3

## Technology Stack

- Python and Flask
- PostgreSQL
- Docker and Docker Compose
- AWS EC2 and S3
- Terraform
- Power BI Desktop

## Run locally or on an EC2 instance

1. Install Docker and Docker Compose.
2. Copy `.env.example` to `.env`.
3. Set the database password, Flask secret, S3 bucket, and AWS region.
4. Configure AWS credentials or an EC2 IAM role with restricted S3 access.
5. Run:

   `docker compose up -d --build`

6. Open `http://localhost:5000`.

## Database

PostgreSQL runs as a Docker service. The database initialization SQL is in `database/init.sql`.

## AWS Infrastructure

Terraform configuration is in the `terraform/` directory.

Run `terraform init`, `terraform validate`, `terraform plan`, and `terraform apply` from that directory.

## Power BI

Power BI Desktop can connect to PostgreSQL for reporting on patients, doctors, departments, and appointments.

## Security

- Do not commit `.env`, Terraform state files, AWS credentials, or private keys.
- Keep the S3 bucket private.
- Configure authentication and authorization before using real patient data.
- Use synthetic data for demonstrations.
