<script>
  import Nested from "./components/Nested.svelte";

  let name = "Svelte";
  let src = "./assets/svelte.svg";
  let name2 = "Rick Ashley";

  let count = 0;
  $: doubled = count * 2;

  function increment() {
    count += 1;
  }
</script>

<h1>Hello {name.toUpperCase()}!</h1>
<img {src} alt="{name2} dances." />
<p>This is a paragraph.</p>
<Nested answer={42} />
<button on:click={increment}>
  Clicked {count}
  {count === 1 ? "time" : "times"}
</button>
<p>{count} doubled is {doubled}</p>

{#if count > 10}
  <p>{count} is greater than 10</p>
{:else}
  <p>{count} is between 0 and 10</p>
{/if}

<style>
  p {
    color: goldenrod;
    font-family: "Comic Sans MS", cursive;
    font-size: 2em;
  }
</style>
