<script>
  // Need to initialize vars for svelte to work
  let count = 0;
  const increment = () => {
    count += 1;
  };
</script>

<button on:click={increment}>
  count is {count}
</button>
