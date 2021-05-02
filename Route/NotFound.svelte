<script>
  import { activeRoute } from "./Router";
</script>

{#if activeRoute.path === '*'}
  <slot />
{/if}