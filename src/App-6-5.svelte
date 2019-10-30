<script>
     import Product from "./Product-6-5.svelte";

</script>
<h1>App-6-5</h1>
<Product on:click="{()=>alert('Clicked!')}"
        productTitle="A Book" />