<script lang="ts">
  // export let name;
  let firstName = "Ridwan";
  let lastName = "Rais";
  let beltColor = "black";

  const handleClick = () => {
    beltColor = "orange";
  };

  const handleInput = (e) => {
    beltColor = e.target.value;
  };

  $: fullName = firstName + " " + lastName;
  $: {
    console.log(beltColor);
    console.log(fullName);
  }
</script>

<main>
  <p>{fullName} - {beltColor} belt</p>
  <input type="text" bind:value={firstName} />
  <input type="text" bind:value={lastName} />
  <!-- <input type="text" on:input={handleInput} value={beltColor} /> -->
  <input type="text" bind:value={beltColor} />
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 4em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
