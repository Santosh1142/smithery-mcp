# Smithery MCP (Model Context Protocol)

A toolkit for building and connecting Model Context Protocol (MCP) servers to extend AI assistant capabilities.

## What is MCP?

The Model Context Protocol (MCP) is a standardized way to extend AI assistant capabilities by connecting to external servers that provide additional tools and resources. MCP servers can:

- Provide custom tools that the AI can use to perform specific actions
- Expose resources that the AI can access for additional context
- Connect to external APIs, databases, and services
- Enable domain-specific functionality

## Features

- **Easy Server Creation**: Build custom MCP servers with minimal boilerplate
- **Tool Definition**: Define custom tools with JSON schema validation
- **Resource Exposure**: Make resources available to AI assistants
- **Secure Communication**: Implement authentication and secure data exchange
- **Extensible Architecture**: Add new capabilities through a plugin system

## Getting Started

### Installation

```bash
npm install @smithery/mcp-core
```

### Creating a Basic MCP Server

```javascript
const { createMcpServer } = require('@smithery/mcp-core');

// Create a new MCP server
const server = createMcpServer({
  name: 'example-server',
  description: 'An example MCP server'
});

// Define a tool
server.defineTool({
  name: 'greet',
  description: 'Greet a person by name',
  inputSchema: {
    type: 'object',
    properties: {
      name: { type: 'string', description: 'The name of the person to greet' }
    },
    required: ['name']
  },
  execute: async ({ name }) => {
    return `Hello, ${name}!`;
  }
});

// Start the server
server.listen(3000, () => {
  console.log('MCP server running on port 3000');
});
```

## Documentation

For full documentation, visit [docs.smithery.dev](https://docs.smithery.dev).

## Examples

Check the `examples/` directory for more usage examples:

- Weather API integration
- Database access
- File system operations
- Custom API integrations

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT
