
# TBay

This repository contains the frontend of **TBay**, a platform for renting, buying, and selling products. Built with React, TypeScript, and Vite, the project utilizes a robust stack of tools and libraries to provide a seamless user experience.

### 🚀 Features

- **Authentication**: Token-based login and registration with protected routes.
- **Product Management**: Create, update, delete, and list products.
- **Shopping Cart**: Add, edit, and remove items for buying or renting.
- **Order Management**: View and manage placed orders.
- **Responsive Design**: Optimized for various screen sizes using Mantine components.

### 🛠 Tech Stack

- **Frontend**: React, TypeScript, Vite
- **State Management**: Zustand
- **Styling**: Mantine UI
- **GraphQL**: Apollo Client
--
- **Backend**: Nestjs
- **ORM**: Prisma
- **Query**: Graphql
- **GraphQL Server**: Apollo Server

---
# 📦 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/Zulker-Nien/tbay.git
   ```

2. Navigate to the project directory:
   ```bash
   cd tbay
   ```

3. Initialize the submodules:
   ```bash
   git submodule init
   
   # This part initializes the repository links of the respective submodules
   ```

4. Populate the submodules:
   ```bash
   git submodule update

   # This part pulls the data inside of each of the respective submodules
   # Perform a pull request 
   ```

5. Build your project:
   ```bash
   docker-compose build --no-cache
   ```
   `The --no-cache flag forces Docker to rebuild all layers from scratch, ignoring cached layers.`

6. Start all the processes:
   ```bash
   docker-compose up
   ```

#### You now have installed everything and the instances are running.
Go to `http://localhost:5173`

---

### 📚 Scripts

- The prisma generate and seed functions are handled automatically so you do not need to manually run them.
- Run **`docker-compose exec backend npx prisma migrate`** for any schema migration `to be done only after running docker-compose up`


### 🔑 Environment Variables

`You don't need to create environment variables. I have already added required envs to the docker-compose.yml file`


### 🏗 Project Structure

`Frontend`
- **`/src`**: Contains the source code.
  - **`/components`**: Reusable UI components.
    - **`/product`**: Product Implementation.
    - **`/cart`**: Cart Implementation.
    - **`/navbar`**: Navbar Implementation.
    - **`/dashboardTabs`**: Tabs containing protected user views.
  - **`/pages`**: Application pages (e.g., Home, Dashboard).
  - **`/store`**: Zustand stores for state management.
  - **`/graphql`**: Queries and mutations for GraphQL.
  - **`/types`**: TypeScript types and interfaces.
  - **`/hooks`**: Useful custom hooks
- [User flow Diagram](https://miro.com/app/board/uXjVLwuiGCE=/?share_link_id=784278555308)
- [Authentication flow Diagram](https://miro.com/app/board/uXjVLwvVAOM=/?share_link_id=530700702074)
- [Database Schema](https://miro.com/app/board/uXjVLwkJD6g=/?share_link_id=844530873010)


`Backend`
- The backend structure and proper documentation can be found with running a command in a separate terminal instance: `docker-compose exec backend npm run doc` then go to `localhost:3001` once all the processes are running.
   
### 📖 Key Libraries

- **Mantine**: UI components and hooks for responsive design.
- **Apollo Client**: Simplified interaction with GraphQL APIs.
- **Zustand**: Lightweight and efficient state management.
- **ESLint**: Ensures code quality and consistency.


### ╔ Corner Cases Handled

- Logged in users cannot go to the signin/ register pages via the unprotected routes.
- Validation upon every step of the create form.
- Instantly handles the refetching of the created data.
- Updated cart is shown instantly.

### ╝ Corner Cases Not Handled

- Fetching tokens over http-only cookies. Currently stored in localhost.
- Cart Items cannot be edited, only deleted
- If user A has an item in cart, and another user buys the item prior to user A resulting in an out of stock exception, the user A will be posed with an error only after ordering. `Whereas: the cart should be disabled in the first place.` 
- Navigation in mobile screen not updated.

### Comments

- A design system could help add better visual aspects of the clientside
- Role based Authentication could turn it into an actual secured product.
- Prisma ORM handles the Database relations by itself. While it automates, the ERD contains unnecessary additions. `TypeORM/MikroORM in my opinion provides with more manual access and validation functionality`
- Ability to extent rent period and return rented products to update product stock accordingly could be added.
- Wishlist, product rating, coupons and discount could also be incorporated.

### 🙌 Acknowledgements

Special thanks to Sazim for this challenge.


### 🧑‍💻 Author

Developed by **Zulker Nien**.
