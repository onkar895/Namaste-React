# 🚀 NAMASTE-REACT COURSE EPISODE-2

## Chapter 02 - Igniting our App

### Q: What is NPM?

**A:** npm is a package manager and repository for libraries, frameworks, and tools. It is the default package manager for Node.js projects and is installed along with Node.js. The **NPM Registry** hosts public and private packages, and the **NPM CLI** (Command-Line Interface) is used to manage dependencies and interact with this registry.

### Q: Difference between Caret (^) and Tilde (~)

- **Caret (^):** Allows updates that do not change the first non-zero version number (e.g., `^1.2.3` allows `1.x.x` updates but not `2.x.x`).
- **Tilde (~):** Allows patch updates but locks the minor version (e.g., `~1.2.3` allows `1.2.x` but not `1.3.x`).

### npm Alternative

**Yarn** is an alternative package manager.

### How to Initialize npm?

- `npm init` → Creates a `package.json` file.
- `npm init -y` → Skips setup and automatically generates `package.json`.

---

### Q: What is Parcel/Webpack? Why do we need it?

**A:** Parcel and Webpack are **bundlers** that optimize web applications by managing dependencies, improving performance, and reducing build time.

#### **Parcel Features:**

- **HMR (Hot Module Replacement):** Automatically updates modules without reloading the page.
- **File Watcher Algorithm:** Built with C++ for efficient tracking of file changes.
- **Minification:** Reduces file size by removing unnecessary code.
- **Dev & Production Builds:** Provides optimized builds for different environments.
- **Super-fast building algorithm:** Enhances development speed.
- **Image Optimization & Caching:** Improves performance and reduces reprocessing.
- **Zero Configuration:** Works out of the box with minimal setup.
- **Automatic Code Splitting:** Enhances load time efficiency.

#### **Installation & Commands:**

```sh
npm install -D parcel  # Install as a development dependency
npx parcel <entry_point>  # Run development build
npx parcel build <entry_point>  # Create a production build
```

---

### Q: What is .parcel-cache?

**A:** `.parcel-cache` speeds up builds by storing project metadata and avoiding redundant reprocessing.

---

### Q: What is npx?

**A:** `npx` executes npm packages without installing them globally. It is included with npm (v5.2+).

---

### Q: What is Node-Modules?

**A:** The `node_modules` folder stores installed dependencies. It acts as a local database for required packages.

---

### Q: Difference between Dependencies and DevDependencies

- **Dependencies:** Required for the app to function (e.g., React, Angular, Express).
- **DevDependencies:** Only needed during development (e.g., Parcel, Webpack, Jest).

#### **Installation:**

```sh
npm install --save-dev  # Adds to devDependencies
npm install --save  # Adds to dependencies (default)
```

---

### Q: What is Tree Shaking?

**A:** Tree shaking removes unused code, optimizing the final bundle size.

---

### Q: What is Hot Module Replacement (HMR)?

**A:** HMR updates modules in real-time without a full page reload, retaining application state.

---

### Q: 5 Superpowers of Parcel

1. **HMR (Hot Module Replacement)** – Updates modules without reloading.
2. **File Watcher Algorithm** – Monitors file changes efficiently.
3. **Minification** – Reduces file size for better performance.
4. **Image Optimization** – Compresses images automatically.
5. **Caching during Development** – Speeds up the build process.

---

### Q: What is .gitignore? What should we add to it?

**A:** `.gitignore` tells Git which files to exclude from version control.

#### **Common Entries:**

```gitignore
# Ignore system files
.DS_Store

# Ignore dependencies
node_modules/

# Ignore environment files
.env

# Ignore logs
logs/
```

---

### Q: Difference between package.json and package-lock.json

- **package.json:** Contains project metadata, dependencies, and scripts.
- **package-lock.json:** Locks exact versions of installed dependencies to ensure consistency.

#### **Example Dependency Versions in package.json:**

```json
"dependencies": {
  "react": "^18.2.0",
  "react-dom": "^18.2.0"
}
```

- `^18.2.0`: Updates minor/patch versions but not major versions.
- `~18.2.0`: Updates only patch versions.

#### **Why shouldn't we modify package-lock.json?**

It ensures consistent dependencies across environments. Modifying it manually can break installations.

---

### Q: Should we push node_modules to Git?

**A:** No, because it is large (100MB+) and can be recreated using `npm install`. Use `.gitignore` to exclude it.

---

### Q: What is the dist folder?

**A:** The `dist/` folder contains the optimized, minified, and production-ready build of the application.

---

### Q: What is Browserslist?

**A:** Browserslist configures supported browsers for frontend apps, optimizing compatibility.

#### **Example Browserslist Configuration:**

```json
"browserslist": [
  "> 0.5%",
  "last 2 versions",
  "not dead"
]
```

---

### Conclusion 🎯

This chapter covers essential topics for setting up a React app using modern tools like npm, Parcel, and Browserslist. 🚀
