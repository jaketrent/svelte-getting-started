<script>
  import { links } from "svelte-routing";

  export let to;
</script>

<style>
  .button {
    background: var(--colorCta);
    border: none;
    border-radius: calc(
      (2 * (var(--spacingSmall) * 1.5) + var(--typeLineHeightTight)) / 2
    );
    color: var(--colorFgInverse);
    cursor: pointer;
    display: inline-block;
    font-size: var(--typeSizeSmall);
    font-weight: var(--typeWeightBold);
    line-height: var(--typeLineHeightTight);
    margin: 0;
    padding: calc(var(--spacingSmall) * 1.5) var(--spacingLarge);
    text-overflow: ellipsis;
    text-transform: uppercase;
    transition: filter 150ms;
    white-space: nowrap;
  }
  .button:hover,
  .button:focus {
    filter: brightness(115%);
    outline: none;
    text-decoration: none;
  }
</style>

{#if to}
  <a href={to} on:click use:links class="button">
    <slot />
  </a>
{:else}
  <button on:click class="button">
    <slot />
  </button>
{/if}
