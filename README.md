## Next.js App Router Course - Starter

This is the starter template for the Next.js App Router Course. It contains the starting code for the dashboard application.

For more information, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.
 #   p r o j e c t 2 
 
 ###  CHAPTER 1 
** How to cretae the Next.js app
**How to install the project's packages with the command npm install.
** Understandinf the folder structure of the project.

# CHAPTER 2 CSS STYLING
-How to add Global Styles in the application.
- Knowledge about Tailwind CSS Framsework.
- CSS Modules which allow to scope CSS to a component by creating unique class names.
 - Clsx library lets us yo toggle class names easily if we need to conditionally style an element based on state or some other condition.

 # CHAPTER 3 OPTIMIZING FONTS AND IMAGES
  - Fonts :  play a significant role in the design of a website, but using custom fonts can affect performance if the font files need to be fetched and 
    loaded.
  - How to add custom fonts with next/font and images with next/images.

  # CHAPTER 4 CREATNG LAYOUTS AND PAGES
 - How to create nested routing.
 - Next.js uses file-system routing where folders are used to create nested routes. Each folder represents a route segment that maps to a URL segment.
 - The purpose of the laytout file in the Next.js is to create a shared layout that all pages in your application can use.
  
 # CHAPTER 5 NAVIGATING BETWWEN PAGES
  - In Next.js, you can use the <Link /> Component to link between pages in your application. <Link> allows you to do client-side navigation with JavaScript.
  - To improve the navigation experience, Next.js automatically code splits your application by route segments. This is different from a traditional React SPA, where the 
    browser loads all your application code on initial load.
  - Showing active links we use  usePathname().
  - clsx library  apply class names when the link is active. When link.href matches the pathname, the link should be displayed with blue text and a light blue background.
  
  #  CHAPTER 6 SETTING UP YOUR DATABASE
  -How to set up a Vercel account and to how to connect the githuib repositary with the Vercel account.
  - By connecting your GitHub repository, whenever you push changes to your main branch, Vercel will automatically redeploy your application with no configuration needed.
  - How to create a Postgres database in the Vercel account. 
  
 #  CHAPTER 7 FETCHING DATA
 - APIs are an intermediary layer between your application code and database. There are a few cases that we can  use an API:
 1 If you're using 3rd party services that provide an API.
 2 If you're fetching data from the client, you want to have an API layer that runs on the server to avoid exposing your database secrets to the client.
 - Fetching data with Server Components allow you to query the database directly from the server without an additional API layer.
 - SQL allows us to write targeted queries to fetch and manipulate specific data
 - A "waterfall" refers to a sequence of network requests that depend on the completion of previous requests. In the case of data fetching, each request can only begin once 
   the previous request has returned data.

 #  CHAPTER 8 STATIC AND DYNAMIC RENDERING 
 - With static rendering, data fetching and rendering happens on the server at build time (when you deploy) or when revalidating data.
 - Benefits of using static rendering: Faster Websites, Reduced Server Load, SEO.
 - Static rendering is useful for UI with no data or data that is shared across users, such as a static blog post or a product page. It might not be a good fit for a 
    dashboard that has personalized data which is regularly updated.
 - With dynamic rendering, content is rendered on the server for each user at request time (when the user visits the page).
 - The bebnefits od using dynamic rendering:Real-Time Data,User-Specific Content , Request Time Information.
  
  # CHAPTER 9 STREAMING
 - Streaming is a data transfer technique that allows you to break down a route into smaller "chunks" and progressively stream them from the server to the client as they 
   become ready.
 - By streaming, you can prevent slow data requests from blocking your whole page. This allows the user to see and interact with parts of the page without waiting for all the data to load before any UI can be shown to the user.
 - Two ways to  implement streaming in Next.js:
   1 At the page level, with the loading.tsx file.
   2 For specific components, with <Suspense>.
  
 #  CHAPTER 10 PARTIAL PRERENDERING
  - Partial Prerendering is a new rendering model that allows you to combine the benefits of static and dynamic rendering in the same route.
  - Partial Prerendering uses React's Suspense  to defer rendering parts of your application until some condition is met (e.g. data is loaded).
  - The Suspense fallback is embedded into the initial HTML file along with the static content. At build time (or during revalidation), the static content is prerendered to 
     create a static shell. The rendering of dynamic content is postponed until the user requests the route.
  -  To enable PPR  we add the ppr option.
 
 #  CHAPTER 11 ADDING SEARCH AND PAGINATION
  - <Search/> allows users to search for specific invoices.
  - <Pagination/> allows users to navigate between pages of invoices.
  -  <Table/> displays the invoices.
  -  URL search params hep us to manage the search state.
  -  Benefits 0f using  of implementing search with URL params: Bookmarkable and Shareable URLs, Server-Side Rendering and Initial Load, Analytics and Tracking.
  -  useSearchParams- Allows you to access the parameters of the current URL. For example, the search params for this URL /dashboard/invoices?page=1&query=pending would
    look like this: {page: '1', query: 'pending'}.
  -  sePathname - Lets you read the current URL's pathname. For example, for the route /dashboard/invoices, usePathname would return '/dashboard/invoices'.
  -  useRouter - Enables navigation between routes within client components programmatically. There are multiple methods you can use.
  -  "use client" - This is a Client Component, which means you can use event listeners and hooks.
  -  <input> - This is the search input.
  - Implementation Steps: Capture the user's input, Update the URL with the search params, Keep the URL in sync with the input field, Update the table to reflect the search 
     query.

  
 #  CHAPTER 12 MUTATING DATA
  - React Server Actions allow you to run asynchronous code directly on the server. They eliminate the need to create API endpoints to mutate your data.
  - offer an effective security solution, protecting against different types of attacks, securing your data, and ensuring authorized access.
  - In React, you can use the action attribute in the <form> element to invoke actions. The action will automatically receive the native FormData object, containing the 
    captured data.
  - Server Actions are integrated with Next.js caching. When a form is submitted through a Server Action, not only can you use the action to mutate data, but you can also 
    revalidate the associated cache using APIs like revalidatePath and revalidateTag.
  - How to create an invoice :
    1 Create a form to capture the user's input.
    2 Create a Server Action and invoke it from the form.
    3 Inside your Server Action, extract the data from the formData object.
    4 Validate and prepare the data to be inserted into your database.
    5 Insert the data and handle any errors.
    6 Revalidate the cache and redirect the user back to invoices page.
  
 #  CHAPTER 13 HANDLING ERRORS
 - How to handle all the errors tha we have by using error.tsx.
 - The error.tsx file can be used to define a UI boundary for a route segment. It serves as a catch-all for unexpected errors and allows you to display a fallback UI to 
   your users.
 - Another way how to handle errors is by using the notFound function.
 - error.tsx is useful for catching all errors, notFound can be used when you try to fetch a resource that doesn't exist.
  
  # CHAPTER 14 IMPROVING ACCESSIBILITY
  - Accessibility refers to designing and implementing web applications that everyone can use, including those with disabilities.
  -  eslint-plugin-jsx-a11y plugin in its ESLint config to help catch accessibility issues early.
  -  Three things that improve accessibility: Using sematic elements , labelling and focus outline.
  -  How to add aria labels.
  
 #  CHAPTER 15 ADDING AUTHENTICATION
  -Authentication is about making sure the user is who they say they are. You're proving your identity with something you have like a username and password.
  -Authorization is the next step. Once a user's identity is confirmed, authorization decides what parts of the application they are allowed to use.
  - To add authentication in the application we use NextAuth.js and we install NextAuth by the command pnpm i next-auth@beta.
  - How to use Middleware to redirect users and protect your routes.This will prevent users from accessing the dashboard pages unless they are logged in.
  - Adding providers option in the NextAuth help us to list different login options such as Google or GitHub.
    
 #  CHAPTER 16 ADDING METADATA
  - Metadata provides additional information about a webpage and play a significant role in enhancing a webpage's SEO ,
    making it more accessible and understandable for search engines and social media platforms.
  - Types of Metadata:
    1 Title Metadata: Responsible for the title of a webpage that is displayed on the browser tab.
    2 Description Metadata : provides a brief overview of the webpage content and is often displayed in search engine results.
    3 Keyword Matadata : includes the keywords related to the webpage content, helping search engines index the page.
    4 Open Graph Metadata : enhances the way a webpage is represented when shared on social media platforms
    5 Favicon Metadata : links the favicon (a small icon) to the webpage, displayed in the browser's address bar or tab.
    - Adding Metadata: There are two ways that we can add metadata in our applicsation :Config -based and File-based.
    
