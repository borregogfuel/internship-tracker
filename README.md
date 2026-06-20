# Internship Tracker

A platform for tracking available internships, with a focus on early programs like Duolingo Thrive, Microsoft Explore, Google STEP, Meta University, and Uber STAR.

## Why

These programs often open applications earlier than most summer internships, and they frequently don't show up in public GitHub repos until someone submits a pull request. The goal is to find out the moment they open, before most other applicants.

This is a personal project — initial use is for myself, a 2nd-semester student looking for Summer 2027 opportunities. If it works well, I plan to open it up to the Tec de Monterrey community.

It's also my practice project as the incoming AWS Builder Group Campus Captain for my campus, so it's built entirely on AWS.

## How it works

Two data sources:

1. **GitHub repository** (SimplifyJobs/Summer2026-Internships) — a Lambda checks the README every hour and detects new internships or status changes.
2. **Direct company portals** — a second Lambda watches careers pages for specific companies not covered by the public repo.

When something new is detected, an email alert is sent.

## Stack

- Frontend: React + Vite + TypeScript + Tailwind
- Backend: AWS Lambda + API Gateway
- Database: DynamoDB
- Scheduling: EventBridge
- Notifications: SNS + SES
- Hosting: S3 + CloudFront
- Infrastructure: AWS CDK (TypeScript)
- CI/CD: GitHub Actions

Each AWS service is built manually in the console first to understand how it works, then recreated with CDK so it's versioned and reproducible.

## Status

Work in progress. Currently personal use only, no frontend yet.