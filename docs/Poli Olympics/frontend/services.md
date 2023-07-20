---
sidebar_position: 2
---

# Services

1. **Universal service**
   
   Service that send all our request from frontend to backend. We use ask for requests that send the user token and get for the others. Example of usage:
``` javascript
   await RequestService.ask("auth.login", { email: emailLogin, password: passwordLogin }, function (result, error) {
            if (error) {
                console.log(error);
                setemailError("Email sau parola incorecte");
                return;
            }
            localStorage.setItem("loginToken", result.data.token);
            window.location.href = '/'
        });
```
2. **Validator**
   
   General validator for any input where we can choose the restrictions applied. Example of usage:
``` javascript
   validator.validate(email, "email", [{ restrictionType: "required" }]);
```