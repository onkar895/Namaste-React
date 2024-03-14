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

-   React Testing Library :

    -   **React Testing Library** builds on top of DOM Testing Library by adding APIs for working with React components.
    -   The **React Testing Library** is a very light-weight solution for testing React components. It provides light utility functions on top of react-dom and react-dom/test-utils, in a way that encourages better testing practices.
