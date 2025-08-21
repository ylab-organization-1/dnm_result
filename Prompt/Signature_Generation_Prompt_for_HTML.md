# Task: Generate {service_name} Detection Regex from HTML Files

## Objective
Analyze the provided HTML files and create a regular expression pattern to detect {service_name} service dependencies.

## Reference Manual for {service_name}
{manual_content}

---

### Market {i}: {market['name']} (Complete HTML)
```html
{market['html_content']}
```

---

## Analysis Requirements

Based on ALL the HTML content provided above, create a regex pattern that can detect {service_name} usage by identifying:
- Script sources and inline JavaScript
- CSS classes and IDs 
- Data attributes
- Form actions and inputs
- Comments mentioning the service
- Meta tags
- Any URLs or domains
- Function calls and variable names
- Service-specific HTML structures

## Output Format

Provide ONLY the final regex pattern on a single line without any explanation or formatting.
The pattern should be ready to use directly in code.
Use alternation (|) to match any of the indicators.

Example format (do not include backticks or quotes):
pattern1|pattern2|pattern3