<script>
  import { link } from 'svelte-routing';
  export let rental;
</script>

<style>
  li {
    list-style: none;
    padding: 10px 15px;
  }

  .rental {
    margin-top: 15px;
    background-color: #f6f6f6;
    padding: 20px 25px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
  }

  .rental:hover {
    background-color: #f3f3f3;
  }

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

  .details {
    flex-basis: 50%;
    flex-grow: 2;
    display: flex;
    height: 150px;
    margin: 20px 25px;
    justify-content: space-between;
    flex-wrap: wrap;
    align-content: space-around;
  }

  .map {
    flex-grow: 0;
    flex-basis: 150px;
    font-size: 0;
    margin: 0 25px;
  }

  h3 {
    flex-basis: 100%;
  }

  .detail {
    flex-basis: 50%;
    font-weight: 300;
    font-style: italic;
    white-space: nowrap;
  }

  img {
    max-width: 100%;
    border-radius: 5px;
  }

  span {
    font-weight: 400;
    font-style: normal;
  }

  a {
    display: inline;
    color: #016aba;
    text-decoration: none;
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

<li>
  <article class="rental">
    <button class="image " type="button">
      <img src="{rental.image}" alt="A picture of {rental.title}">
      <small>View Larger</small>
    </button>

    <div class="details">
      <h3>
        <a href="/rentals/{rental.id}" use:link>
          {rental.title}
        </a>
      </h3>
      <div class="detail owner">
        <span>Owner:</span> {rental.owner}
      </div>
      <div class="detail type">
        <span>Type:</span> {rental.category}
      </div>
      <div class="detail location">
        <span>Location:</span> {rental.city}
      </div>
      <div class="detail bedrooms">
        <span>Number of bedrooms:</span> {rental.bedrooms}
      </div>
    </div>
    <div class="map">
      <img alt="A map of Grand Old Mansion" src="https://api.mapbox.com/styles/v1/mapbox/streets-v11/static/-122.4194,37.7749,9/150x150@2x?access_token=pk.eyJ1IjoiZW1iZXJqcyIsImEiOiJjazBycmxldGwwMDVvM2VxajdkYjl1OHY0In0.YeeBOuhKFJmuL3Tt9ueMgg" width="150" height="150">
      /div>

  </article>
</li>
