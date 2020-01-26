<script>
  import Detail from "./detail/Detail.svelte";
  import Library from "./library/Library.svelte";

  let page = "library";
  let pageArgs = {};

  function handleBookSelect(event) {
    console.log("app handle", event.detail.id);

    page = "detail";
    pageArgs = event.detail;
  }
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<main>
  {#if page === 'library'}
    <Library on:book-select={handleBookSelect} />
  {:else if page === 'detail'}
    <Detail {...pageArgs} />
  {/if}
</main>
