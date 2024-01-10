<script lang="ts">
    import { each } from "svelte/internal";
  
    let people = [
      { name: "yoshi", beltColour: "black", age: 25, id: 1 },
      { name: "mario", beltColour: "orange", age: 45, id: 2 },
      { name: "luigi", beltColour: "brown", age: 35, id: 3 },
    ];
  
    const handleClick = (id, e) => {
      people = people.filter((person) => person.id != id);
  
      console.log(e);
    };
  
    let num = 20;
  </script>
  
  {#if num > 20}
    <p>Greater than 20</p>
  {:else if num < 20}
    <p>Less than 20</p>
  {:else}
    <p>Hi 20</p>
  {/if}
  
  <main>
    {#each people as person (person.id)}
      <div>
        <h4>{person.name}</h4>
        {#if person.beltColour === "black"}
          <p><strong>MASTER</strong></p>
        {/if}
        <p>{person.age} years old, {person.beltColour} belt.</p>
        <button on:click={(e) => handleClick(person.id, e)}>delete</button>
      </div>
    {:else}
      <p>There are no people to show...</p>
    {/each}
  </main>
  
  <style>
    main {
      text-align: center;
      padding: 1em;
      max-width: 240px;
      margin: 0 auto;
    }
  
    @media (min-width: 640px) {
      main {
        max-width: none;
      }
    }
  </style>
  