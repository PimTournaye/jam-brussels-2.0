# sv

Everything you need to build a Svelte project, powered by [`sv`](https://github.com/sveltejs/cli).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npx sv create

# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://svelte.dev/docs/kit/adapters) for your target environment.

## Setting up Supabase

To set up Supabase in your project, follow these steps:

1. Sign up for a free account at [Supabase](https://supabase.io/).
2. Create a new project in the Supabase dashboard.
3. Obtain your Supabase URL and Anon Key from the project settings.

### Environment Variables

Create a `.env` file in the root of your project and add the following environment variables:

```
SUPABASE_URL=your-supabase-url
SUPABASE_ANON_KEY=your-supabase-anon-key
```

Replace `your-supabase-url` and `your-supabase-anon-key` with the values obtained from the Supabase dashboard.

### Supabase Client

The Supabase client is configured in `src/lib/supabaseClient.ts`. You can use this client to interact with your Supabase database.

```typescript
import { createClient } from '@supabase/supabase-js';

const SUPABASE_URL = process.env.SUPABASE_URL;
const SUPABASE_ANON_KEY = process.env.SUPABASE_ANON_KEY;

const supabase = createClient(SUPABASE_URL, SUPABASE_ANON_KEY);

export { supabase };
```
