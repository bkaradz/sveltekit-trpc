<script lang="ts">
  import { trpc } from "$lib/trpc/client";

  let test: string;

  const getHello = async () => {
    test = await trpc.hello.query("World from trpc");
  };
  getHello();
</script>

<h1>Welcome to SvelteKit</h1>

<p>Visit these sites to read the documentation</p>
<ul>
  <li><a href="https://trpc.io">trpc.io</a></li>
  <li><a href="https://kit.svelte.dev">kit.svelte.dev</a></li>
</ul>
{#await getHello() then test2}
  <p>{test2}</p>
{/await}

<style lang="postcss">
  /* your styles go here */
</style>
