<script>
  import Face from "./Face.svelte";
  import Container from "./Container.svelte";
  import Header from "./Header.svelte";
  import Buttons from "./Buttons.svelte";
  import story from "./story";

  let showHeader = false;
  let happyScore = 0;
  let storyIndex = 0;
  $: smileySays = story[storyIndex].smileySays;
  $: buttons = story[storyIndex].buttons;

  const clickHanlder = ({ detail }) => {
    storyIndex += 1;
    happyScore += detail.value;
  };
</script>

<style>
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
  <Buttons {buttons} on:click={clickHanlder} />
</Container>
