# Far Away – Travel Packing List

A small React app that helps you prepare for a trip by managing a packing list.  
You can add items, mark them as packed, delete them, clear the list, and sort the items in different ways.

---

## Features

- **Add items**

  - Choose a quantity (1–20)
  - Type an item description
  - Submit the form to add it to the list

- **Toggle packed status**

  - Click on the checkbox to mark an item as packed / unpacked
  - Packed items are displayed with a line-through style

- **Delete a single item**

  - Remove any item by clicking the ❌ button

- **Clear the entire list**

  - "Clear list" button removes all items
  - Shows a `window.confirm` dialog to avoid accidental deletion

- **Sorting options**

  - Sort by input order
  - Sort alphabetically by description
  - Sort by packed status (unpacked first, then packed)

- **Live stats footer**
  - Shows how many items are on the list
  - Shows how many items are already packed
  - Displays the packing progress in %
  - Special message when everything is packed 🎉

---

## Technologies Used

- React
- JavaScript (ES6+)
- JSX
- CSS (custom `index.css` styling)

---

## How to Run the Project

1. Make sure **Node.js** and **npm** are installed.
2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the development server:

```bash
   npm start
```

4. Open the app in your browser at:

```bash
   http://localhost:3000
```
