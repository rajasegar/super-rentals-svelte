<script>
  import Jumbo from '../Jumbo.svelte';
  import LinkButton from '../LinkButton.svelte';
  import RentalImage from '../RentalImage.svelte';

  const path = location.path;
  const response = fetch(`/api${location.pathname}.json`)
    .then((res) => res.json())
    .then(data => data.data.attributes);
</script>

<style>
  h2 {
    font-size: 3.2em;
    margin-top: -25px;
  }

  article {
    background: 0 0;
    align-items: flex-start;
    margin-top: 15px;
    padding: 20px 25px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
</style>

{#await response}
  <h2>Loading...</h2>
{:then rental}
  <Jumbo>
    <h2>{rental.title}</h2>
    <p>
    Nice find! This looks like a nice place to stay near {rental.city}
    </p>
    <LinkButton url="/contact">Share on Twitter</LinkButton>
  </Jumbo>
  <article class="rental detailed">
    <RentalImage image={rental.image} title={rental.title}/>

    <div class="details">
      <h3>About Grand Old Mansion</h3>

      <div class="detail owner">
        <span>Owner:</span> {rental.owner}
      </div>
      <div class="detail type">
        <span>Type:</span> Standalone – { rental.category}
      </div>
      <div class="detail location">
        <span>Location:</span> {rental.city}
      </div>
      <div class="detail bedrooms">
        <span>Number of bedrooms:</span> {rental.bedrooms}
      </div>
      <div class="detail description">
        <p>{rental.description}</p>
      </div>
    </div>

    <div class="map">
      <img alt="A map of Grand Old Mansion" class="large" src="https://api.mapbox.com/styles/v1/mapbox/streets-v11/static/-122.4194,37.7749,12/894x600@2x?access_token=pk.eyJ1IjoiZW1iZXJqcyIsImEiOiJjazBycmxldGwwMDVvM2VxajdkYjl1OHY0In0.YeeBOuhKFJmuL3Tt9ueMgg" width="894" height="600">
    </div>

  </article>
{:catch error}
  <p>Error: Unable to fetch rental details</p>


{/await}
