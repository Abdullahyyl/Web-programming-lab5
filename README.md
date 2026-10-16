# Simple Product Dashboard (React + Vite)

This is my Assignment 5 for Web Programming. It is a small React app that shows a list of products. The user can show or hide the list with a button and type their name into an input to get a greeting. All the data is hard-coded, and I only used what we learned in the lecture (`useState`, props, `children`, `.map()`, conditional rendering, controlled inputs).

## How to run

```
npm install
npm run dev
```

Then open the link that Vite prints in the terminal (usually http://localhost:5173).

## File organization

```
assignment1
 ├─ src/
 │   ├─ components/
 │   │   ├─ Card.jsx
 │   │   ├─ Product.jsx
 │   │   └─ ProductList.jsx
 │   ├─ App.jsx
 │   └─ main.jsx
 ├─ index.html
 └─ package.json
```

- `index.html`: the page that Vite loads. It only has the `#root` div.
- `src/main.jsx`: puts the `App` component into the `#root` div.
- `src/App.jsx`: the root component. It keeps two states with `useState`: `showProducts` (true/false) and `name` (string). It has the heading, the Show/Hide button, the controlled name input, the `Hello, {name}` paragraph, and it shows `ProductList` only when `showProducts` is true.
- `src/components/ProductList.jsx`: has the static products array. It uses `.map()` to make one `Product` for each item and uses `product.id` as the key (not the index).
- `src/components/Product.jsx`: shows one product (title and price). It only uses props, has no state, and is wrapped inside `Card`.
- `src/components/Card.jsx`: a layout component. It takes `children` and puts a border, padding and margin around them. It does not know what is inside it.

## Challenges I faced

- At first I did not fully understand controlled inputs. I had to understand that the input's `value` comes from the `name` state and `onChange` updates it, so React is always in control of the input.
- I had to remember to use `product.id` as the `key` and not the array index, and to render the products with `.map()` instead of writing every `Product` by hand.
- Understanding `children` in `Card` took me some time, because `Card` shows whatever is put between its tags.
- Git was new for me. I ran `git init` in the wrong folder (Desktop) the first time, so I had to delete that repo and start again inside the project folder. I also learned to make small commits with clear messages and to keep `node_modules` out of the repo with `.gitignore`.
