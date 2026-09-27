---
name: nextjs-app-router
description: Personal best practices for building Next.js App Router applications.
---

# Next.js App Router

## Recommended directory structure

Follow these guidelines for directories under the `app/` directory:

- Colocate code specific to a directory under that directory. Code that is common to multiple parts of the application can go in a top level `components/` or `lib/` folder.
- Put shared components under `/_components/`
- Put server actions in `/_actions/`
- Put server side data fetching code in `/_data/`

For example, if the page is `app/dashboard`, put shared components in `app/dashboard/_components/`.

Generally code that doesn't require any user input should be server components. The `use client` boundary should be pushed down the component tree to just the components that need client input.

## Suspense + Dynamic I/O

Any use of dynamic I/O, including `await` and `useSearchParams` should be wrapped in a `Suspense` boundary.

A common way to do this is to export a wrapper component that contains the component and the inner component contains the Dynamic I/O. For example:

```
async function DynamicMyComponent(props) {
    const data = await getData();
    return <div>...</div>;
}

export async function MyComponent(props) {
    return (
        <Suspense fallback={<MyComponentSkeleton />}>
          <DynamicMyComponent ...props />
        </Suspense>
    )
}
```

This should usually not happen in `page.tsx` or `layout.tsx` files since they will cause
the entire page to be in loading state until the promise is resolved, but if it is necessary then the directory can use a `loading.tsx` to show a loading state.

## Deferred promises

Promises, such as data fetch calls, should be pushed down to the lowest component that needs that data. If the data needs to be shared or kicked off early for performance, it can be started in the root `page.tsx` file but `await` should not be called on the promise there and the Promise should be passed down to child components until it is needed. This is important for performance as blocking on async code will delay the rendering of the component and all child components.

## Forms

A benefit of the App Router is that client side forms can automatically keep the URL state up to date.

The Next.js Form component should be used: https://nextjs.org/docs/app/api-reference/components/form.

Client components should optimistically update the input components. When the URL updates, the client component should be updated with the new search params. 

A Suspense may need a `key` with the serialized search params to trigger it going back into the loading state.

## References

- https://nextjs.org/docs/app/getting-started/fetching-data
- https://www.robinwieruch.de/next-server-actions-fetch-data/
- https://www.robinwieruch.de/next-search-params/
- https://buildui.com/posts/instant-search-params-with-react-server-components