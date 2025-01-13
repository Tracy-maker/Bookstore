<script>
  import "../app.css";
  import Footer from "../lib/components/Footer.svelte";
  import Header from "../lib/components/Header.svelte";
  let { children } = $props();
</script>

<div class="app">
  <Header />

  <main>
    {@render children()}
  </main>

  <Footer />
</div>

<style>
  .app {
    display: flex;
    flex-direction: column;
    height: 100vh;
  }

  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    width: 100%;
    margin: 0;
    padding: 0;
    background: #f8f9fa;
  }
</style>
