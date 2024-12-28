<script lang="ts">
  import { roll } from './util.js';

  let promise = $state(roll());
</script>

<button onclick={() => promise = roll()}>
  Roll the dice
</button>

{#await promise}
  <p>...rolling</p>
{:then number}
  <p>You rolled a { number }!</p>
{:catch error}
  <p style="color: red">{error.message}</p>
{/await}
