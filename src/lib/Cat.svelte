<script>
  import { onMount } from "svelte";
  let catTags = [];
  let markup = "<h1>YOLO 🐈</h1>";

  // https://cataas.com/cat
  onMount(async () => {
    const response = await fetch("https://cataas.com/api/tags");
    catTags = await response.json();
    // console.log(json);
  });
</script>

{@html markup}
<ul>
  {#each catTags as tag}
    {#if tag !== ""}
      <li>
        <img
          src={`https://cataas.com/cat/${encodeURIComponent(tag)}`}
          loading="lazy"
          alt={`Random cat image for the tag ${tag}`}
          height="200px"
        />
      </li>
    {/if}
  {/each}
</ul>

<style>
  ul {
    display: grid;
    gap: 1rem;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    list-style: none;
  }

  img {
    aspect-ratio: 1/1;
    margin: 1rem;
  }
</style>
