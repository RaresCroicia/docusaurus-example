---
sidebar_position: 1
---

# Ask Service
Responds only to "${URL}/api/" requests.Example of correct request:

     https://olympics.lsacbucuresti.ro/api/auth.getUser


The ask service splits the request as follow:
- request = "auth.getUser"
- module = "auth"
- method = "getUser"
- params_list = "[]" (optional array of parameters, empty in this case)

And calls modules[module][method](req, res).

### How to add routes?

You need to follow the ask service pattern:
1. Create a file ${route}.js in routes/ where you export all the functions associated with your route.
2. Export in routes/modules.js your route file.
3. Create in modules/ a folder that contains all files with functions associated with your route.