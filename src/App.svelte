<script>
  import Nested from "./components/Nested.svelte";
  import ColoredButtons from "./components/ColoredButtons.svelte";
  import Inner from "./components/Inner.svelte";

  let name = "Svelte";
  let src = "./assets/svelte.svg";
  let name2 = "Rick Ashley";

  let count = 0;
  $: doubled = count * 2;

  function increment() {
    count += 1;
  }

  let m = { x: 0, y: 0 };

  function handleMessage(event) {
		alert(event.detail.text);
	}

  let name3 = 'world';
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
{:else if count < 5}
  <p>{count} is less than 5</p>
{:else}
  <p>{count} is between 0 and 10</p>
{/if}

<ColoredButtons />

<button on:click|once={() => alert("clicked")}> Click me </button>

<div
  on:pointermove={(e) => {
    m = { x: e.clientX, y: e.clientY };
  }}
>
  The pointer is at {m.x} x {m.y}
</div>

<Inner on:message={handleMessage} />
<p></p>
<input bind:value={name3} />

<h1>Hello {name3}!</h1>

<style>
  p {
    color: goldenrod;
    font-family: "Comic Sans MS", cursive;
    font-size: 2em;
  }
</style>
