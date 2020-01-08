<script>
import ClipboardButton from './ClipboardButton.svelte'

export let defaultLength = 10;

function generate(length) {
  const OK_BOOMER = 'ok boomer'
  let result = ''
  for (let index = 0; index < length; index++) {
    result += `${OK_BOOMER} `
  }
  return result
}


let amount = defaultLength;
$: uppercase = false;
$: OKBOOMER = uppercase ? generate(amount).toUpperCase() : generate(amount)

</script>

<div class="settings">
  <div class="settings__options">
    <label>
      <span>amount</span>
      <input type="number" class="settings__amount" bind:value={amount}>
    </label>
    <label class="settings__char">
      <span>uppercase?</span>
      <input type="checkbox" bind:checked={uppercase}>
    </label>
  </div>
  <ClipboardButton clipboardData={OKBOOMER} />
</div>


<p class="output">
  {OKBOOMER}
</p>

<style>
.settings {
  padding: 2.5em 1em;
  max-width: 300px;
  width: 100%;
  margin: 0 auto;
  text-align: center;
}

.settings__options {
  display: flex;
  justify-content: space-between;
}

.settings__amount {
  background: #1a1538;
  border: none;
  color: #ddd9e1;
}

.settings__char {
  margin-left: 1em;
}

.output {
  max-width: 90vw;
  margin: 0 auto;
  padding: 0 1em 2.5em;
  width: 100%;
  text-align: center;
}

label {
  display: inline-block;
  text-align: left;
}
span {
  color: #ec5576;
  text-transform: uppercase;
  display: block;
  font-size: 0.8rem;
}
</style>