# 🚀 NAMASTE-REACT COURSE EPISODE-1

## REACT INTRODUCTION :-

- React is a free and open-source JavaScript library for building interactive websites and user interfaces or front-end webpage components, such as forms, buttons, and other UI elements.
- Since its release in 2013, React has been maintained by Meta (formerly Facebook) along with a community of developers and companies.
- It is **component-based**, meaning applications are entirely built using reusable components.
- React allows us to create single-page applications (SPAs) and manage UI efficiently by rendering only the necessary parts instead of reloading the entire page.
- React was first used in 2011 on Facebook's News Feed, in 2012 on Instagram, and was publicly released in 2013.
- It is optimized for applications that require dynamic data updates, making user interactions smooth and efficient.

## HOW DOES REACT WORK :-

- When building client-side apps, Facebook developers realized that directly manipulating the **DOM** (Document Object Model) is slow.
- To solve this, React implements a **Virtual DOM**, a lightweight JavaScript representation of the actual DOM.
- When a user interacts with a React application, React updates the Virtual DOM first, then compares it with the previous version, and finally updates only the changed elements in the actual DOM.
- This **diffing algorithm** helps React achieve **faster rendering** and better performance.

## WHAT IS EMMET ?

- **Emmet** is a productivity tool that helps developers write HTML and CSS faster using shorthand syntax.
- It expands abbreviations into full-fledged HTML structures, making coding quicker and more efficient.

## WHAT IS CDN ?

- **CDN (Content Delivery Network)** is a distributed network of servers that helps deliver content faster to users.
- React and ReactDOM can be loaded via CDN instead of installing them locally.
- CDNs reduce page load time, optimize data-heavy applications, and improve site performance.

## CROSSORIGIN ATTRIBUTE IN CDN LINKS :

- **CORS (Cross-Origin Resource Sharing)** is an HTTP-based security mechanism that controls how resources are requested from different origins.
- The `crossorigin` attribute in `<script>` tags enables CORS support when loading external scripts.
- Example:
  ```html
  <script crossorigin src="https://cdn.example.com/react.js"></script>
  ```

## WHY REACT IS KNOWN AS 'REACT' ?

- React is named because it helps developers **"react"** efficiently to changes in application state by re-rendering only the necessary parts of the UI.

## DIFFERENCE BETWEEN FRAMEWORK AND LIBRARY :

| Feature  | Framework                                             | Library                                                   |
| -------- | ----------------------------------------------------- | --------------------------------------------------------- |
| Purpose  | Provides a full structure for application development | Provides specific functionality to enhance an application |
| Control  | The framework dictates the architecture               | Developers control how the library is used                |
| Examples | Angular, Vue.js                                       | React, jQuery                                             |

React is considered a **library**, not a framework, because it focuses only on UI rendering, giving developers flexibility to integrate other tools as needed.
