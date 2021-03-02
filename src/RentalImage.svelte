<script>
  export let image;
  export let title;
</script>

<style>
  .image {
    position: relative;
    cursor: pointer;
    border: none;
    background: 0 0;
    z-index: 1;
    flex-grow: 0;
    flex-basis: 150px;
    margin: 20px 25px;
    text-align: center;
  }

  .image:after {
    content: "";
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
    margin: -20px;
    padding: 20px;
    border-radius: 5px;
    background: #016aba;
    opacity: 0;
    transition: opacity .25s ease-in-out;
}

  img {
    max-width: 100%;
    border-radius: 5px;
  }

  small {
    display: block;
    margin-top: 5px;
    margin-bottom: -15px;
    text-align: center;
    color: #016aba;
    position: relative;
  }


</style>
    <button class="image " type="button">
      <img src="{image}" alt="A picture of {title}">
      <small>View Larger</small>
    </button>
