<script>
  import { light } from "$lib/store/theme";
  const year = new Date().getFullYear();
  console.log($light);
</script>

<footer class="theme-{$light ? 'light' : 'dark'}">
  fabezio - {year}
</footer>

<style>
  footer {
    position: absolute;
    bottom: 0;
    left: 0;
    display: grid;
    width: 100%;
    padding: 1em auto;
    min-height: 2em;
    text-align: center;
  }
</style>
