# Sign in with Github

https://backstage.io/docs/auth/#adding-the-provider-to-the-sign-in-page

### In app-config.yaml oe app-config.local.yaml add resolvers


```
  signIn:
    resolvers:
    - resolver: usernameMatchingUserEntityName
    - resolver: emailMatchingUserEntityProfileEmail
    - resolver: emailLocalPartMatchingUserEntityName
```

### Add github library in packages/backend/src/index.ts

```
backend.add(import('@backstage/plugin-auth-backend-module-github-provider'));
```

### Add users or groups in org.yaml

```
apiVersion: backstage.io/v1alpha1
kind: User
spec:
  memberOf: [owners]
```