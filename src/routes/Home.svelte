<script>
  import { link } from 'svelte-routing';
</script>
<style>
  .right {
    float: right;
  }

  .svelte {
    background: url(/logo.svg) no-repeat;
    background-size: contain;
    height: 200px;
    width: 200px;
    top: -25px;
  }

  .button {
  padding: 10px 30px 10px;
  text-decoration: none;
  color: #fff;
  background: #016aba;
  border-radius: 5px;
  border: none;
  font-size: 20px;
  font-weight: bold;
  opacity: 0.9;
  display: inline-block;
}

.button:hover {
  opacity: 1;
}

  
</style>

<div class="jumbo">
  <div class="right svelte"></div>
  <h2>Welcome to Super Rentals</h2>
  <p>We hope you find exactly what you're looking for in a place to stay.</p>
  <a href="/about" use:link class="button">About Us</a>
</div>
<div class="rentals">
  <label>
    <span>Where would you like to stay?</span>
    <input type="text"/>
  </label>
  <ul class="rentals">
  </ul>

</div>
