<script>
  let inputArray = "";
  let trimmedInput = "";
  let arrayOfObjects = [
    {color: "red"},
    {color: "green"},
    {color: "blue"},
  ];
function addObject() {
    trimmedInput = inputArray.trim();
}
function handleInput(event) {
   inputArray = event.target.value;
}
    // Check if the input value is not empty before adding to the array
    if (trimmedInput !== "") {
      const newObject = { color: arrayOfObjects.length + 1};
      // Use push method to add the new object to the array
      arrayOfObjects.push(newObject);
      // Clear the input after adding to the array
      inputArray = "";
    }
  </script>

<div>
  <h1>Array of Objects</h1>
  <ul>
    {#each arrayOfObjects as obj (obj.color)}
      <li>{obj.color}</li>
    {/each}
  </ul>

  <label for="text-input">Text input</label>: 
  <input type="text" id="text-input" bind:value={inputArray}>

  <button on:click={addObject}>Add Object</button>
</div>