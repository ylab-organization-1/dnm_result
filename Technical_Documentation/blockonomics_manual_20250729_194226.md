# Blockonomics Service Detection Manual

## Service Overview

Blockonomics is a decentralized Bitcoin payment gateway that allows merchants to accept cryptocurrency payments directly to their wallets without intermediaries.

## Known URLs

- Main website: https://www.blockonomics.co
- Developer documentation: https://developers.blockonomics.co
- API reference: https://developers.blockonomics.co/reference/getting-started
- Integration guide: https://www.blockonomics.co/views/api.html

---

# Blockonomics Dependency Detection Manual

This manual provides a comprehensive guide for detecting dependencies on the Blockonomics service in web applications. Blockonomics is a Bitcoin payment processing service that offers real-time updates via WebSocket connections and supports multiple cryptocurrencies. This guide outlines unique identifiers, authentication patterns, HTTP headers, JavaScript patterns, CSS classes, WebSocket connection patterns, error response patterns, and example detection signatures.

## 1. Unique Identifiers

### URLs
- Main Website: `https://www.blockonomics.co`
- Developer Documentation: `https://developers.blockonomics.co`
- API Reference: `https://developers.blockonomics.co/reference/getting-started`
- Integration Guide: `https://www.blockonomics.co/views/api.html`

### Common API Endpoints
- `/api/new_address`
- `/api/price`
- `/api/balance`
- `/api/invoice`
- `/api/transaction`

### Function Names
- `createNewAddress()`
- `getPrice()`
- `getBalance()`
- `createInvoice()`
- `getTransactionDetails()`

## 2. Authentication Patterns

### API Key Authentication
- API keys are typically included in the request headers or as query parameters.
- Example Header: `Authorization: Bearer <API_KEY>`
- Example Query Parameter: `?api_key=<API_KEY>`

## 3. Common HTTP Headers

- `Content-Type: application/json`
- `Accept: application/json`
- `Authorization: Bearer <API_KEY>`
- `User-Agent: Blockonomics-Client/<version>`

## 4. JavaScript Patterns and Variable Names

### Common JavaScript Patterns
- Variable for API key: `var apiKey = '<API_KEY>';`
- Function to initialize WebSocket: `function initWebSocket()`
- Function to handle payment processing: `function processPayment()`

### Variable Names
- `blockonomicsApiKey`
- `blockonomicsSocket`
- `paymentData`
- `transactionId`

## 5. CSS Classes and HTML Identifiers

### CSS Classes
- `.blockonomics-button`
- `.blockonomics-invoice`
- `.blockonomics-payment-status`

### HTML Identifiers
- `#blockonomics-payment-form`
- `#blockonomics-invoice-id`
- `#blockonomics-status`

## 6. WebSocket Connection Patterns

- WebSocket URL: `wss://www.blockonomics.co/websocket`
- Connection Initialization: `new WebSocket('wss://www.blockonomics.co/websocket');`
- Event Listeners: 
  - `socket.onopen`
  - `socket.onmessage`
  - `socket.onclose`
  - `socket.onerror`

## 7. Error Response Patterns

### Common Error Messages
- `{"error": "Invalid API Key"}`
- `{"error": "Address not found"}`
- `{"error": "Transaction failed"}`
- `{"error": "Service unavailable"}`

### HTTP Status Codes
- `401 Unauthorized`
- `404 Not Found`
- `500 Internal Server Error`

## 8. Example Detection Signatures

### Signature for API Key Usage
```plaintext
rule BlockonomicsAPIKeyUsage
{
    strings:
        $api_key_header = "Authorization: Bearer"
        $api_key_param = "?api_key="
    condition:
        any of them
}
```

### Signature for WebSocket Connection
```plaintext
rule BlockonomicsWebSocketConnection
{
    strings:
        $websocket_url = "wss://www.blockonomics.co/websocket"
    condition:
        $websocket_url
}
```

### Signature for JavaScript Patterns
```plaintext
rule BlockonomicsJavaScriptPatterns
{
    strings:
        $init_websocket = "function initWebSocket()"
        $process_payment = "function processPayment()"
    condition:
        any of them
}
```

### Signature for Error Responses
```plaintext
rule BlockonomicsErrorResponses
{
    strings:
        $invalid_api_key = "Invalid API Key"
        $address_not_found = "Address not found"
        $transaction_failed = "Transaction failed"
    condition:
        any of them
}
```

This manual should serve as a comprehensive guide for detecting Blockonomics dependencies within web applications, enabling developers and security professionals to identify and manage these integrations effectively.

---

## Additional Notes

This manual was generated using OpenAI GPT-4o based on known Blockonomics documentation URLs and service characteristics. It should be used as a reference for creating detection signatures for Blockonomics service dependencies in web applications.

## Example Combined Detection Regex

```regex
(?i)(blockonomics\.co|wss://[^/]*blockonomics|blockonomics[_-]?\w+|btc[_-]?address|/api/(new_address|price|tx_detail)|payment[_-]?received|blockonomics[_-]?webhook)
```
