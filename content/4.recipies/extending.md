---
title: Extending Auth plugin
---

If you have plugins that need to access `$auth`, you can use `auth.plugins` option.

```ts{}[nuxt.config.ts]
{
    modules: [
        '@nuxt-alt/auth'
    ],
    auth: {
        plugins: [
            '~/auth-plugins/auth.ts' 
        ]
    }
}
```

```ts{}[auth-plugins/auth.ts]
export default defineNuxtPlugin(({ $auth }) => {
    if (!$auth.loggedIn) {
        return
    }

    const username = $auth.user.username
})
```