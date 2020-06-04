<script>
  import Face from "./Face.svelte";
  import Container from "./Container.svelte";

  let say = "hi";
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
  <div>Say: {say}</div>

  <Face index={0} />
  <Face />
  <Face index={2} />
</Container>
