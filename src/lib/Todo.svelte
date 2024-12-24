<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  export let task;
  export let completed = false;

  function handleInput(event) {
    dispatch("checked", {
      checked: event.target.checked,
    });
  }
</script>

<p>
  <input type="checkbox" checked={completed} on:input={handleInput} />
  {task}
</p>
