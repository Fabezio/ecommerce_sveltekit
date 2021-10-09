<script>
  import Card from "$lib/contents/Card.svelte";
  export let cards = [];
</script>

{#each cards as card}
  {#if card.quantity > 0}
    <a href="products/{card.id}">
      <Card {card} />
    </a>
  {/if}
{/each}

<style>
  /* a {
    display: block;
  }
  a:hover {
    background: gray;
  } */
</style>
