<script>
     import Product from "./Product-6-5.svelte";

</script>
<h1>App-6-5</h1>
<Product
        on:add-to-cart="{()=>alert('Add to cart!')}"
        on:delete="{()=>alert('Delete!')}"
        productTitle="A Book" />