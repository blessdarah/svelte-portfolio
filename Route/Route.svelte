<script>
  import { register, activeRoute } from "./Router";
  export let path = "*";
  export let component = null;

  // register all routes
  register({ path, component });
  console.log("component: ", component);
</script>

{#if activeRoute.path === path}
  <svelte:component this="{component}" />
  <slot />
{/if}