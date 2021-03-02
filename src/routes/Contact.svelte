<script>
  import Jumbo from '../Jumbo.svelte';
  import LinkButton from '../LinkButton.svelte';
</script>

<style>
   h2 {
    font-size: 3.2em;
    margin-top: -25px;
  }
</style>
<Jumbo>
  <h2>Contact Us</h2>
  <p>
  Super Rentals Representatives would love to help you
choose a destination or answer any questions you may have.
  </p>
  <address>
    Super Rentals HQ
    <p>
      1212 Test Address Avenue<br>
      Testington, OR 97233
    </p>
    <a href="tel:503.555.1212">+1 (503) 555-1212</a><br>
    <a href="mailto:superrentalsrep@svelte.dev">superrentalsrep@svelte.dev</a>
  </address>
  <LinkButton url="/about">About</LinkButton>

</Jumbo>
