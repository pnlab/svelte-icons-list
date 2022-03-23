<script>
  import VirtualList from '@sveltejs/svelte-virtual-list';
  let emojis = []
  for (let i=128100;i<128293;i++){
    emojis.push(String.fromCodePoint(`${i}`.toString(16)))  
   
  }
  // console.log(emojis)
  let start;
	let end;
</script>

<div class="container">
<!--   {#each emojis as emoji}
  <p class="text">{emoji}</p>
{/each} -->

  <VirtualList {emojis} bind:start bind:end let:item>
		<p class="text">{item}</p>
	</VirtualList>
</div>

<style>
  .text {
    font-size: 25px;
  }
  .container {
    display: grid;
    grid-template-columns: repeat(10, 1fr);
  }
</style>
