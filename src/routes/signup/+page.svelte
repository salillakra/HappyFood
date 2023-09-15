<script>
  // Define multiple reactive variables to store states
  let count = 0;
  let text = "";
  let isOpen = false;

  // Function to update the states
  function increment() {
    count += 1;
  }

  function updateText(event) {
    text = event.target.value;
  }

  function toggleOpen() {
    isOpen = !isOpen;
  }
</script>

<!-- Use the states in your template -->
<div>
  <p>Count: {count}</p>
  <button on:click={increment}>Increment</button>
</div>

<div>
  <input type="text" value={text} on:input={updateText} />
  <p>Text: {text}</p>
</div>

<div>
  <p>Is Open: {isOpen ? "Yes" : "No"}</p>
  <button on:click={toggleOpen}>Toggle Open</button>
</div>
