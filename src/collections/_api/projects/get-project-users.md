---
{
  "authentication": "required", 
  "description": "Return a list of users seen within this project.", 
  "example_request": "", 
  "example_response": "", 
  "method": "GET", 
  "parameters": null, 
  "path_parameters": [
    {
      "description": "the slug of the organization.", 
      "name": "organization_slug", 
      "type": "string"
    }, 
    {
      "description": "the slug of the project.", 
      "name": "project_slug", 
      "type": "string"
    }, 
    {
      "description": "the tag key to look up.", 
      "name": "key", 
      "type": "string"
    }
  ], 
  "query_parameters": [
    {
      "description": "Limit results to users matching the given query. Prefixes should be used to suggest the field to match on: id, email, username, ip. For example, query=email:foo@example.com", 
      "name": "query", 
      "type": "string"
    }
  ], 
  "sidebar_order": 18, 
  "title": "Projects"
}
---