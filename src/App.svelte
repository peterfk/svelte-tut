<script>

	import Nested from './components/Nested.svelte';

	let name = 'Svelte';
  let src = './assets/svelte.svg';
  let name2 = 'Rick Ashley';

  let count = 0;
  $: doubled = count * 2;

	function increment() {
		count += 1;
	}

</script>

<h1>Hello {name.toUpperCase()}!</h1>
<img {src} alt="{name2} dances."/>
<p>This is a paragraph.</p>
<Nested/>
<button on:click={increment}>
	Clicked {count}
	{count === 1 ? 'time' : 'times'}
</button>
<p>{count} doubled is {doubled}</p>


<style>
	p {
		color: goldenrod;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>