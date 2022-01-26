# svelte-typeahead
The typeahead component implements a search box with typeahead (and an optional random button) for snel projects. (Snel is a cybernetical compiler for svelte applications in deno)

![image](https://user-images.githubusercontent.com/79450010/151197042-e21d0882-91e2-4365-9f8c-f78c4b74d9fe.png)

![image](https://user-images.githubusercontent.com/79450010/151198797-3d1a0327-b152-430b-aba1-e6f85a65dec0.png)


A visual example to play around with is also given in the svelte REPL: https://svelte.dev/repl/6f381dc0e66242288a1ba69d059d105b?version=3.46.2

In case you have not created a snel project before, head to https://deno.land/x/snel@v0.6.0 and follow the steps to create one.

To then use it, import the link "https://deno.land/x/svelte_typeahead/Typeaheadmodule.svelte" as shown in the usage example.

After you initiated a snel project and added the code shown below, you are able to see in when running the project with "trex run start".

An example of the usage is shown in the exampleclientapp, which is a snel project intended to show the functionality of the component.

## Usage Example

Import the component and set list of possible Results.

```javascript
 import Typeahead from "https://deno.land/x/svelte_typeahead/Typeaheadmodule.svelte"
 
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
