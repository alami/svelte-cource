<script>
    import CustomInput from "./CustomInput.svelte"
    import Toggle from "./Toggle.svelte"
    let val='Max';
    let selectedOption =1;
    $: console.log(val);
    function setValue(event) { val = event.target.value; }
</script>
<!--<input type="text" value={val}   on:input={setValue}>-->
<!--<input type="text" value={val} bind:value={val}>-->
<CustomInput type="text" bind:val={val} />
<Toggle bind:chosenOption={selectedOption}/>