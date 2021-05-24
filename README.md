
# react-router
Summary about react-router
- use `react-router-dom` to route
- wrap `BrowserRouter` around `App` to make routing works
- use `<Route path="/welcome">` to wrap around components that want to show if path is `/welcome` 
- use `<Route path="/product-detail/:productId">` :productId is query params that can access with 
```javascript
const params = useParams()
return (
        <section>
           <h1>Product Detail</h1> 
           <p>{params.productId}</p>
        </section>
  )
```
- use `Link` to navigate to destination path
- use `NavLink` to navigate with style, `activeClassName` is class when route is active
```javascript
<NavLink activeClassName={classes.active} to="/welcome">Welcome</NavLink>
```
- use `Switch` to display only matched route
```javascript
<Switch>
     <Route path="/welcome">
       <Welcome />
     </Route>
     <Route path="/products" exact> // add exact props match only if path is exactly
       <Products />
     </Route>
     <Route path="/products/:productId">
       <ProductDetail />
     </Route>
</Switch>
```
- Nested Route can use Route in each component to create nested route
```javascript
// App.js
<Route path="/welcome">
    <Welcome />
</Route>
```
```javascript
// Welcome.js
<section>
      <h1>The Welcome Page</h1>
      <Route path="/welcome/new-user"> 
// when user enter '/welcome/new-user' will show this component too      
        <p>Welcome new user</p>
      </Route>
</section>
```
- use `Redirect` to redirect to destination path 
```javascript
  <Route path="/" exact>
    <Redirect to="/welcome" />
  </Route>
```
