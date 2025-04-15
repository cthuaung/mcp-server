# MCP Server Tutorial

This repository contains a simple MCP (Machine Conversation Protocol) server built with FastMCP. The server provides various mathematical operations as tools that can be used through the MCP protocol.

## Features

- Basic arithmetic operations (addition, subtraction, multiplication, division)
- Advanced mathematical functions:
  - Power
  - Square root
  - Cube root
  - Factorial
  - Logarithm
  - Trigonometric functions (sin, cos, tan)
  - Remainder
- Dynamic greeting resource

## Prerequisites

- Python 3.8 or higher
- FastMCP library

## Installation

1. Clone this repository
2. Create and activate a virtual environment:
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```
   uv install fastmcp
   ```

## Usage

### Running the Server

Run the server using:

```
python main.py
```

The server uses SSE (Server-Sent Events) transport by default, which allows you to connect using MCP Inspector.

### Connecting with MCP Inspector

1. Open MCP Inspector
2. Connect to the server URL (typically http://localhost:8000)
3. You can now interact with the mathematical tools and resources defined in the server

## Available Tools

- `add(a, b)`: Adds two numbers
- `subtract(a, b)`: Subtracts two numbers
- `multiply(a, b)`: Multiplies two numbers
- `divide(a, b)`: Divides two numbers
- `power(a, b)`: Calculates a raised to the power of b
- `sqrt(a)`: Calculates the square root of a number
- `cbrt(a)`: Calculates the cube root of a number
- `factorial(a)`: Calculates the factorial of a number
- `log(a)`: Calculates the natural logarithm of a number
- `remainder(a, b)`: Calculates the remainder when a is divided by b
- `sin(a)`: Calculates the sine of a number
- `cos(a)`: Calculates the cosine of a number
- `tan(a)`: Calculates the tangent of a number

## Available Resources

- `greeting://{name}`: Returns a personalized greeting for the given name

## Modifying the Server

You can add more tools and resources by following the pattern in `main.py`:

1. To add a new tool, use the `@mcp.tool()` decorator
2. To add a new resource, use the `@mcp.resource()` decorator

## Transport Options

FastMCP supports two transport protocols:
- `stdio`: Standard input/output (terminal-based)
- `sse`: Server-Sent Events (browser-based, compatible with MCP Inspector)

To change the transport protocol, modify the transport parameter in the `mcp.run()` call.
