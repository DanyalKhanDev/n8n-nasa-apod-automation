# NASA APOD Automation using n8n

## Project Overview

An automated workflow built using **n8n** that retrieves astronomy data from NASA's Astronomy Picture of the Day (APOD) API, processes API responses using conditional logic, and sends structured results to PostBin.

## Tech Stack

- n8n (self-hosted using Docker)
- NASA REST API
- HTTP Request
- JSON
- Conditional Workflow Logic
- PostBin

## Workflow Architecture

Schedule Trigger → HTTP Request (NASA APOD) → IF Node → PostBin

## How It Works

1. **Schedule Trigger:** Runs the workflow automatically on a weekly schedule.
2. **HTTP Request:** Retrieves astronomy data from NASA's APOD API.
3. **IF Node:** Checks whether the returned media type is an image.
4. **Conditional Routing:** Routes image and non-image responses through separate branches.
5. **PostBin:** Receives the processed information for testing and verification.

## API Endpoint

`GET https://api.nasa.gov/planetary/apod`

Authentication is provided using a NASA API key.

## Running Locally

1. Install Docker and run a local n8n instance.
2. Import `nasa-apod-workflow.json` into n8n.
3. Configure your own NASA API key.
4. Configure the PostBin destination.
5. Execute the workflow and verify the output.
6. Publish the workflow to enable scheduled execution.

## Skills Demonstrated

- REST API integration
- Workflow orchestration
- JSON data processing
- Conditional automation
- Docker-based self-hosting
- API error troubleshooting

## Workflow Screenshot

![NASA APOD n8n Workflow](workflow.png)

## Reference

Based on the [official n8n beginner workflow tutorial](https://docs.n8n.io/build-your-first-workflow/), adapted to use the NASA APOD API instead of the DONKI Solar Flare API.
