# svelte-typeahead
The typeahead component implements a search box with typeahead (and an optional random button) for snel projects. (Snel is a cybernetical compiler for svelte applications in deno)

A visual example is given in the svelte REPL: https://svelte.dev/repl/6f381dc0e66242288a1ba69d059d105b?version=3.46.2

Incase you have not created a snel project before, head to https://deno.land/x/snel@v0.6.0 and follow the steps to create one.

To then use it, import the raw Typeaheadsmodule.svelte file as shown in the usage example.

After you initiated a snel project and added the code shown below, you are able to see in when running the project with "trex run start".

## Usage

Import the component and set list of possible Results.

```javascript
 import Typeahead from "https://raw.githubusercontent.com/svelte-reusable-components/svelte-typeahead/main/Typeaheadmodule.svelte"
 
 let possibleResults = ["Result1","Result2","Result3"];
```

Use the component in your code. Set randomButton equal to {true} or {false} depending on whether the Button should appear.

```html
<Typeahead possibleResults={possibleResults} randomButton={true} />
```
## CSS
- `randombutton` class of the Button
- `searchfield` id of the input field
- `typeahead-object-list` class of the entire typeahead list
- `typeahead-objects` class of the listitems
