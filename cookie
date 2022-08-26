In Server side

```javascript
//code to set cookie from the server side
import cookie from "cookie";

export default function handler(req, res) {
  if (req.method === "POST") {
    res.setHeader(
      "Set-Cookie",
      cookie.serialize("token", req.body.token, {
        httpOnly: true,
        secure: process.env.NODE_ENV !== "development",
        maxAge: 60 * 60 * 24 * 7, // 1 week
        sameSite: "strict",
        path: "/",
      })
    );    
  }
  return res.status(200).json({ success: true });
}
```

In client side

```js
export function getServerSideProps({ req, res }) {
  return { props: { token: req.cookies.token || "NONE" } };
}
```
