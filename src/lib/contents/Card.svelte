<script>
  import thousands from "thousands";
  export let card = {};
  let { description, text, price, label, quantity, img } = card;
</script>

<div class="card">
  <figure>
    <img src={img} alt={label} width="196" height="196" />
  </figure>
  <p>{label}</p>
  <p>{thousands(parseFloat(price).toFixed(2), " ")} €</p>
  <!-- <p>{description}</p>
  <p>{quantity} restant{quantity > 1 ? "s" : ""}</p> -->
</div>

<style>
  .card {
    display: grid;
    padding: 1em;
  }
  .card:hover {
    background-color: gray;
  }
  @media screen and (min-width: 480px) {
    .card {
      max-width: 200px;
      min-height: 200px;
      border: 2px solid silver;
      border-radius: 8px;
      padding: 0;
      transition: border 250ms linear;
    }
    .card:hover {
      border-color: purple;
    }
    figure {
      background: light-gray;
      /* border-radius: 12px; */
      width: 196px;
      min-height: 196px;
      /* border: 1px solid aquamarine; */
      padding: 2px;
      margin: 0;
    }
    img[alt] {
      align-self: center;
      display: grid;
      align-items: center;
    }
  }
</style>
