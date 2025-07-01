# Next.js Interview Questions

---

### 1. Explain the difference between Server-Side Rendering (SSR) and Static Site Generation (SSG) in Next.js? [Medium]

**Sample Answer**:

-   **Server-Side Rendering (SSR)**: Pages are rendered on the server at request time using `getServerSideProps`. Each request generates a fresh HTML page, ensuring up-to-date data. SSR is ideal for dynamic content that changes frequently or is user-specific (e.g., dashboards, authenticated pages).
-   **Static Site Generation (SSG)**: Pages are rendered at build time using `getStaticProps`. The generated HTML is reused for every request, resulting in fast load times and better scalability. SSG is best for content that doesn't change often (e.g., blogs, documentation). Incremental Static Regeneration (ISR) allows static pages to be updated after deployment.

**Comparison:**

-   SSR: Dynamic, slower per request, always up-to-date.
-   SSG: Static, fast, scalable, may need revalidation for updates.

**Connected Questions**: [#2](#2), [#3](#3)

**Further Reading**:

-   [Next.js Docs: Data Fetching](https://nextjs.org/docs/basic-features/data-fetching)
-   [Vercel Blog: Static vs Server Rendering](https://vercel.com/blog/static-vs-server-rendering)
-   [Learning Next.js by Vercel](https://nextjs.org/learn)

---

### 2. What is the App Router in Next.js 13+ and how does it differ from the Pages Router? [Medium]

**Sample Answer**:

-   **App Router** (introduced in Next.js 13) uses the `/app` directory for routing, supporting nested layouts, server components, and advanced data fetching. It enables more granular control over rendering and layout composition.
-   **Pages Router** uses the `/pages` directory, with each file corresponding to a route. It relies on traditional React components and data fetching methods like `getStaticProps` and `getServerSideProps`.

**Comparison:**

-   App Router: Modern, supports server components, layouts, streaming, and advanced routing.
-   Pages Router: Simpler, more mature, but less flexible for complex layouts.

**Connected Questions**: [#1](#1), [#3](#3)

**Further Reading**:

-   [Next.js Docs: App Router](https://nextjs.org/docs/app/building-your-application/routing)
-   [Next.js Docs: Pages Router](https://nextjs.org/docs/pages/building-your-application/routing)
-   [Next.js 13 Release Notes](https://nextjs.org/blog/next-13)

---

### 3. Explain the concept of Server Components in Next.js 13+. [Hard]

**Sample Answer**:
**Server Components** are React components that run only on the server and never send their code to the client. They allow you to fetch data, access backend resources, and keep sensitive logic on the server. Server components reduce client bundle size and improve performance by sending only the rendered HTML and minimal JavaScript to the browser.

-   **Client Components** (marked with `'use client'`) can use browser APIs, state, and effects, but are sent to the client as JavaScript.
-   Server and client components can be composed together, but server components cannot use hooks like `useState` or `useEffect`.

**Connected Questions**: [#2](#2)

**Further Reading**:

-   [Next.js Docs: Server Components](https://nextjs.org/docs/app/building-your-application/rendering/server-components)
-   [React Docs: Server Components](https://react.dev/reference/react-server)
-   [Vercel Blog: Introducing React Server Components](https://vercel.com/blog/introducing-react-server-components)

---

### 4. What is the difference between `getStaticProps` and `getStaticPaths`? [Medium]

**Sample Answer**:

-   **`getStaticProps`** is used to fetch data at build time for a page. It returns props that are passed to the page component, enabling static generation.
-   **`getStaticPaths`** is used with dynamic routes to specify which paths should be statically generated at build time. It returns an array of paths and a fallback mode.

**Use Cases:**

-   Use `getStaticProps` for static pages with data that doesn't change often.
-   Use `getStaticPaths` for dynamic routes (e.g., blog posts, product pages) to pre-render specific paths.

**Connected Questions**: [#1](#1)

**Further Reading**:

-   [Next.js Docs: getStaticProps](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-props)
-   [Next.js Docs: getStaticPaths](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-paths)
-   [Next.js Blog: Static Generation](https://nextjs.org/blog/next-9-3#next-gen-static-site-generation-ssg-support)

---

### 5. Explain Next.js Image component and its benefits? [Easy]

**Sample Answer**:
The **Next.js Image component** (`next/image`) provides automatic image optimization, including resizing, lazy loading, and serving modern formats like WebP. It improves performance by reducing image sizes and loading only images in the viewport. The component requires width/height or `fill` for layout and supports responsive images with the `sizes` attribute.

**Benefits:**

-   Faster page loads
-   Better Core Web Vitals
-   Automatic format conversion and optimization

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Next.js Docs: Image Component](https://nextjs.org/docs/pages/api-reference/components/image)
-   [Vercel Blog: Image Optimization](https://vercel.com/blog/nextjs-image-component)

---

### 6. What is API Routes in Next.js and how do you create them? [Medium]

**Sample Answer**:
**API Routes** in Next.js allow you to create backend endpoints as files in the `/pages/api` or `/app/api` directory. Each file exports a handler function that receives a request and response object. API routes can handle any HTTP method (GET, POST, etc.), connect to databases, and run server-side logic. They are deployed as serverless functions on Vercel.

**Example:**

```js
// pages/api/hello.js
export default function handler(req, res) {
    res.status(200).json({message: 'Hello from API route!'});
}
```

**Connected Questions**: [#7](#7)

**Further Reading**:

-   [Next.js Docs: API Routes](https://nextjs.org/docs/pages/api-reference/api-routes)
-   [Vercel Docs: Serverless Functions](https://vercel.com/docs/concepts/functions/serverless-functions)

---

### 7. Explain the concept of middleware in Next.js? [Medium]

**Sample Answer**:
**Middleware** in Next.js runs before a request is completed, allowing you to modify the request/response, perform authentication, add headers, or redirect users. Middleware is defined in a `middleware.js` file at the root or in specific directories. It runs on the Edge Runtime for low latency.

**Use Cases:**

-   Authentication and authorization
-   A/B testing
-   URL rewrites and redirects

**Connected Questions**: [#6](#6)

**Further Reading**:

-   [Next.js Docs: Middleware](https://nextjs.org/docs/app/building-your-application/routing/middleware)
-   [Vercel Blog: Middleware](https://vercel.com/blog/introducing-middleware)

---

### 8. What is the difference between `next/link` and regular anchor tags? [Easy]

**Sample Answer**:

-   **`next/link`** enables client-side navigation between pages in a Next.js app, preventing full page reloads and improving performance. It also prefetches linked pages in the background for faster navigation.
-   **Regular anchor tags** (`<a>`) cause a full page reload and do not prefetch content.

**Best Practices:**

-   Use `next/link` for internal navigation.
-   Use `<a>` for external links or when you need default browser behavior.

**Connected Questions**: [#2](#2)

**Further Reading**:

-   [Next.js Docs: next/link](https://nextjs.org/docs/pages/api-reference/components/link)
-   [Vercel Blog: Prefetching in Next.js](https://vercel.com/blog/nextjs-prefetching)

---

### 9. Explain Next.js configuration and the `next.config.js` file? [Medium]

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

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Next.js Docs: Configuration](https://nextjs.org/docs/pages/api-reference/next-config-js)
-   [Vercel Blog: Customizing Next.js](https://vercel.com/blog/customizing-nextjs)

---

### 10. What is the difference between `next build` and `next dev`? [Easy]

**Sample Answer**:

-   **`next dev`** runs the Next.js development server with hot reloading, source maps, and debugging features. It is optimized for developer experience, not performance.
-   **`next build`** creates an optimized production build, including minification, code splitting, and static generation. The output is ready for deployment and optimized for speed and scalability.

**Best Practices:**

-   Use `next dev` during development for fast feedback.
-   Use `next build` before deploying to production.

**Connected Questions**: [#5](#5), [#9](#9)

**Further Reading**:

-   [Next.js Docs: next build](https://nextjs.org/docs/pages/api-reference/cli#build)
-   [Next.js Docs: next dev](https://nextjs.org/docs/pages/api-reference/cli#development)
-   [Vercel Blog: Next.js Build Performance](https://vercel.com/blog/nextjs-build-performance)

### 11. What is Incremental Static Regeneration (ISR) in Next.js? [Medium]

**Sample Answer**:
Incremental Static Regeneration (ISR) allows you to update static content after deployment without rebuilding the entire site. Pages are regenerated in the background as traffic comes in, using the `revalidate` property in `getStaticProps`. This combines the benefits of static and dynamic rendering.

**Connected Questions**: [#2](#2), [#3](#3)

**Further Reading**:

-   [Next.js Docs: ISR](https://nextjs.org/docs/pages/building-your-application/data-fetching/incremental-static-regeneration)
-   [Vercel Blog: ISR](https://vercel.com/blog/nextjs-incremental-static-regeneration)

---

### 12. How does Next.js handle image optimization? [Medium]

**Sample Answer**:
Next.js provides the `next/image` component for automatic image optimization. It supports responsive images, lazy loading, and modern formats like WebP. Images are served in optimal sizes and formats, improving performance and user experience.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Next.js Docs: Image Optimization](https://nextjs.org/docs/pages/api-reference/components/image)
-   [Vercel Blog: Image Optimization](https://vercel.com/blog/nextjs-image-optimization)

---

### 13. What is middleware in Next.js and how is it used? [Medium]

**Sample Answer**:
Middleware in Next.js allows you to run code before a request is completed. It can be used for authentication, redirects, logging, and more. Middleware runs at the edge, enabling fast, dynamic request handling without server round-trips.

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Next.js Docs: Middleware](https://nextjs.org/docs/pages/building-your-application/routing/middleware)
-   [Vercel Blog: Middleware](https://vercel.com/blog/introducing-middleware)

---

### 14. How does Next.js support internationalization (i18n)? [Medium]

**Sample Answer**:
Next.js has built-in support for internationalized routing and locale detection. You can define supported locales and default locale in `next.config.js`, and Next.js will handle locale-based routing and automatic language detection.

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Next.js Docs: Internationalization](https://nextjs.org/docs/pages/building-your-application/routing/internationalization)
-   [Vercel Blog: i18n](https://vercel.com/blog/nextjs-internationalized-routing)

---

### 15. What is the difference between `getServerSideProps` and `getStaticProps`? [Medium]

**Sample Answer**:
`getServerSideProps` runs on every request and enables server-side rendering (SSR), while `getStaticProps` runs at build time for static site generation (SSG). Use SSR for dynamic data and SSG for static content that doesn't change often.

**Connected Questions**: [#2](#2), [#3](#3)

**Further Reading**:

-   [Next.js Docs: Data Fetching](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-server-side-props)
-   [Next.js Docs: Data Fetching](https://nextjs.org/docs/pages/building-your-application/data-fetching/get-static-props)

---

### 16. How do you use API routes in Next.js? [Medium]

**Sample Answer**:
API routes in Next.js allow you to create backend endpoints as files in the `pages/api` directory. Each file exports a handler function that receives request and response objects. API routes are deployed as serverless functions, enabling full-stack development.

**Connected Questions**: [#5](#5)

**Further Reading**:

-   [Next.js Docs: API Routes](https://nextjs.org/docs/pages/api-reference/api-routes)
-   [Vercel Blog: API Routes](https://vercel.com/blog/nextjs-api-routes)

---

### 17. How does Next.js handle static assets? [Easy]

**Sample Answer**:
Static assets like images, fonts, and files are placed in the `public` directory in a Next.js project. They are served at the root URL path and can be accessed directly in your application.

**Connected Questions**: [#12](#12)

**Further Reading**:

-   [Next.js Docs: Static File Serving](https://nextjs.org/docs/pages/building-your-application/deploying/static-file-serving)

---

### 18. What is the difference between client-side and server-side navigation in Next.js? [Medium]

**Sample Answer**:
Client-side navigation uses the Next.js `Link` component to navigate between pages without a full page reload, providing a single-page application (SPA) experience. Server-side navigation reloads the entire page. Client-side navigation is faster and preserves state.

**Connected Questions**: [#4](#4)

**Further Reading**:

-   [Next.js Docs: Routing](https://nextjs.org/docs/pages/building-your-application/routing)
-   [Vercel Blog: Client-side Navigation](https://vercel.com/blog/client-side-navigation)

---

### 19. How do you handle environment variables in Next.js? [Easy]

**Sample Answer**:
Next.js supports environment variables via `.env` files. Variables prefixed with `NEXT_PUBLIC_` are exposed to the browser. Access variables using `process.env.VARIABLE_NAME` in your code.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Next.js Docs: Environment Variables](https://nextjs.org/docs/pages/building-your-application/configuring/environment-variables)

---

### 20. How do you deploy a Next.js application? [Easy]

**Sample Answer**:
Next.js applications can be deployed to Vercel, which offers seamless integration and serverless deployment. You can also deploy to other platforms using Docker, static export, or custom servers.

**Connected Questions**: [#10](#10)

**Further Reading**:

-   [Next.js Docs: Deployment](https://nextjs.org/docs/pages/building-your-application/deploying)
-   [Vercel Docs: Deploying Next.js](https://vercel.com/docs/concepts/deployments/overview)
