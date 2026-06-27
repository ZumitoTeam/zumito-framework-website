<script>
  import { afterNavigate } from '$app/navigation';
  import "../app.postcss";

  afterNavigate(() => {
    if (window.__cursor) {
      window.__cursor.update();
    }
  });
</script>

<svelte:head>
  <title>Zumito Framework</title>
</svelte:head>

<slot />
