<script>
  import Face from "./Face.svelte";
  import Container from "./Container.svelte";

  let say = false;
  setTimeout(() => {
    say = "bye";
  }, 1000);
</script>

<style>
  div {
    color: red;
  }
</style>

<Container>
  {#if say}
    <div>Hi!</div>
  {:else if !say}not saying anything..{/if}
  {#each [2, 1, 0] as index}
    <Face {index} />
  {/each}
</Container>
