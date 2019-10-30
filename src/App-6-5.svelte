<script>
     import Product from "./Product-6-5.svelte";
     function addToCart(event) {
         console.log(event);
     }
     function deleteProduct(event) {
         console.log(event);
     }
</script>
<h1>App-6-5</h1>
<Product
        on:add-to-cart="{addToCart}"
        on:delete="{deleteProduct}"
        productTitle="A Book" />