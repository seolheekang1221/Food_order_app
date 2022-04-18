# Food Order App
This app a a Food Order App built using React and Node.js

# Objective
- Using the useEffect for CSS animation and implemented responsive design with React Scripts, and Web-vitals
- Implemented REST API using Firebase service for customers  to order from restaurant by Fetching some data and HTTP requests
- Passed a prop through multiple levels of components by ReactDOM
- Managed state by React Hook and dispatch an action by useReducer
- Parsed to the ref prop on component function by useRef
- Used useContext for accessing to createContext

# Features
1. React Portal for backdrop and overlay
Behind the modal overlay which blocks interaction with the rest of the page

2. Passed a prop through multiple levels of components 
1. Open Cart
App.js - showCartHandler => Header.js - onShowCart => HeaderCartButton - onClick => onShowCart

2. Open Close
"onClose" is passed
App.js - hideCartHandler => Cart.js - onClose => Model.js => Backdrop

3. store => convention in react state management

4. Used useContext react hook for access to cartContext in HeaderCartButton.
Access to cart context dot items and length is for get the array of cart items. 
Reduce that allows to transform an array of data in a single value in numberOfCartItems.

5. CartProvider.js => For re-evaluated whenever the cart data changes, it is imported useReducer which allow them to mange state
-> cartReducer receive a state object and action which is dispatched such like "ADD" "REMOVE" "CLEAR" in CartProvider.js. useReducer(react hook) which allow them to mange state and dispatchCartAction is function dispatch an action to the reducer

6. MealItemForm.js => Parsed to the ref prop on component function by using the "useRef"

7. Whenever i push item a second or thihrd times, it can be aggregated together into one item.
I am reaching existing items in the cart by findindex which is built-in method about finding the index of an item in array and if item.id === action.item.id, it will return true. If the item is same id with the item I want to add, it will be dispatched. If a item that i want to add already in the cart, i will make const existingCartItem = state.items[existingCartItemIndex];
If existingCartItem is already in array, updateditem will be set existingCartItem and be updated amount: existingCartItem.amount + action.item.amount. And updateItems is same with new array which is existing items and it is updatedItems = […state.items];. I copy the old objects and overwrite it. updatedItems[existingCartItemIndex] = updatedItem; Everything is showing the cart items array. In else case, updatedItems is new item and copy action item and updatedItems set to state.items.concat, and add updatedItem.

# Deployment
This app is deployed and hosted using Netlify
<a href="https://famous-gingersnap-88a91f.netlify.app/" rel="nofollow">Food Order App<a/>

# Demo
![Hnet com-image (1)](https://user-images.githubusercontent.com/71479209/163729742-f953308a-d259-46c4-85a8-40b73e07b210.gif)

# Screen Shot

### 1. Add Items to put in the cart

![1](https://user-images.githubusercontent.com/71479209/163729657-88cec191-a85f-47cd-be36-def28d582fa5.png)

### 2. Added Items in the cart
![2](https://user-images.githubusercontent.com/71479209/163729659-673b0a2c-ffc7-4964-a3d8-745d71bd8f44.png)

### 3. Checkout information for order
![2-1](https://user-images.githubusercontent.com/71479209/163729662-7e16c4aa-2a40-444c-9e9a-97cc9c7a34a5.png)

### 4. Check validation about Checkout information
![2-1-1](https://user-images.githubusercontent.com/71479209/163729665-37097d4c-8aef-4167-aa85-ecc90c298b2d.png)


### 5. Success the order
![3](https://user-images.githubusercontent.com/71479209/163729678-119e0ccc-2ef1-49a7-8dca-b12602efaa4f.png)

### 6. Confirm the order in Firebase
![2-2](https://user-images.githubusercontent.com/71479209/163729672-0e5e2d4a-6bcc-4f59-a16d-4d05daf67436.png)

# Clone this repository
git clone https://github.com/seolheekang1221/Food_order_app
# Getting Started
1. Go to Food_order_app directory
```sh
cd Food_order_app
```
2. Install dependencies and start the server
```sh
npm install
```
3. run the development server
```sh
npm run dev
# or
yarn dev
```
4. Open http://localhost:3000 with your browser to see the result.

