<script>
    import Model from "./Modal.svelte";
     import Product from "./Product-6-5.svelte";
     let products = [
         {
             id: "p1",
             title:"A Book",
             price:9.99
         }
     ];
     function addToCart(event) {
         console.log(event);
     }
     function deleteProduct(event) {
         console.log(event.detail);
     }
</script>


<h1>App-6-5</h1>
{#each products as product}
<Product
        on:add-to-cart="{addToCart}"
        on:delete="{deleteProduct}"
        {...product}
/>
{/each}

<Model>
    <h1>WWW</h1>
</Model>
