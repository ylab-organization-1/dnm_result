# Task: Generate {service_name} Detection Regex from HAR Files

## Objective
Analyze the provided HAR (HTTP Archive) files and create a regular expression pattern to detect {service_name} service dependencies.

## Reference Manual for {service_name}
{manual_content}

---

### Market {i}: {market['name']} (Complete HAR)
```json
{market['har_content']}
```

---

## Analysis Requirements

Based on ALL the HAR content provided above, create a regex pattern that can detect {service_name} usage by identifying:
- Request URLs and domains
- Request/response headers
- Cookies
- POST data and parameters
- WebSocket connections
- API endpoints
- Authentication tokens or keys
- Query parameters
- Response content patterns

## Output Format

Provide ONLY the final regex pattern on a single line without any explanation or formatting.
The pattern should be ready to use directly in code.
Use alternation (|) to match any of the indicators.

Example format (do not include backticks or quotes):
pattern1|pattern2|pattern3