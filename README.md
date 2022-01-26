# svelte-typeahead
A svelte component to implement a search box with typeahead (and an optional random button)

## Usage

Import the component and set list of possible Results.

```javascript
 import Typeahead from 'svelte-typeahead'
 
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
