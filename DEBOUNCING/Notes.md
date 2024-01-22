# Debouncing :

-   **Debouncing** is a technique used to limit the number of times a function gets executed based on how frequently it's called. It's often used in cases where a function is triggered repeatedly in a short amount of time, such as in response to a user typing in an input field or scrolling down a page.

-   When you debounce a function, you specify a wait time. After the user stops interacting with the element for the specified amount of time, the function will be executed. **This prevents the function from being executed too often, which can improve performance and prevent unnecessary API calls.**

-   Debouncing can help you to **improve the performance of your React applications by reducing unnecessary function calls, you can prevent unnecessary API calls and improve the overall user experience.**

-   There are a few different ways to implement debouncing in React:

    -   One common way is to use a **debounce function**. This function takes a function as an argument and returns a new function that will only be executed after the specified wait time has passed.

    -   Another way to implement debouncing in React is to use React's built-in **useEffect hook**. This hook allows you to run a function after a specific delay. To debounce a function using useEffect, **you can pass the function to the useEffect hook with a wait time as the second argument.**

## How debouncing works in React, this is the example of SearchBar in my YouTube project :

-   Use a debouncing function:
    You can implement a debouncing function, often using setTimeout, to delay the execution of the actual function.

```js
const [searchQuery, setSearchQuery] = useState("");
// console.log(searchQuery)

useEffect(() => {
    // Make an API call after every key press
    // But if the difference between 2 API calls is < 200ms then decline the API call.
    const timer = setTimeout(() => {
        getSearchSuggestions();
    }, 200);

    return () => {
        clearTimeout(timer);
    };
}, [searchQuery]);
// I don't want to make an API call only at the first time; I want to make an API call everytime my searchQuery changes, taht why I'm taking searchQuery in the dependency array.

/**
 * If I want to search for india
 * 1. key - i
 * - render the component
 * - call useEffect()
 * - start the timer => make an api call after 200ms
 *
 * 2. key - in
 * (Evenbefore 200ms if I press the key it will first destroy the component and when it destroying the component, it will call clearTimeOut)
 * - destroy the component(call useEffect return method)
 * - re-render the component
 * - call useEffect()
 * - start the timer => make an api call after 200ms and this timer is new everytime searchQuery changes.
 */

const getSearchSuggestions = async () => {
    try {
        const data = await fetch(YOUTUBE_SEARCH_API + searchQuery);
        const response = await data.json();
        console.log(response);
    } catch (error) {
        console.error("Error while fetching search suggestions:", error);
    }
};
```

## Lets assume the exmaple of Youtube Search Bar:

-   So, when you start writing in search bar it will start showing you suggessions whatever you search for.
-   Suppose I search for **India**, then it start showing me suggessions about **India.**
-   So basically **it makes an API call and shows you suggessions.**
-   Go to the inspect on youtube homepage and see how it makes an API call for every character you search.
-   If you search 4 characters word then it will make four API calls.
-   Its useless right. So there is **no need to make an multiple API calls** for only 1 word whatever you are typing.
-   If you search on FlipKart, then you will find out that, they are not making an API calls for every key press.
-   If you are typing very slow, then it will definately make an API call for every and each key press.
-   Why are you want to make an API calls in every key Press.
-   If I want to search **cloths** and I'm typing it very fast so we **need to only make an API call when I finished writing something.** That's the better way right?
-   So, this concept is known as **Debouncing.**
-   Suppose I'm typing something very fast in search bar, so what happens is, it just skips some of the events.
-   So, the concept behind this is **Debouncing.**

## Better Explaination :

-   Imagine using the search bar on YouTube. As you type, the system generates suggestions in real-time.
-   Each keystroke triggers an API call to fetch relevant suggestions, leading to multiple unnecessary calls, especially if you type quickly.
-   This is where the concept of debouncing comes into play, optimizing the efficiency of API calls.

## Debouncing :

-   Debouncing says, suppose if you are **typing something very fast , then the difference between the two key strokes is very less.**
-   And suppose if you are **typing something very slow , then the difference between the two key strokes is very high.**

## Debouncing with 200ms :

-   If difference between 2 key press is less than 200ms - Decline API Call

-   And if difference between 2 key press is greater than 200ms - make an API Call

-   So, If you are **searching very fast on Youtube**, it still makes an API call for every character. **But the Debouncing is there and it's very less. Not even 200ms, less than this.**

-   **So why youtube has very less debouncing?** Because they want to give a much more better user experince. and may be there API's are also faster.

-   That's why, if you will search something on Youtube, it will almost give you the results for every key stroke.

## Performance - Why Debouncing Matters:

-   Debouncing is crucial for optimizing performance by minimizing unnecessary API calls.

-   The main goal of debouncing is to optimize performance and prevent unnecessary function executions, especially in scenarios where the function might be triggered rapidly or repeatedly.

-   Consider a scenario where a user searches for "Iphone 14 Max" with 14 letters. Without debouncing, a thousand searches could result in a staggering 14,000 API calls.

-   However, with **debouncing**:

    -   **Optimized Performance:** Even with 1000 searches, making API calls only when necessary significantly reduces the load on the server, resulting in a more efficient and performant system.

    -   **Enhanced User Experience:** Debouncing ensures that API calls are made judiciously, striking a balance between real-time suggestions and server load. This leads to a smoother and more responsive user experience.

-   If you typing **Iphone 14 Max** = 14 letter \* search for 1000 times = It will make 14000 API Calls.
-   But if you are using **Debouncing** here , and if we make 3 API calls \* search for 1000 times = It will only make 3000 API Calls.
-   So for improve the performance , debouncing will be better right?
