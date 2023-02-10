## better fetch

```js
wretch("/user")
  .get()
  .badRequest()
  .notFound()
  .unauthorized()
  .internalError()
  .then();
```

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

## URL SECURE

```js
const url = new URL("xyz.com");
url.searchParam.set("model", model);
url.searchParam.set("locale", locale);
url.searchParam.set("text", text);

const res = await fetch(url);
```

## Resolve 2 promise at once with both resolved

```js
async function getPageData() {
  const results = await Promise.allSettled([fetchUser(), fetchProduct()]);

  const [user, product] = handle(results);
}
```
