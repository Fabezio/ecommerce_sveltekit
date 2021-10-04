<script context="module">
  export const prerender = true;
  const website = "e-commerce";
</script>

<script>
  import Counter from "$lib/Counter.svelte";
</script>

<svelte:head>
  <title>{website}</title>
</svelte:head>

<section>
  <h1>
    {website}
    <!-- <div class="welcome">
			<picture>
				<source srcset="svelte-welcome.webp" type="image/webp" />
				<img src="svelte-welcome.png" alt="Welcome" />
			</picture>
		</div>

		to your new<br />SvelteKit app -->
    <!-- </h1>

  <h2>
    try editing <strong>src/routes/index.svelte</strong>
  </h2>

  <Counter /> -->
  </h1>
  <h2>products</h2>
  <div class="cards-group">
    <div class="card" />
    <div class="card" />
    <div class="card" />
    <div class="card" />
  </div>
  <p>c'est <strong>mes</strong> produits, na!</p>
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
  .card {
    min-width: 20em;
    min-height: 20em;
    border: 2px solid darkgray;
    border-radius: 8px;
  }
  .cards-group {
    text-align: center;
  }

  .welcome {
    position: relative;
    width: 100%;
    height: 0;
    padding: 0 0 calc(100% * 495 / 2048) 0;
  }

  .welcome img {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    display: block;
  }
  @media screen and (min-width: 480px) {
    .cards-group {
      display: grid;
      grid-gap: 1em;
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
