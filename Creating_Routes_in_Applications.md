
# Creating Routes in Applications

1. **Install React Router Dom**:  
   ```bash
   npm install react-router-dom
   ```

2. **Set Up `App.js`**:
   - **Import Required Functions**:
     ```javascript
     import { createBrowserRouter, RouterProvider } from 'react-router-dom';
     ```

3. **Create `appRouter`** using `createBrowserRouter`:
   - **Define Routes** as an array of objects, where each object has:
     - `path`: The URL path.
     - `element`: The component to render for that path.
     ```javascript
     const appRouter = createBrowserRouter([
       {
         path: "/",
         element: <HomeComponent />,
         children: [
           { path: "about", element: <AboutComponent /> },
           { path: "contact", element: <ContactComponent /> }
         ]
       }
     ]);
     ```

4. **Provide the Router** in `App.js`:
   - Use `RouterProvider` to set up the router.
     ```javascript
     function App() {
       return <RouterProvider router={appRouter} />;
     }
     ```

5. **Children Array of Objects**:
   - All routes under `/` are defined in the `children` array.
   - **`Outlet` Component**:
     - The `children` routes are rendered inside the `Outlet` component provided by React Router.
