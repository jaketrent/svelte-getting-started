<script>
  import { onMount } from "svelte";

  import { httpGet } from "../common/api.js";

  export let id;

  let book = {};
  onMount(async () => {
    const { data } = await httpGet("/" + id);
    book = data;
  });
</script>

<div>Detail page - {id}/{book.title}</div>
