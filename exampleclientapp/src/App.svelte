<script>
  import { fade } from "svelte/transition";
  import Typeahead from "https://raw.githubusercontent.com/svelte-reusable-components/svelte-typeahead/main/Typeaheadmodule.svelte";

  let name = "Hello";
  let possibleResults = ["Result1","Result2","Result3","Result4","Result5","Result6"];
</script>

<main transition:fade>
  <Typeahead possibleResults={possibleResults} randomButton={true}/>
</main>

<style>
  main {
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
