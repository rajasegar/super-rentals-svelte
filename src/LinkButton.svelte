<script>
  import { link } from 'svelte-routing';
  export let url;
</script>

<style>
  a {
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

a:hover {
  opacity: 1;
}


</style>

<a href="{url}" use:link>
  <slot></slot>
</a>
