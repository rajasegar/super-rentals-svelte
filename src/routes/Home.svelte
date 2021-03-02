<script>
  import { link } from 'svelte-routing';
  import Jumbo from '../Jumbo.svelte';
  import Rental from '../Rental.svelte';

  let rentals = [];
  (async () => {
    const response = await fetch('/rentals.json');
    const data = await response.json();
    console.log(data);
    rentals = data.data;
  })();
</script>
<style>

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

  
   h2 {
    font-size: 3.2em;
    margin-top: -25px;
  }

   p {
     margin-bottom: 25px;
   }

   span {
     font-size: 140%;
    margin: 50px auto 20px;
    display: block;
    text-align: center;
    font-style: italic;
   }

   input {
     padding: 11px;
    font-size: 18px;
    width: 500px;
    margin: 20px auto 50px;
    background-color: rgba(255,255,255,.75);
    border: 1px solid #d3d3d3;
    display: block;
   }
</style>

<Jumbo>
  <h2>Welcome to Super Rentals!</h2>
  <p>We hope you find exactly what you're looking for in a place to stay.</p>
  <a href="/about" use:link class="button">About Us</a>
</Jumbo>
<div class="rentals">
  <label>
    <span>Where would you like to stay?</span>
    <input type="text"/>
  </label>
  <ul class="rentals">
    {#each rentals as rental}
    <Rental rental={rental.attributes}/>
    {/each}
  </ul>

</div>
