# `supabase-js-without-realtime-js`

An isomorphic JavaScript client for Supabase.

- **Documentation:** https://supabase.com/docs/client/supabase-client
- TypeDoc: https://supabase.github.io/supabase-js

## Usage

First of all, you need to install the library:

```sh
npm install supabase-js-without-realtime-js
```

Then you're able to import the library and establish the connection with the database:

```js
import { createClient } from 'supabase-js-without-realtime-js'

// Create a single supabase client for interacting with your database
const supabase = createClient('https://xyzcompany.supabase.co', 'public-anon-key')
```

### Custom `fetch` implementation

`supabase-js` uses the [`cross-fetch`](https://www.npmjs.com/package/cross-fetch) library to make HTTP requests, but an alternative `fetch` implementation can be provided as an option. This is most useful in environments where `cross-fetch` is not compatible, for instance Cloudflare Workers:

```js
import { createClient } from 'supabase-js-without-realtime-js'

// Provide a custom `fetch` implementation as an option
const supabase = createClient('https://xyzcompany.supabase.co', 'public-anon-key', {
  fetch: (...args) => fetch(...args),
})
```
