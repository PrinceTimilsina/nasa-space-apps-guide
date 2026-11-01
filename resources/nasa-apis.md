# NASA APIs for Beginners

An API (Application Programming Interface) lets software request information from another service, often in a structured format such as JSON.

## Start here

- [NASA API Portal](https://api.nasa.gov/)
- [NASA Image and Video Library API](https://images.nasa.gov/docs/images.nasa.gov_api_docs.pdf)
- [NASA Earthdata](https://www.earthdata.nasa.gov/)
- [NASA Open Data Portal](https://data.nasa.gov/)

The NASA API portal does not list every NASA data service. Some projects use APIs documented by individual NASA missions, science archives, or partner agencies.

## Typical workflow

1. Find an API relevant to your question.
2. Read its official documentation.
3. Check whether it requires an API key or account.
4. Review rate limits, parameters, response formats, and attribution guidance.
5. Test one simple request.
6. Inspect the response and handle errors.
7. Store secrets securely if a key is required.

## API keys and security

- Never commit a real API key to a public GitHub repository.
- Put secrets in environment variables or a local `.env` file.
- Add `.env` to `.gitignore`.
- Provide a `.env.example` with placeholder names only.
- If a key is accidentally published, revoke or rotate it using the provider's instructions.

## Example: requesting JSON with JavaScript

This is a generic browser example. Replace the URL with an endpoint from the API's current official documentation.

```js
async function loadData() {
  const response = await fetch("https://example.com/api/data");

  if (!response.ok) {
    throw new Error(`Request failed: ${response.status}`);
  }

  const data = await response.json();
  console.log(data);
}

loadData().catch(console.error);
```

Do not copy example URLs as if they were working NASA endpoints. Always use the endpoint and parameters shown in the relevant official documentation.

## API status changes

APIs can be updated, replaced, rate-limited, or retired. For example, the NASA API portal currently warns about changes to its APOD service and archived Earth and Mars Rover APIs. Check the portal before starting a project and again before presenting it.

Portal: https://api.nasa.gov/
