<script>
  export let happyScore = 1;
  export let size = 1;

  const faces = [
    "🤬",
    "😡",
    "😭",
    "🙁",
    "😕",
    "😐",
    "🙂",
    "😀",
    "😄",
    "😊",
    "😘"
  ];
  $: index = happyScore + 5;
</script>

<div style="font-size: {size}em">{faces[index]}</div>
