- [Vite + ReactJS Project - Job Portal (SPA CRUD Application)](#vite--reactjs-project---job-portal-spa-crud-application)
  - [Start the Application](#start-the-application)
  - [Deploy for production](#deploy-for-production)
  - [Development Notes](#development-notes)
  - [Notes](#notes)
    - [What is React?](#what-is-react)
    - [What is Components?](#what-is-components)
    - [What is State?](#what-is-state)
    - [What is Hooks?](#what-is-hooks)
    - [What is JSX (Javascript Syntax Extension)?](#what-is-jsx-javascript-syntax-extension)
    - [Different Types of Applications you can build using ReactJS](#different-types-of-applications-you-can-build-using-reactjs)
    - [Tools](#tools)
  - [Tutorial References / Takeaways:](#tutorial-references--takeaways)


# Vite + ReactJS Project - Job Portal (SPA CRUD Application)
Vite + ReactJS SPA CRUD


## Start the Application
``` 
$ npm install
$ npm run dev
$ npm run server
```

## Deploy for production
```
$ npm run build
```

## Development Notes

```
$ npm create vite@latest job-portal 
$ cd job-portal 
$ code . 

 
Edit vite.config.js and define your preferred server 

    import { defineConfig } from 'vite' 
    import react from '@vitejs/plugin-react' 

    // https://vitejs.dev/config/ 
    export default defineConfig({ 
        plugins: [react()], 
        server:{ 
            port: 3000, 
        } 
    }) 

$ npm install 
$ npm run dev 

Install VS Code Extension ES7+ React/Redux/React-Native snippets, to use snippets for creating components: 
    rafc – create a react arrow function component 
    rafce – create a react arrow function component with export 
    rafcp - create a react arrow function component with prop types 
    and more 

Setup tailwind CSS with Vite https://tailwindcss.com/docs/guides/vite 
    $ npm install –D tailwindcss postcss autoprefixer 
    $ npx tailwindcss init –p 
    edit tailwind.config.js 

        /** @type {import('tailwindcss').Config} */ 

        export default { 

        content: [ 

            "./index.html", 

            "./src/**/*.{js,ts,jsx,tsx}", 

        ], 

        theme: { 

            extend: { 

            fontFamily:{ 

                sans: ['Roboto', 'sans-serif'] 

            }, 

            gridTemplateColumns:{ 

                '70/30': '70% 28%', 

            } 

            }, 

        }, 

        plugins: [], 

        } 

Install VS Code extension Tailwind CSS, Console Ninja 
    Edit index.css, add below: 

        @tailwind base; 

        @tailwind components; 

        @tailwind utilities; 

Restart the server 
    ctrl + C 
    $ npm run dev 

Install React Icons Package 
    $ npm install react-icons 

Install React Router for routing 
    $ npm install react-router-dom 

Install json-server as a dev dependency to create a mock API 
    $ npm i -D json-server 

Add "server" to package.json to let jobs.json be the mock API data, run on port 8000 (5000 is default): 

    "scripts": { 
        "dev": "vite", 
        "build": "vite build", 
        "lint": "eslint . --ext js,jsx --report-unused-disable-directives --max-warnings 0", 
        "preview": "vite preview", 
        "server": "json-server --watch src/jobs.json --port 8000" 
    }, 

Add proxy to server to vite.config.js so that next time you want to do make a request, you would just call "/api/jobs". Anything that starts from /api will call to the server 

    export default defineConfig({ 
    plugins: [react()], 
    server:{ 
        port: 3000, 
        proxy: { 
        '/api':{ 
            target: 'http://localhost:8000', 
            changeOrigin: true, 
            rewrite: (path) => path.replace(/^\/api/, ''), 
        } 
        } 
    } 
    }) 

Run mock server 
    $ npm run server 

Install spinner for loading 
    $ npm install react-spinners 

Install toastify 
    $ npm install react-toastify 

Deploy for production > output to /dist folder 
    Stop the development server : $ ctrl + c 
    $ npm run build 
    $npm run preview 
```

## Notes

### What is React? 
- React is a JavaScript library/framework for building user interfaces. 
- It was created by Facebook. 
- Websites/Uls are looked at in terms of components. 
- React is currently the most popular out of the major front-end frameworks. 
- React allows us to build very dynamic and interactive websites and user interfaces. 
- Very fast, especially with the new compiler. 
- There is a huge ecosystem from Next.js to React Native. 
Best framework to learn to get a job. 


### What is Components? 
- Reusable piece of code that can be used to build elements on the page. 
- Allows us to break down complex Uls, which makes them easier to maintain and scale. 
- Components can get props passed in and can hold their own state. 

### What is State? 
- State represents the data that a component manages internally. 
- This could be form input data, fetched data, Ul-related data like if a modal is open/close. 
- There is also global state, which relates to the app as a whole and not a single component. 

### What is Hooks? 
- Allow us to use state and other React features within functional components 
    - useState 
    - useEffect 
    - useRef 
    - useReducer 
    - useContext, useMemo & useCallback will be phased out in React 19 

### What is JSX (Javascript Syntax Extension)? 
- An HTML-like syntax within JavaScript (components) 

### Different Types of Applications you can build using ReactJS 
- SSA (Single Page App) 
- Load a single HTML file and Javascript loads the entire UI including routes 
- SSR (Server-Side Rendered) 
- Server sends fully rendered page to client. You can fetch data and load it as well 
- SSG (Static Site Generation) 
- React generated static HTML files at build time. These are very fast 


### Tools 
- Vite 
    - A super fast front-end toolkit that can be used for all kinds of JS projects including React 
    - It is built on top of ESBuild, which is a very fast JS bundler 
    - Fast development server with hot-reload 
    - Installed with npm create vite@latest 

    <strong>Note: </strong>

    `$ create react app` was the most popular option to build a spa with react and it's been around for a long time but it's no longer recommended it's a bit bloated it's uh slower and as far as I know it's not supported anymore so vit is a newer Solution that's faster it has a better developer experience 


## Tutorial References / Takeaways:

```

React Crash Course 2024 
By Traversy Media 
https://www.youtube.com/watch?v=LDB4uaJ87e0


References: 
 
0:00 - Intro 
1:55 - What Is React? (Slide) 
3:43 - Why React? (Slide) 
7:19 - What Are Components? (Slide) 
8:21 - What Is State? (Slide) 
10:00 - What Are Hooks? (Slide) 
11:17 - What Is JSX? (Slide) 
12:42 - SPA, SSR, SSG (Slide) 
15:38  - Vite (Slide) 
16:30 - Project Demo 
19:53 - Setup React With Vite 
22:29 - File Explanation 
25:11 - Boilerplate Cleanup 
26:48 - Tailwind CSS Setup 
30:24 - JSX Crash Course 
39:37 - Start Homepage  
42:00 - Navbar Component 
43:56 - Image Import 
45:24 - Hero Component 
46:17 - Props 
48:00 - Default Props 
48:51 - Wrapper Components 
55:14 - JobListings Component 
58:50 - Create Lists With map() 
1:03:20 - Single JobListing Component 
1:05:49 - Limit Jobs to 3 
1:07:50 - useState() Hook & Desc Toggle 
1:13:07 - Creating an Event 
1:14:20 - Updating Component State 
1:16:00 - React Icons Package 
1:18:00 - React Router Setup 
1:20:21 - Create Routes From Elements 
1:21:36 - Router Provider 
1:22:36 - Homepage Component/Route 
1:24:40 - Layouts 
1:29:06 - Jobs Page Component/Route 
1:30:50 - Link Component 
1:34:20 - Custom 404 Page 
1:36:55 - Active Links With NavLink 
1:41:00 - Conditional Rendering 
1:43:10 - JSON Server Setup 
1:47:00 - useEffect() & Data Fetching 
1:53:07 - Loading Spinner 
1:51:06 - Conditional Fetching 
1:59:45 - Proxying 
2:03:38 - Single Job Page 
2:09:04 - useParams() to Get ID 
2:12:25 - Data Loaders 
2:16:36 - Single Job Output 
2:22:00 - Add Job Page 
2:23:40 - Working With Forms 
2:30:05 - Form Submission 
2:35:27 - Pass Function as Prop 
2:39:32 - POST Request to Add Job 
2:41:45 - Delete Job Button/function 
2:45:12 - DELETE Request to Remove Job 
2:46:50 - React Toastify Package 
2:50:08 - Edit Job Page/Form 
2:56:05 - Update Form Submission 
2:58:54 - PUT Request to Update Job 
3:02:10 - Build Static Assets For Production 

 
React crash course teaches how to build a job listing website using React, covering components, props, state, hooks, data fetching, and React Router. It demonstrates creating a single-page application, server-side rendering, and static site generation. The course also covers setting up a development environment, using Tailwind CSS, and implementing CRUD functionality with a mock backend. 
 

Key moments: 

00:00 React is a JavaScript library for building user interfaces using components, props, state, and hooks. It simplifies UI development and is popular due to its job opportunities and vast ecosystem. 

        - React is a UI library, not a framework, but competes with frameworks like Angular. It is widely used with other libraries like React Router for full-featured solutions. 

        - React simplifies building dynamic user interfaces with components, props, state, and hooks. It offers an easier way to manage and scale UIs compared to vanilla JavaScript. 

        - Components in React are reusable pieces of code that help build elements on a page. They can be functional or class-based, with functional components being more commonly used. 

12:04 React allows for dynamic interfaces with JSX, enabling expressions, loops, conditionals, and more within HTML, offering flexibility. Different types of applications like SPAs, SSR apps, and static site generation can be built using React and various frameworks. 

        - Differences between JSX and HTML, like using 'class name' instead of 'class', showcase the flexibility JSX offers for dynamic content. 

        - Types of applications possible with React, such as SPAs, SSR apps, and static site generation, each catering to different needs and considerations. 

        - Comparison of SSR apps and static site generation with SPAs, highlighting benefits for SEO and initial page load times, and deployment considerations. 

24:09 The video discusses setting up Tailwind CSS in a React project, demonstrating how to install and configure it, use Tailwind classes, and work with JSX syntax for dynamic content.  

        - Setting up Tailwind CSS involves installing and configuring it in a React project, including adding Tailwind classes to style components. 

        - Working with JSX in React components requires understanding how to handle dynamic content, use variables, loops, lists, and conditionals within the JSX syntax. 

36:14 JSX allows for dynamic content rendering and inline styling in React components. Components can be organized into separate files and passed props for reusability and customization. 

        - Utilizing JSX for dynamic content rendering and inline styling in React components enhances flexibility and customization. 

        - Organizing components into separate files and passing props enables reusability and easy customization of content. 

48:16 The video demonstrates creating components in React, passing props to customize styling, and importing data from a JSON file to display dynamic content. It emphasizes keeping code clean and organized by separating components. 

        - Creating components in React and organizing code for clarity and reusability. Demonstrating the use of self-closing tags and wrapper components. 

        - Passing props to customize styling in React components. Utilizing props to dynamically change background colors and styles. 

        - Importing data from a JSON file in React to display dynamic content. Discussing the use of JSON files for mock backend data. 

1:00:20 The video demonstrates how to dynamically update a webpage by replacing hardcoded data with data from a JSON file, creating components for job listings, and implementing a 'show more' feature for job descriptions. 

        - Replacing hardcoded data with dynamic data from a JSON file to display unique job listings. Utilizing job data to populate different fields like job type, title, description, and salary. 

        - Creating reusable components for job listings to enhance code organization and scalability. Implementing a singular job listing component that can be used for each job entry. 

        - Introducing state management using the useState hook to toggle between short and full job descriptions. Adding a 'show more' button to expand job descriptions dynamically. 

1:12:23 The video discusses implementing conditional rendering based on state in React components, showcasing how to toggle between showing more or less text based on a boolean state. It also delves into adding icons using a separate package and setting up routing using React Router for multi-page applications. 

        - Implementing conditional rendering based on state to toggle between showing more or less text in React components. 

        - Adding icons to components using a separate package like React Icons for enhanced visual elements. 

        - Setting up routing for multi-page applications using React Router to navigate between different pages in a React application. 

1:24:28 Layouts in React help display components like navbar and footers on every page, enhancing reusability and efficiency. Creating multiple layouts allows for flexible design structures in React projects. 

        - Implementing layouts in React for consistent display of components like navbar and footers on every page. This enhances user experience and simplifies development. 

        - Creating multiple layouts in React projects to accommodate different design structures and enhance flexibility in displaying components across various pages. 

1:36:34 The video discusses setting up a catchall route for a not found page, implementing active links in a navigation bar, and fetching data from a backend using Json server in a React application. 

        - Implementing a catchall route for a not found page and setting up active links in a navigation bar. 

        - Fetching data from a backend using Json server and integrating it into a React application. 

        - Utilizing useEffect and useState hooks to fetch and manage data in React components. 

1:48:36 The video explains how to fetch data from an API in React using useEffect and useState, including handling loading states and displaying spinners during data fetching. 

        - Setting up state variables for data and loading states, and using useEffect to fetch data from an API. 

        - Implementing a loading spinner component to indicate data fetching in progress. 

        - Utilizing conditional rendering based on the page to control the number of displayed items fetched from the API. 

2:00:41 The video demonstrates how to fetch data using useEffect in React, showing how to use params from React Router Dom to dynamically fetch data based on the URL. It also hints at other methods like React Suspense and React Query for data fetching. 

        - Using React Suspense and React Query for data fetching, providing alternatives to useEffect for fetching data in React applications. 

        - Implementing a data loader from React Router to fetch data in a different way, allowing for global state management and data export to other components. 

        - Exploring the use of params from React Router Dom to dynamically fetch data based on the URL, showcasing how to integrate it into the data fetching process. 

2:12:43 The video discusses implementing a job loader feature using React Router, fetching data from an API, and updating a job page with dynamic data. It also covers creating an add job page with a form and managing form fields using state. 

        - Implementing a job loader feature using React Router and fetching data from an API. 

        - Updating a job page with dynamic data and creating an add job page with a form. 

        - Managing form fields using state and discussing different approaches to handling form data. 

2:24:48 The video discusses setting default values for form inputs, connecting form fields to state using onchange events, and submitting form data to an API in a React application. 

        - Connecting form fields to state by adding onchange events to update state values when input changes. 

        - Submitting form data to an API by creating an object from form fields and handling form submission. 

        - Setting default values for form inputs like type and salary to ensure initial values are displayed correctly. 

2:36:55 The video demonstrates how to pass functions as props in React components, make API requests, handle deletions, and use toast notifications for user feedback. 

        - Passing functions as props in React components and handling form submissions. 

        - Making API requests and handling deletions in React applications. 

        - Implementing toast notifications for user feedback in React applications. 

2:49:01 The video demonstrates creating, editing, and updating job data in a React application using forms and state management. It showcases how to populate forms with existing data and make PUT requests to update job information. 

        - Creating a new job and displaying success messages upon addition and deletion. 

        - Setting up the edit job page, loading existing job data, and navigating between pages. 

        - Copying and modifying form elements for editing existing job data, including updating job information and displaying success messages. 

3:01:05 The tutorial covers creating a full CRUD application with React, including components, props, state, React Router, and various hooks, providing enough knowledge to start simple projects independently. Deploying involves running 'npm run build' for a production version, suitable for deployment anywhere. 

        - Deployment process involves creating a production build using 'npm run build' and deploying the 'disc' folder to any hosting platform, ensuring the site runs with the production build of React. 

        - For a real project deployment, an API with Express or similar is needed, but the front-end structure remains the same whether using a local server or a REST API. 

```