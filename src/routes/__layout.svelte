<script>
  import Header from "$lib/containers/Header.svelte";
  import Footer from "$lib/containers/Footer.svelte";
  import { light } from "$lib/store/theme";
  import "../app.css";
  $light = true;
</script>

<div class="main theme-{$light ? 'light' : 'dark'}">
  <Header />

  <!-- <button
    >change theme</button
  > -->

  <main>
    <slot />
  </main>

  <Footer />

  <!-- <footer>
    <p>
      visit <a
        class="theme-{$light ? 'light' : 'dark'}"
        href="https://kit.svelte.dev">kit.svelte.dev</a
      > to learn SvelteKit
    </p>
  </footer> -->
</div>

<style>
  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    width: 100%;
    max-width: 1024px;
    margin: 0 auto;
    box-sizing: border-box;
  }
  .main {
    min-height: 100vh;
  }

  /* footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 40px;
  } */

  /* footer a {
    font-weight: bold;
  } */

  @media (min-width: 480px) {
    /* footer {
      padding: 40px 0;
    } */
  }
</style>
