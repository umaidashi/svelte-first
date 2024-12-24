<script>
  export let task;

  export let completed = false;

  function handleInput(event) {
    if (event.target.checked) {
      alert("Good job!");
    }
  }
</script>

<p>
  <input type="checkbox" checked={completed} on:input={handleInput} />
  {task}
</p>
