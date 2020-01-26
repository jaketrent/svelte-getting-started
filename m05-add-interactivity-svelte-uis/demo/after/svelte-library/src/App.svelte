<script>
  import Library from "./library/Library.svelte";

  function handleBookSelect(id) {
    console.log("app handle", id);
  }
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<main>
  <Library onBookSelect={handleBookSelect} />
</main>
