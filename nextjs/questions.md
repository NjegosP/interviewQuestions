# Next.js Interview Questions

---

## Questions

### 1. **Question**: Explain the difference between Server-Side Rendering (SSR) and Static Site Generation (SSG) in Next.js.

**Difficulty**: Medium  
**Category**: Rendering Strategies  
**Key Concepts**: SSR, SSG, getServerSideProps, getStaticProps, performance  
**Sample Answer**:

-   **Server-Side Rendering (SSR)**: Pages are rendered on the server at request time using `getServerSideProps`. Each request generates a fresh HTML page, ensuring up-to-date data. SSR is ideal for dynamic content that changes frequently or is user-specific (e.g., dashboards, authenticated pages).
-   **Static Site Generation (SSG)**: Pages are rendered at build time using `getStaticProps`. The generated HTML is reused for every request, resulting in fast load times and better scalability. SSG is best for content that doesn't change often (e.g., blogs, documentation). Incremental Static Regeneration (ISR) allows static pages to be updated after deployment.

**Comparison:**

-   SSR: Dynamic, slower per request, always up-to-date.
-   SSG: Static, fast, scalable, may need revalidation for updates.

**Connected Questions**: [#2: What is the App Router in Next.js 13+ and how does it differ from the Pages Router?], [#4: What is the difference between `getStaticProps` and `getStaticPaths`?]

**Further Reading**:

-   [Next.js Docs: Data Fetching](https://nextjs.org/docs/basic-features/data-fetching)
-   [Vercel Blog: Static vs Server Rendering](https://vercel.com/blog/static-vs-server-rendering)
-   [Learning Next.js by Vercel](https://nextjs.org/learn)

---

### 2. **Question**: What is the App Router in Next.js 13+ and how does it differ from the Pages Router?

**Difficulty**: Medium  
**Category**: Routing  
**Key Concepts**: App Router, file-based routing, layouts, server components  
**Sample Answer**:

-   **App Router** (introduced in Next.js 13) uses the `/app` directory for routing, supporting nested layouts, server components, and advanced data fetching. It enables more granular control over rendering and layout composition.
-   **Pages Router** uses the `/pages` directory, with each file corresponding to a route. It relies on traditional React components and data fetching methods like `getStaticProps` and `getServerSideProps`.

**Comparison:**

-   App Router: Modern, supports server components, layouts, streaming, and advanced routing.
-   Pages Router: Simpler, more mature, but less flexible for complex layouts.

**Connected Questions**: [#1: Explain the difference between Server-Side Rendering (SSR) and Static Site Generation (SSG) in Next.js.], [#3: Explain the concept of Server Components in Next.js 13+.]

**Further Reading**:

-   [Next.js Docs: App Router](https://nextjs.org/docs/app/building-your-application/routing)
-   [Next.js Docs: Pages Router](https://nextjs.org/docs/pages/building-your-application/routing)
-   [Next.js 13 Release Notes](https://nextjs.org/blog/next-13)

---

### 3. **Question**: Explain the concept of Server Components in Next.js 13+.

**Difficulty**: Hard  
**Category**: React Features  
**Key Concepts**: Server components, client components, hydration, performance  
**Sample Answer**:
**Server Components** are React components that run only on the server and never send their code to the client. They allow you to fetch data, access backend resources, and keep sensitive logic on the server. Server components reduce client bundle size and improve performance by sending only the rendered HTML and minimal JavaScript to the browser.

-   **Client Components** (marked with `'use client'`) can use browser APIs, state, and effects, but are sent to the client as JavaScript.
-   Server and client components can be composed together, but server components cannot use hooks like `useState` or `useEffect`.

**Connected Questions**: [#2: What is the App Router in Next.js 13+ and how does it differ from the Pages Router?]

**Further Reading**:

-   [Next.js Docs: Server Components](https://nextjs.org/docs/app/building-your-application/rendering/server-components)
-   [React Docs: Server Components](https://react.dev/reference/react-server)
-   [Vercel Blog: Introducing React Server Components](https://vercel.com/blog/introducing-react-server-components)

---

### 4. **Question**: What is the difference between `getStaticProps` and `getStaticPaths`?

**Difficulty**: Medium  
**Category**: Data Fetching  
**Key Concepts**: Static generation, dynamic routes, pre-rendering  
**Sample Answer**:

-   **`getStaticProps`** is used to fetch data at build time for a page. It returns props that are passed to the page component, enabling static generation.
-   **`getStaticPaths`** is used with dynamic routes to specify which paths should be statically generated at build time. It returns an array of paths and a fallback mode.

**Use Cases:**

-   Use `getStaticProps` for static pages with data that doesn't change often.
-   Use `getStaticPaths` for dynamic routes (e.g., blog posts, product pages) to pre-render specific paths.

**Connected Questions**: [#1: Explain the difference between Server-Side Rendering (SSR) and Static Site Generation (SSG) in Next.js.]

**Further Reading**:

-   [Next.js Docs: getStaticProps](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-props)
-   [Next.js Docs: getStaticPaths](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-paths)
-   [Next.js Blog: Static Generation](https://nextjs.org/blog/next-9-3#next-gen-static-site-generation-ssg-support)

---

### 5. **Question**: Explain Next.js Image component and its benefits.

**Difficulty**: Easy  
**Category**: Performance  
**Key Concepts**: Image optimization, lazy loading, responsive images, WebP  
**Sample Answer**:
The **Next.js Image component** (`next/image`) provides automatic image optimization, including resizing, lazy loading, and serving modern formats like WebP. It improves performance by reducing image sizes and loading only images in the viewport. The component requires width/height or `fill` for layout and supports responsive images with the `sizes` attribute.

**Benefits:**

-   Faster page loads
-   Better Core Web Vitals
-   Automatic format conversion and optimization

**Connected Questions**: [#10: What is the difference between `next build` and `next dev`?]

**Further Reading**:

-   [Next.js Docs: Image Component](https://nextjs.org/docs/pages/api-reference/components/image)
-   [Vercel Blog: Image Optimization](https://vercel.com/blog/nextjs-image-component)

---

### 6. **Question**: What is API Routes in Next.js and how do you create them?

**Difficulty**: Medium  
**Category**: Backend Integration  
**Key Concepts**: API routes, serverless functions, HTTP methods, middleware  
**Sample Answer**:
**API Routes** in Next.js allow you to create backend endpoints as files in the `/pages/api` or `/app/api` directory. Each file exports a handler function that receives a request and response object. API routes can handle any HTTP method (GET, POST, etc.), connect to databases, and run server-side logic. They are deployed as serverless functions on Vercel.

**Example:**

```js
// pages/api/hello.js
export default function handler(req, res) {
    res.status(200).json({message: 'Hello from API route!'});
}
```

**Connected Questions**: [#7: Explain the concept of middleware in Next.js.]

**Further Reading**:

-   [Next.js Docs: API Routes](https://nextjs.org/docs/pages/api-reference/api-routes)
-   [Vercel Docs: Serverless Functions](https://vercel.com/docs/concepts/functions/serverless-functions)

---

### 7. **Question**: Explain the concept of middleware in Next.js.

**Difficulty**: Medium  
**Category**: Middleware  
**Key Concepts**: Request/response modification, authentication, redirects, headers  
**Sample Answer**:
**Middleware** in Next.js runs before a request is completed, allowing you to modify the request/response, perform authentication, add headers, or redirect users. Middleware is defined in a `middleware.js` file at the root or in specific directories. It runs on the Edge Runtime for low latency.

**Use Cases:**

-   Authentication and authorization
-   A/B testing
-   URL rewrites and redirects

**Connected Questions**: [#6: What is API Routes in Next.js and how do you create them?]

**Further Reading**:

-   [Next.js Docs: Middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)
-   [Vercel Blog: Middleware](https://vercel.com/blog/introducing-middleware)

---

### 8. **Question**: What is the difference between `next/link` and regular anchor tags?

**Difficulty**: Easy  
**Category**: Navigation  
**Key Concepts**: Client-side navigation, prefetching, performance optimization  
**Sample Answer**:

-   **`next/link`** enables client-side navigation between pages in a Next.js app, preventing full page reloads and improving performance. It also prefetches linked pages in the background for faster navigation.
-   **Regular anchor tags** (`<a>`) cause a full page reload and do not prefetch content.

**Best Practices:**

-   Use `next/link` for internal navigation.
-   Use `<a>` for external links or when you need default browser behavior.

**Connected Questions**: [#2: What is the App Router in Next.js 13+ and how does it differ from the Pages Router?]

**Further Reading**:

-   [Next.js Docs: next/link](https://nextjs.org/docs/pages/api-reference/components/link)
-   [Vercel Blog: Prefetching in Next.js](https://vercel.com/blog/nextjs-prefetching)

---

### 9. **Question**: Explain Next.js configuration and the `next.config.js` file.

**Difficulty**: Medium  
**Category**: Configuration  
**Key Concepts**: Webpack configuration, environment variables, redirects, rewrites  
**Sample Answer**:
The `next.config.js` file is used to customize and extend the default Next.js configuration. You can add custom Webpack settings, define environment variables, set up redirects and rewrites, and enable experimental features. The file can export an object or a function.

**Example:**

```js
module.exports = {
    reactStrictMode: true,
    images: {
        domains: ['example.com'],
    },
    async redirects() {
        return [{source: '/old', destination: '/new', permanent: true}];
    },
};
```

**Connected Questions**: [#10: What is the difference between `next build` and `next dev`?]

**Further Reading**:

-   [Next.js Docs: Configuration](https://nextjs.org/docs/pages/api-reference/next-config-js)
-   [Vercel Blog: Customizing Next.js](https://vercel.com/blog/customizing-nextjs)

---

### 10. **Question**: What is the difference between `next build` and `next dev`?

**Difficulty**: Easy  
**Category**: Development  
**Key Concepts**: Development vs production, hot reloading, optimization  
**Sample Answer**:

-   **`next dev`** runs the Next.js development server with hot reloading, source maps, and debugging features. It is optimized for developer experience, not performance.
-   **`next build`** creates an optimized production build, including minification, code splitting, and static generation. The output is ready for deployment and optimized for speed and scalability.

**Best Practices:**

-   Use `next dev` during development for fast feedback.
-   Use `next build` before deploying to production.

**Connected Questions**: [#5: Explain Next.js Image component and its benefits.], [#9: Explain Next.js configuration and the `next.config.js` file.]

**Further Reading**:

-   [Next.js Docs: next build](https://nextjs.org/docs/pages/api-reference/cli#build)
-   [Next.js Docs: next dev](https://nextjs.org/docs/pages/api-reference/cli#development)
-   [Vercel Blog: Next.js Build Performance](https://vercel.com/blog/nextjs-build-performance)
