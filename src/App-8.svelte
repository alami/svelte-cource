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

</script>
<!--<input type="text" value={val}   on:input={setValue}>-->
<!--<input type="text" value={val} bind:value={val}>-->
<CustomInput type="text" bind:val={val} />
<Toggle bind:chosenOption={selectedOption}/>

<hr><!-- ch-8-4-->
<input type="number"
       bind:value={price} />
<!--       on:input={event => console.log('1'+event.target.value)}>-->