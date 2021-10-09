<script context="module">
  export const prerender = true;
</script>

<script>
  const website = "e-commerce";
  // import Counter from "$lib/Counter.svelte";

  // import Card from "$lib/contents/Card.svelte";
  import ConditionnalList from "$lib/contents/ConditionnalList.svelte";
  import { products } from "$lib/data/products";
  let label = "";
  let isSelected = false;
  let selectedItems = [];

  function foundItems() {
    isSelected = true;
    return (selectedItems = products.filter((card) => card.label === label));
  }
  function resetItems() {
    label = "";
    isSelected = false;
    selectedItems = [];
    return label, isSelected, selectedItems;
    // selectedItems = [...products];
  }
  $: console.log(selectedItems);
</script>

<svelte:head>
  <title>{website}</title>
</svelte:head>

<section>
  <h1>
    {website}
  </h1>
  <h2>produits</h2>

  <div class="cards-group">
    {#if !isSelected}
      <ConditionnalList cards={products} />
    {:else}
      <ConditionnalList cards={selectedItems} />
    {/if}
    <!-- <div class="card" />
    <div class="card" />
    <div class="card" /> -->
  </div>
  <!-- <p>c'est <strong>mes</strong> produits, na!</p> -->
  <h2>Rechercher un produit</h2>
  <form>
    <label for="label">nom du produit </label>
    <input
      on:change={() => foundItems()}
      id="label"
      name="label"
      bind:value={label}
      list="hint"
    />
    <datalist id="hint">
      {#each products as product}
        <option value={product.label} />
      {/each}
    </datalist>
  </form>
  <button on:change={resetItems()}>reinitialiser</button>
</section>

<style>
  section {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    flex: 1;
  }

  h1 {
    width: 100%;
  }

  .cards-group {
    display: grid;
    /* max-width: 100%; */
    grid-gap: 1em;
    text-align: center;
    /* grid-auto-rows: column; */
    /* grid-template-columns: repeat(auto-fill, 212px); */
  }

  /* .welcome {
    position: relative;
    width: 100%;
    height: 0;
    padding: 0 0 calc(100% * 495 / 2048) 0;
  } */

  /* .welcome img {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    display: block;
  } */
  /* section {
    margin-bottom: 3em;
  } */
  @media screen and (min-width: 480px) {
    .cards-group {
      grid-template-columns: repeat(2, 1fr);
    }
  }
  @media screen and (min-width: 770px) {
    .cards-group {
      grid-template-columns: repeat(3, 1fr);
    }
  }
  @media screen and (min-width: 1024px) {
    .cards-group {
      grid-template-columns: repeat(4, 1fr);
    }
  }
</style>
