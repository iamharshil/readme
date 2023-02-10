## better fetch

````js
wretch("/user")
    .get()
    .badRequest()
    .notFound()
    .unauthorized()
    .internalError()
    .then()

    ```
````

and

```js
fetch('/user')
    .then(res => {
        if (!res.ok) {
            case 400: break;
            case 401: break;
            case 404: break;
            case 500: break;
        }
        return res.json()
    })
    .catch((err) => {
        return err.message
    })
```
