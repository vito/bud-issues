<script>
  export let posts = []
</script>

<h1>Post Index</h1>

<table border="1" cellpadding="10">
  {#if posts.length > 0}
    <thead>
      {#each Object.keys(posts[0]) as key}
        <th>{key}</th>
      {/each}
    </thead>
  {/if}
  {#each posts as post}
    <tr>
      {#each Object.keys(post) as key}
        {#if key === "id"}
          <td><a href={`/${post[key]}`}>{post[key]}</a></td>
        {:else}
          <td>{post[key]}</td>
        {/if}
      {/each}
    </tr>
  {/each}
</table>

<style>
  table {
    border-collapse: collapse;
  }
</style>
