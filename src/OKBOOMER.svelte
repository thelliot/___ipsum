<script>
import clipboard from 'clipboard'

new clipboard('#copy')

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

<input type="number" bind:value={amount}>
<button id="copy" data-clipboard-text={OKBOOMER}>copy</button>
<label>
  uppercase?
  <input type="checkbox" bind:checked={uppercase}>
</label>
<br>
<p>
  {OKBOOMER}
</p>
