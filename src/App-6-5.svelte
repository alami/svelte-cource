<script>
     import Modal from "./Modal.svelte";
     import Product from "./Product-6-5.svelte";
     let showModal = false;
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

<button on:click = "{()=>showModal=true}">Show Modal</button>

{#if showModal}
<Modal on:cancel="{()=>showModal=false}" on:close="{()=>showModal=false}" >
    <h1 slot="header">head</h1>
    <h1>WWW</h1>
    <button slot="footer" on:click = "{()=>showModal=false}">Confirm</button>
</Modal>
{/if}