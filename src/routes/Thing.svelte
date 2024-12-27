<script>
  const emojis = {
    apple: '🍎',
    banana: '🍌',
    carrot: '🥕',
    doughnut: '🍩',
    eggplant: '🍆',
  };

  // name is updated whenever the prop value changes
  let { name } = $props();

  // ...but `emoji` is fixed upon initialisation
  const emoji = emojis[name];
</script>

<p>{emoji} = {name}</p>
