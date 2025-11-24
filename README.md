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

## Project Structure (main components)

- **`src/index.js`**

  - React entry point
  - Renders the `<App />` component into the `root` element

- **`src/components/App.js`**

  - Main component that holds the state for all items
  - Functions:
    - `handleAddItems` – adds a new item to the list
    - `handleDeleteItem` – removes an item by `id`
    - `handleToggleItem` – toggles `packed` status
    - `handleClearList` – clears all items after confirmation
  - Renders:
    - `<Logo />`
    - `<Form />`
    - `<PackingList />`
    - `<Stats />`

- **`src/components/Logo.js`**

  - Displays the app title "Far Away" with emojis

- **`src/components/Form.js`**

  - Controlled form component
  - Local state:
    - `description` – item text
    - `quantity` – selected quantity
  - On submit:
    - Prevents default form behavior
    - Validates that description is not empty
    - Creates a new item object: `{ description, quantity, packed: false, id: Date.now() }`
    - Passes the new item up via `onAddItems`

- **`src/components/PackingList.js`**

  - Receives the `items` array and handler functions as props
  - Local state:
    - `sortBy` – current sort type (`"input"`, `"description"`, `"packed"`)
  - Creates `sortedItems` based on the selected sort option
  - Renders:
    - `<Item />` list
    - Sorting `<select>` dropdown
    - "Clear list" button

- **`src/components/Item.js`**

  - Displays one list item:
    - Checkbox to toggle `packed`
    - Quantity + description
    - Delete button
  - Calls `onToggleItem` and `onDeleteItem` handlers via props

- **`src/components/Stats.js`**
  - Shows summary information at the bottom
  - If no items:
    - Shows message: _"Start adding some items to your packing list"_
  - If there are items:
    - Calculates:
      - `numItems` – total count
      - `numPacked` – packed items
      - `percentage` – rounded packed percentage
    - Renders different message when `percentage === 100`

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
