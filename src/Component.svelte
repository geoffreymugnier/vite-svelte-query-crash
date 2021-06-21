<script>
  import { useQuery } from '@sveltestack/svelte-query'
import App from './App.svelte';

  const result = useQuery("key", async () => {
    const { ok, json } = await fetch('https://jsonplaceholder.typicode.com/todos/');
    if (!ok) {
      throw new Error('Network response was not ok')
    }
    return json()
  });
</script>

{#await result}
    <p>load...</p>
{:then}
    <p>{$result.data}</p>
{:catch}
    <p>An error has occured.</p>
{/await}