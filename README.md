## NextJS API---> Working With Response Header In Proxy

###
![]()

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

```
---
