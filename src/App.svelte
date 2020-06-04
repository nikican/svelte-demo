<script>
  import Face from "./Face.svelte";
  import Container from "./Container.svelte";
  import Header from "./Header.svelte";
  import Buttons from "./Buttons.svelte";

  let showHeader = false;
  let score = 0;
  $: smileySays = "Hi there, you score is: " + score;
  $: if (score < -4) smileySays = "Wow your score is low!";
  const buttons = [
    { value: 0, text: "ummmmmm......" },
    { value: 1, text: "I sure do!" },
    { value: -2, text: "gross!" }
  ];
</script>

<style>
  div {
    color: red;
  }
  :global(*) {
    box-sizing: border-box;
  }
  :global(body, html) {
    margin: 0;
    height: 100vh;
    overflow: hidden;
  }
</style>

{#if showHeader}
  <Header />
{/if}
<Container>
  <h1>{smileySays}</h1>
  <Face index={2} />
  <Buttons
    {buttons}
    on:click={({ detail }) => {
      score += detail.value;
    }} />
</Container>
