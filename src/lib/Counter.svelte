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

<style>
  button {
    background: #f00;
    color: #fff;
    padding: 0.5em;
    border: none;
    border-radius: 0.25em;
    cursor: pointer;
  }
</style>
