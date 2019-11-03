<script>
    let val='Max';
    $: console.log(val);
    function setValue(event) { val = event.target.value; }
</script>
<!--<input type="text" value={val}   on:input={setValue}>-->
    <input type="text" value={val} bind:value={val}>