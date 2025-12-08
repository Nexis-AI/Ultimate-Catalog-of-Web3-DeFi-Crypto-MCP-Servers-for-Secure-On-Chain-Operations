# Contributing to the Registry

We welcome community contributions! If you have built an MCP server relevant to Web3, DeFi, or Crypto, please add it here.

## How to Add a Server

1. **Fork this Repository**
2. **Edit `registry.json`**
   Add your server object to the `servers` array. Use the following format:

   ```json
   {
     "name": "your-server-name",
     "description": "Brief description of what it does.",
     "vendor": "YourName or Org",
     "source": {
       "type": "docker", // or "git"
       "location": "image:tag" // or repo URL
     },
     "tags": ["Category1", "Category2"],
     "env": {
       "API_KEY": {
         "description": "Required for XYZ API",
         "required": true
       }
     }
   }
   ```

3. **Validate**
   Ensure your JSON is valid and conforms to `registry.schema.json`.

4. **Submit a Pull Request**
   Open a PR with the title `Add [Server Name]`.

## Guidelines

- **Quality**: Ensure your server implements at least one functional tool or resource.
- **Security**: Do not hardcode secrets. Use environment variables.
- **Docker**: We prefer Docker-based distributions for security and portability.
