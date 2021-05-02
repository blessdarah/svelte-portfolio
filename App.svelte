<script>
  import Button from "./Button.svelte";

  import Route from "./Route/Route";
  import Router from "./Route/Router";
  import NotFound from "./Route/NotFound";

  import Home from "./pages/home";
  import Services from "./pages/services";
  import About from "./pages/about";
</script>

<style>
  main {
    font-family: sans-serif;
    text-align: center;
  }
  nav {
    margin-top: 2rem;
  }
  a {
    padding: 0.4rem 1rem;
    background: tomato;
    margin-top: 1rem;
    text-decoration: none;
    color: #fff;
    border-radius: 2px;
  }

  a:hover {
    background: rgb(226, 76, 50);
  }
</style>

<main>
  <nav>
    <a href="/">home</a>
    <a href="/about">about</a>
    <a href="/services">services</a>
  </nav>

  <Router>
    <Route path="/" component={Home} />
    <Route path="/services" component={Services} />
    <Route path="/about" component={About} />

    <NotFound>
     <p>No page found</p>
    </NotFound>
  </Router>
</main>