## HomeWork Questions:

#### 1. Explore all the ways of writing CSS

1. **Vanilla CSS:**

   - We can use plain CSS to give styles to our app.
   - We create an `index.css` file and add all the CSS rules there.

2. **SASS / SCSS:**

   - SASS stands for **Syntactically Awesome StyleSheets**.
   - It is a stylesheet language that is **compiled to CSS**.
   - Allows us to make use of **Nested rules, variables, functions**.
   - SASS supports 2 syntaxes: **SASS and SCSS**.
   - **SCSS:** Uses the file extension `.scss`. It is a superset of CSS, using curly braces and semicolon syntax.
   - **SASS (The Indented Syntax):** Uses file extension `.sass`. It uses indentation instead of curly braces, and line-end instead of semicolon.

   | SCSS                       | SASS                      |
   | -------------------------- | ------------------------- |
   | .button {                  |                           |
   | padding: 3px 10px;         | .button                   |
   | font-size: 12px;           | padding: 3px 10px         |
   | border-radius: 3px;        | font-size: 12px           |
   | border: 1px solid #e1e4e8; | border-radius: 3px        |
   | }                          | border: 1px solid #e1e4e8 |

3. **Styled Components:**

   - It allows us to write styles just as we write React components.
   - It removes the mapping between components and styles.
   - Utilizes **tagged template literals** to style your components.

4. **Using External CSS Libraries** like Material UI, Tailwind CSS, Bootstrap, Ant Design, Chakra UI, etc.
   - These libraries provide **pre-styled components**.
   - **Tailwind CSS** is the most modern method used extensively to style web apps.

---

#### 2. How do you configure Tailwind?

1. **Step 1:** Create the project.
2. **Step 2:** Install Tailwind CSS via npm and initialize it to generate `tailwind.config.js`:
   ```sh
   npm install -D tailwindcss postcss
   npx tailwindcss init
   ```
3. **Step 3:** Create a `.postcssrc` file at the root level of our app. This tells Parcel to use PostCSS to read and understand Tailwind CSS.
4. **Step 4:** Configure the `.postcssrc` file:
   ```json
   {
     "plugins": {
       "tailwindcss": {}
     }
   }
   ```
5. **Step 5:** Configure `tailwind.config.js` by filling the `content` attribute:
   ```js
   module.exports = {
     content: ["./src/**/*.{html,js}"],
     theme: {
       extend: {},
     },
     plugins: [],
   };
   ```
6. **Step 6:** Add Tailwind directives in `index.css`:
   ```css
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```

---

#### 3. In `tailwind.config.js`, what do the keys "content", "theme", "extend", and "plugins" mean?

- **`content`**: Specifies paths to HTML, JS components, and source files that contain Tailwind class names.
- **`theme`**: Defines project’s **color palette, fonts, breakpoints, border radius values, etc.**
- **`extend`**: Extends the default spacing scale. Used to **add new values without removing defaults**.
- **`plugins`**: Allows adding custom utilities and components using JavaScript instead of CSS.

---

#### 4. Why do we have a `.postcssrc` file?

- `.postcssrc` is a configuration file for **PostCSS**.
- It tells **Parcel** to use PostCSS for processing Tailwind CSS.
- Required at the **root level** of the project.

---

#### 5. What are the pros and cons of using Tailwind CSS?

**PROS:**

1. All styles are inside JS files, avoiding switching between JS and CSS files.
2. **Lightweight**: Only used classes are included in the final CSS bundle.
3. Can build **complex UI** with Tailwind.
4. **Responsive UI** without writing media queries.
5. Supports **hover and focus states** easily.
6. **Prevents redundancy**, ensuring minimal CSS code.

**CONS:**

1. Excessive use of utility classes makes code **less readable**.
2. **Learning curve**: Tailwind has its own learning process before becoming productive.
