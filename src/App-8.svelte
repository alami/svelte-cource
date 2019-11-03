<script>
    import CustomInput from "./CustomInput.svelte"
    import Toggle from "./Toggle.svelte"
    let val='Max';
    let selectedOption =1;
    $: console.log(val);
    function setValue(event) { val = event.target.value; }
//<!-- ch-8-4-->
    let price =0;
    $: console.log(price);
    let agreed;
    $: console.log(agreed);
    let favcolor='blue';
    $: console.log(favcolor);
</script>
<!--<input type="text" value={val}   on:input={setValue}>-->
<!--<input type="text" value={val} bind:value={val}>-->
<CustomInput type="text" bind:val={val} />
<Toggle bind:chosenOption={selectedOption}/>

<hr><!-- ch-8-4-->
<input type="number"
       bind:value={price} />
<!--       on:input={event => console.log('1'+event.target.value)}>-->
<hr><!-- ch-8-5-checkboxes-and-radio-buttons -->
<label>
<input type="checkbox" bind:checked={agreed}>
Agree to term?
</label>
<h1>Fav color</h1>
<label>
    <input type="radio" name="color" value="red" bind:group={favcolor}>RED
    <input type="radio" name="color" value="green" bind:group={favcolor}>GREEN
    <input type="radio" name="color" value="blue" bind:group={favcolor}>Blu
</label>