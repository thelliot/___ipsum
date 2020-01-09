<script>
import { word } from './store.js';
import { onMount } from 'svelte';

let inputEl

onMount(() => {
  inputEl.focus()
})

</script>

<header>
  <input bind:value={$word} bind:this={inputEl} placeholder="type your word" />
  <span>(ipsum)</span>
</header>

<style>
header {
  color: #ec5576;
  background: #1a1538;
  text-align: center;
  padding: 3rem 0;
  font-size: calc(1em + 10vw);
}

span {
  display: block;
  font-size: 1rem;
}
input {
  text-align: center;
  width: 100%;
  padding: 0;
  margin: 0;
  border: none;
  color: #ec5576;
  background: #1a1538;
}

input::placeholder {
  color: #ec557683;
}
</style>