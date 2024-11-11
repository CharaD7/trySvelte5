<script lang="ts">
  const colors = ['red', 'blue', 'green', 'yellow', 'purple', 'orange', 'pink', 'brown', 'black', 'white'];
  let selected = $state(colors[0]);
</script>

<h1 style="color: {selected}">Pick a colour</h1>

<div>
  {#each colors as color}
    <button
      style="background: {color}"
      aria-label={color}
      aria-current={selected === color}
      onclick={() => selected = color}
    ></button>
  {/each}
</div>

<style>
  h1 {
    transition: color 0.2s;
  }

  div {
    display: grid;
    grid-template-columns: repeat(7, 1fr);
    gap: 5px;
    max-width: 400px;
  }

  button {
    aspect-ratio: 1;
    border-radius: 50%;
    background: var(--color, #fff);
    transform: translate(-2px, -2px);
    transition: all 0.1s;
  }

  button[aria-current="true"] {
    transform: none;
    filter: none;
    box-shadow: inset 3px 3px 4px rgba(0, 0, 0, 0.2);
  }
</style>
