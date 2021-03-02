<script>
  import {onMount} from 'svelte';
  import { Router, link, Route } from 'svelte-routing';
  import Home from './routes/Home.svelte';
  import About from './routes/About.svelte';
  import Contact from './routes/Contact.svelte';

  export let url = "";

  let count = 0;
  onMount(() => {
    const interval = setInterval(() => count++, 1000);
    return () => {
      clearInterval(interval);
    };
  });
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }

  :global(body) {
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
  }

  .container {
    max-width: 1024px;
    min-height: 100vh;
    background: #f9f9f9;
    margin: 0 auto;
  }

  .menu {
    height: 4em;
    background-color: #e46855;
  }

  .menu h1 {
  position: relative;
  padding: 5px 0 0 8px;
  color: #f9f9f9;
  font-size: 1.8em;
  font-style: italic;
}

a, .links {
  display: inline-block;
}

 a {
  text-decoration: none;
  padding: 0 15px;
  color: #fff;
  font-size: 20px;
  font-weight: bold;
}

 a:hover,
 a.active {
  opacity: 1;
}

 .links {
  padding: 0 21px;
}

 .links a {
  position: relative;
  bottom: 5px;
}


  .body {
    padding: 15px;
  }
</style>

<div class="container">
<Router url="{url}">
  <nav class="menu">
    <a href="/" use:link><h1>Super Rentals</h1></a>
      <div class="links">
    <a  href="/about" use:link>About</a>
    <a href="/contact" use:link>Contact</a>
      </div>
  </nav>
  <div class="body">
    <Route path="/about" component="{About}"/>
    <Route path="/contact" component="{Contact}"/>
    <Route path="/" component="{Home}"/>
  </div>
</Router>
</div>
