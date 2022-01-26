<script>
    export let object;
</script>

<li class="typeahead-objects" on:mousedown>{object} </li>

<style>
    li.typeahead-objects {
    list-style: none;
    border: 1px solid #d4d4d4;
    margin: 0;
    padding: 10px;
    cursor: pointer;
    background-color: #fff;
    display: block;
    }
    li.typeahead-objects:hover {
    background-color: lightgray;
    }
</style>