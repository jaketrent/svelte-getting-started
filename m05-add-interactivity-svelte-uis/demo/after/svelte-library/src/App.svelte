<script>
  import Library from "./library/Library.svelte";

  function handleBookSelect(event) {
    console.log("app handle", event.detail.id);
  }
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<main>
  <Library on:book-select={handleBookSelect} />
</main>
