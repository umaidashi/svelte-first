<script>
  import Todo from "./Todo.svelte";

  function handleChecked(event) {
    if (event.detail.checked) {
      alert("Good job!");
    }
  }
</script>

<Todo task="Mow lawn" on:checked={handleChecked} />
