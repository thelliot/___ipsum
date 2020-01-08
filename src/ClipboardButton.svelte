<script>
import { fly, fade } from 'svelte/transition';
import Clipboard from 'clipboard'

export let buttonText = 'copy text'
export let clipboardData = ''

const button = new Clipboard('#copy')

let show = false

button.on('success', (e) => {
  show = true
  setTimeout(() => {
    show = false
  }, 2250);
})

$: showMessage = show

</script>

{#if showMessage}
  <div role="alert" class="alert" in:fly="{{ y: -500, duration: 600 }}" out:fade>
    🎉 successfully copied! 🎉
  </div>
{/if}


<button id="copy" data-clipboard-text={clipboardData}>
  {buttonText}
</button>

<style>
.alert {
  position: absolute;
  top: 5vh;
  background: #66d88f;
  max-width: 300px;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 5px;
  padding: 15px;
  text-align: center;
  width: 100%;
  color: #1a1538;
  font-weight: bold;
  line-height: 1;
}

button {
  width: 100%;
  margin: 15px 0 0;
  cursor: pointer;
  border: none;
  background: #0d0921;
  border-radius: 5px;
  color: #908bc7;
}

button:active, button:focus {
  background-color: #0d09215b;
}

</style>