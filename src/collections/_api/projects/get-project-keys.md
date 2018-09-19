---
{
  "authentication": "", 
  "description": "Return a list of client keys bound to a project.", 
  "example_request": "GET /api/0/projects/the-interstellar-jurisdiction/pump-station/keys/ HTTP/1.1\nHost: sentry.io\nAuthorization: Bearer {base64-encoded-key-here}", 
  "example_response": "HTTP/1.1\nContent-Length: 813\nX-XSS-Protection: 1; mode=block\nX-Content-Type-Options: nosniff\nContent-Language: en\nVary: Accept-Language, Cookie\nLink: <https://sentry.io/api/0/projects/the-interstellar-jurisdiction/pump-station/keys/?&cursor=4:0:1>; rel=\"previous\"; results=\"false\"; cursor=\"4:0:1\", <https://sentry.io/api/0/projects/the-interstellar-jurisdiction/pump-station/keys/?&cursor=4:100:0>; rel=\"next\"; results=\"false\"; cursor=\"4:100:0\"\nAllow: GET, POST, HEAD, OPTIONS\nX-Frame-Options: deny\nContent-Type: application/json\n\n[\n  {\n    \"dateCreated\": \"2018-09-10T20:36:48.349Z\", \n    \"dsn\": {\n      \"cdn\": \"https://sentry.io/js-sdk-loader/d49da1eb33654ee18a4fe0e8ebc73a75.min.js\", \n      \"csp\": \"https://sentry.io/api/2/csp-report/?sentry_key=d49da1eb33654ee18a4fe0e8ebc73a75\", \n      \"minidump\": \"https://sentry.io/api/2/minidump/?sentry_key=d49da1eb33654ee18a4fe0e8ebc73a75\", \n      \"public\": \"https://d49da1eb33654ee18a4fe0e8ebc73a75@sentry.io/2\", \n      \"secret\": \"https://d49da1eb33654ee18a4fe0e8ebc73a75:90fe9ff73b7144c6b98db08aeb53855a@sentry.io/2\", \n      \"security\": \"https://sentry.io/api/2/security/?sentry_key=d49da1eb33654ee18a4fe0e8ebc73a75\"\n    }, \n    \"id\": \"d49da1eb33654ee18a4fe0e8ebc73a75\", \n    \"isActive\": true, \n    \"label\": \"Fabulous Key\", \n    \"name\": \"Fabulous Key\", \n    \"projectId\": 2, \n    \"public\": \"d49da1eb33654ee18a4fe0e8ebc73a75\", \n    \"rateLimit\": null, \n    \"secret\": \"90fe9ff73b7144c6b98db08aeb53855a\"\n  }\n]", 
  "method": "GET", 
  "parameters": null, 
  "path_parameters": [
    {
      "description": "the slug of the organization the client keys belong to.", 
      "name": "organization_slug", 
      "type": "string"
    }, 
    {
      "description": "the slug of the project the client keys belong to.", 
      "name": "project_slug", 
      "type": "string"
    }
  ], 
  "query_parameters": null, 
  "sidebar_order": 12, 
  "title": "Projects"
}
---