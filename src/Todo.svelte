<script>
  // export let caption
  let isDone = false
  // function check() {
  //   isDone = !isDone
  // }

  
</script>


<button on:click={() => isDone = !isDone} class={isDone ? 'done' : 'todo'} ><slot />
</button>

<!-- <button >
</button> -->

<style>
  button {
    display: block;
    margin: auto;
    text-align: center;
    background: white;
    border: none;
    padding: 0.25rem 1rem;
    font-weight: 400;
  }
  .done {
    color: green;
    filter: opacity(0.5);
    text-decoration: line-through;
    font-weight: 200;
    transition: all 300ms ease-in-out;
  }
  .todo {
    transition: all 300ms ease-in-out;
    color: navy;

  }
</style>