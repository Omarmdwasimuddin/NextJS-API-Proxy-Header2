## NextJS API---> Working With Response Header In Proxy

### Set value in header
![](https://imgur.com/tFLmod3.png)

```bash
import { NextRequest, NextResponse } from "next/server";


export function proxy(request: NextRequest) {
    if (request.nextUrl.pathname.startsWith('/api')) {
        
        const res = NextResponse.next();
        res.headers.set('API_KEY','ex-123-xyz-abc')

        return res;
        
    }
}
```

```bash
import { NextResponse, NextRequest } from "next/server";


export async function GET(request:NextRequest) {


    return NextResponse.json(
        {status: "success", message: "ok"},
        {status: 200}
    )
}
```
---

### Set multiple value in header
![](https://imgur.com/egn07TR.png)

```bash
import { NextRequest, NextResponse } from "next/server";


export function proxy(request: NextRequest) {
    if (request.nextUrl.pathname.startsWith('/api')) {
        
        const res = NextResponse.next();
        res.headers.set('API_KEY','ex-123-xyz-abc');
        res.headers.set('API_KEY2','ex-123-xyz-abc-0102');
        return res;
        
    }
}
```

```bash
import { NextResponse, NextRequest } from "next/server";


export async function GET(request:NextRequest) {


    return NextResponse.json(
        {status: "success", message: "ok"},
        {status: 200}
    )
}
```
