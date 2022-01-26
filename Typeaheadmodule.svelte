<script>
    import Objects from "./Objects.svelte"
  
    export let possibleResults = [];
    export let randomButton = true;
    let results = [];
    let searchInput = "";
    let isFocused = false;
  
    const onFocus = () => isFocused=true;
    const onBlur = () => isFocused=false;
      
    const typeahead = () => {
        let resultsIncludes = possibleResults.filter(possibleResults => possibleResults.toLowerCase().includes(searchInput.toLowerCase()) )
        let resultsStartWith = possibleResults.filter(possibleResults => possibleResults.toLowerCase().startsWith(searchInput.toLowerCase()) )
        results = resultsStartWith.sort().concat(resultsIncludes.sort())
        results = [...new Set(results)]
    }
      
    const newSearchInput = (oneResult) => {
        searchInput = oneResult
    }
    
    const randomInput = () => {
      let randomInput = possibleResults[Math.floor(Math.random()*possibleResults.length)]
      searchInput = randomInput
    }
  
  </script>
  
  <form autocomplete="off" action="/action_page.php">
    <div class="typeahead">
      <input id="searchfield" type="text" name="searchfield" placeholder="Search" bind:value={searchInput} on:input={typeahead} on:focus={onFocus} on:blur={onBlur}> 
    </div>
    <ul class="typeahead-object-list" >
      {#if isFocused === true}
        {#if searchInput.length === 0}
          {#each possibleResults as oneResult}
            <Objects object={oneResult} on:mousedown={() => newSearchInput(oneResult)} />
          {/each}
        {:else}
          {#each results as oneResult}
            <Objects object={oneResult} on:mousedown={() => newSearchInput(oneResult)} />
          {/each}
        {/if}
      {/if}
    </ul>
  </form>
  
  {#if randomButton === true}
    <div class="randombutton">
      <button on:click={() => {randomInput(); typeahead();}}><strong>Random</strong></button>
    </div>
  {/if}

  <style>
  .typeahead {
    position: relative;
  }
  input{
    margin-top: 4em;
    margin-bottom:0;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px, rgba(0, 0, 0, 0.23) 0px 3px 6px;
  }
  input:hover{
    box-shadow: rgba(0, 0, 0, 0.16) 0px 4px 8px, rgba(0, 0, 0, 0.23) 0px 4px 8px;
  }
  input[type=text] {
    width: 60%;
    display: block;
    text-align: center;
    border: 3px solid black;
    border-radius: 0;
    margin-left: auto;
    margin-right: auto;
    transition: width 0.4s ease-in-out;
  }
  input[type=text]:focus {
      background-color: whitesmoke;
      outline: none;
      width: 65%;
    }
  ul {
    max-height: 215px;
    overflow: auto;
  }
  
  ul.typeahead-object-list {
    position: absolute;
    margin-left:17.5%;
    margin-right:17.5%;
    padding:0;
    margin-top:0;
    width:65%;
    z-index: 99;
    background-color: whitesmoke;
  }
  
  button {
    width: 20%;
    display: block;
    text-align: center;
    text-decoration: black;
    border: 3px solid black;
    border-radius: 0;
    margin-top: 1em;
    margin-left: auto;
    margin-right: auto;
    transition: width 0.4s ease-in-out;
    background: rgb(149,65,131,0.3);
    background: linear-gradient(90deg, rgba(149,65,131,0.3) 0%, rgba(191,166,227,0.3) 25%, rgba(125,185,241,0.3) 75%, rgba(68,109,137,0.3) 100%);
    box-shadow: rgba(0, 0, 0, 0.16) 0px 3px 6px, rgba(0, 0, 0, 0.23) 0px 3px 6px;
  }
  button:hover{
    box-shadow: rgba(0, 0, 0, 0.16) 0px 4px 8px, rgba(0, 0, 0, 0.23) 0px 4px 8px;
  }
  </style>