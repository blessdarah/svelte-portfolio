<script context="module">
  import { writable } from "svelte/store";

  export const activeRoute = writable({});

  export const routes = {};
  export function register(route) {
    routes[route.path] = route;
  }
</script>

<script>
  import {onMount, onDestroy} from "svelte";
  import page from "page";

  function configureRoutes(){
    for(let [path, route] of Object.entries(routes)){
      page(path, () => ($activeRoute = route));
    }
    page.start();
  }

  onMount(configureRoutes);

  onDestroy(page.stop);
  
</script>

<slot />