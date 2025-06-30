# Weather MCP Server

A Model Context Protocol (MCP) server that provides weather information using the National Weather Service (NWS) API.

## Features

- **Weather Alerts**: Get active weather alerts for any US state
- **Weather Forecast**: Get detailed weather forecasts for specific coordinates
- **HTTP Streamable**: Runs as an HTTP server with MCP protocol support

## Tools

### `get_alerts(state: str)`
Retrieves active weather alerts for a US state.

**Parameters:**
- `state`: Two-letter US state code (e.g., "CA", "NY", "TX")

**Returns:**
Formatted weather alerts including event type, affected area, severity, description, and instructions.

### `get_forecast(latitude: float, longitude: float)`
Gets weather forecast for a specific location.

**Parameters:**
- `latitude`: Latitude coordinate
- `longitude`: Longitude coordinate

**Returns:**
5-period weather forecast with temperature, wind conditions, and detailed forecast information.

## Installation

1. Install dependencies:
```bash
uv sync
```

## Usage

Run the server:
```bash
python weather.py --port 8123
```

The server will start on `http://localhost:8123` by default.

## Dependencies

- `httpx`: HTTP client for API requests
- `mcp[cli]`: Model Context Protocol framework
- `uvicorn`: ASGI server for running the HTTP application

## API Source

This server uses the National Weather Service API (api.weather.gov) to provide weather data for locations within the United States.