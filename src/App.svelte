<script>
  import Component from "./Component.svelte";
  import { QueryClient, QueryClientProvider } from '@sveltestack/svelte-query'
  
  const queryClient = new QueryClient();
</script>

<QueryClientProvider client={queryClient}>
  <Component />
</QueryClientProvider>