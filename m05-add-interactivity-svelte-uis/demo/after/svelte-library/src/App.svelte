<script>
  import Library from "./library/Library.svelte";

  function handleClick(id) {
    console.log("app handle", id);
  }
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<main>
  <Library onClick={handleClick} />
</main>
