# CI/CD Pipeline Documentation

## Overview

This project demonstrates a **3-job CI/CD pipeline** using **Jenkins**, **GitHub**, and an **AWS EC2 instance**.

The pipeline automates:

1. Pulling code changes from GitHub
2. Building and testing the application
3. Deploying the updated application to an EC2 instance

The goal of this pipeline is to ensure changes are tested and deployed reliably with minimal manual intervention.

---

# What is CI/CD?

## Continuous Integration (CI)

Continuous Integration is a development practice where developers frequently merge code changes into a shared repository.

Each change automatically triggers:

- Code validation
- Builds
- Automated tests
- Linting/checks

### Benefits of CI

- Detects bugs early
- Prevents broken code from reaching production
- Reduces “works on my machine” issues
- Improves collaboration between developers

---

## Continuous Delivery (CD)

Continuous Delivery automates the release process after CI is completed.

Applications are automatically prepared for deployment to testing or staging environments.

### Benefits of Continuous Delivery

- Software is always in a deployable state
- Faster release cycles
- Safer deployments through automation

---

## Continuous Deployment

Continuous Deployment extends Continuous Delivery by automatically deploying every successful change directly to production.

### Benefits of Continuous Deployment

- Rapid delivery of new features
- Reduced manual work
- Faster feedback from users

---

# Why We Used CI/CD

This project uses CI/CD to:

- Automate repetitive deployment tasks
- Improve deployment reliability
- Reduce human error
- Speed up testing and deployment
- Ensure application consistency

Using Jenkins pipelines also allows the team to quickly identify issues and redeploy fixes efficiently.

---

# CI/CD Pipeline Diagram

```text
Developer Pushes Code
          │
          ▼
      GitHub Repo
          │
          ▼
   GitHub Webhook
          │
          ▼
      Jenkins Job 1
   (Clone + Build/Test)
          │
          ▼
      Jenkins Job 2
    (Additional Checks)
          │
          ▼
      Jenkins Job 3
      (Deploy to EC2)
          │
          ▼
    AWS EC2 Application