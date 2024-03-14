# TIME FOR TEST :

-   So, basically there are 3 types of testting that developer can do :

    -   **Unit Testing** :

        -   **What it is**: Testing small parts, like individual components, in your React app separately.
        -   **Example**: Testing a button or a form field to make sure it works on its own.
        -   **Why it's important**: Helps catch bugs early and ensures each piece of your app works correctly.

    -   **Integration testing** :

        -   **What it is**: Testing how different parts of your app work together. So this type of testing is known as integration testing where multiple components involves and talking to each other.
        -   **Example**: Checking if a form submission updates a list correctly or if a button click triggers the right action.
        -   **Why it's important**: Ensures that different components can communicate and function correctly as a whole.

    -   **End to End Testing (e2e testing)** :

        -   **What it is**: Testing your entire app from start to finish, just like a real user would. That means testing the react application as soon as the user lands on the website to the user leaves the website it will test all the floors.
        -   **Example**: Automating actions like signing in, navigating through pages, and submitting forms.
        -   **Why it's important**: Validates the overall functionality and flow of your app, ensuring a smooth user experience.

-   So, **unit testing** checks individual parts, **integration testing** checks how they work together, and **end-to-end testing** checks the whole app like a real user. Each type serves a specific purpose in ensuring your React app functions correctly.

## Libraries to test React Applications :

-   **React Testing Library** :

    -   **React Testing Library** builds on top of DOM Testing Library by adding APIs for working with React components.
    -   The **React Testing Library** is a very light-weight solution for testing React components. It provides light utility functions on top of react-dom and react-dom/test-utils, in a way that encourages better testing practices.
    -   React Testing library uses something Known as **Jest**.

-   **Jest** :

    -   **Jest** is a delightful **javascript testing framework** with a focus on simplicity.
    -   React testing Library uses **jest** behind the scene.
    -   It works with projects using: **Babel, TypeScript, Node, React, Angular, Vue and more!**

### Setting up the testing :

-   Installation of react testing library:

    ```js
    **npm install --save-dev @testing-library/react**.
    ```

-   After Installating the **react testing library** you need to install **jest** also.
-   Jest Installation :

```js
**npm install --save-dev jest**.
```

-   Installation with babel then you need to install additional dependenncies : **npm install --save-dev babel-jest @babel/core @babel/preset-env**
-   After installation You have to configure it :

    ```js
    **babel.config.js**
    module.exports = {
    presets: [['@babel/preset-env', {targets: {node: 'current'}}]],
    };
    ```

-   Remembering the most important things :

    -   So parcel already uses babel behind the scenes.
    -   And parcel has its own configuration for babel.
    -   Now we are trying to add extra configuration in file **babel.config** so the parvel will gets confused.
    -   The parcel will automatically overrides or conflicts the **babel.config**.
    -   So for that, we will have to change the parcel's behaviour to accomodate to use babel along with jest. We will have to make some chages in our parcel.

-   **Usage with other tools** :

    -   While Parcel includes transpilation by default, you may still need to use Babel with other tools such as test runners like **Jest**, and **linters like ESLint**.
    -   If this is the case, you may not be able to completely remove your Babel config.
    -   You can make Parcel ignore your Babel config instead, which will have performance benefits and prevent the other issues described above.
    -   To disable Babel transpilation in Parcel, override the default Parcel config for JavaScript to exclude @parcel/transformer-babel.

-   Configuration of parcel config file to disable default babel transpilation.

```js
**.parcelrc**
{
  "extends": "@parcel/config-default",
  "transformers": {
  "\*.{js,mjs,jsx,cjs,ts,tsx}": [
  "@parcel/transformer-js",
  "@parcel/transformer-react-refresh-wrap"
  ]
  }
  }
```

-   Now You have successfully done with Configuration of parcel config file to disable default babel transpilation.
-   Next step is you have to write the **jest configuration**

```js
npx jest --init
```

-   This command creates a jest.config file in the root level of your react application.
-   After running the above command it will ask for the **node or jsdom** ,Now select **jsdom** to go forward.
-   **jsdom library**:-
    -   Test cases can not run on browser, so **jsdom** provide an runtime environment where the test cases will be executed.
-   Do you want Jest to add coverage reports? ... yes
-   Which provider should be used to instrument code for coverage? » babel
-   Automatically clear mock calls, instances, contexts and results before every test? » ... yes
-   and now you will get the configuration file which is **jest.config**
