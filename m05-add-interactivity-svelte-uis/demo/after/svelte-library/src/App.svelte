<script>
  import { Route, Router } from "svelte-routing";

  import Detail from "./detail/Detail.svelte";
  import Library from "./library/Library.svelte";

  export let url = "";
</script>

<style>
  main {
    padding: var(--spacingLarge);
  }
</style>

<Router {url}>
  <main>
    <Route path="/">
      <Library />
    </Route>
    <Route path="/books/:id" let:params>
      <Detail id={params.id} />
    </Route>
  </main>
</Router>
