# Debouncing :

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

-   Consider a scenario where a user searches for "Iphone 14 Max" with 14 letters. Without debouncing, a thousand searches could result in a staggering 14,000 API calls.

-   However, with **debouncing**:

    -   **Optimized Performance:** Even with 1000 searches, making API calls only when necessary significantly reduces the load on the server, resulting in a more efficient and performant system.

    -   **Enhanced User Experience:** Debouncing ensures that API calls are made judiciously, striking a balance between real-time suggestions and server load. This leads to a smoother and more responsive user experience.

-   If you typing **Iphone 14 Max** = 14 letter \* search for 1000 times = It will make 14000 API Calls.
-   But if you are using **Debouncing** here , and if we make 3 API calls \* search for 1000 times = It will only make 3000 API Calls.
-   So for improve the performance , debouncing will be better right?
