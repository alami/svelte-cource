<script>
    import {tick, afterUpdate} from 'svelte';
     import Modal from "./Modal.svelte";
     import Product from "./Product-6-5.svelte";
let text = 'This some dummy text!';
     let showModal = false;
     let closeable = false;
     let products = [
         {
//             id: "p1",
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
     function transform(event) {
         if (event.which !== 9) { return; }
         event.preventDefault();
         const selectionStart = event.target.selectionStart;
         const selectionEnd = event.target.selectionEnd;
         const value = event.target.value;
         text = value.slice(0, selectionStart)+
                 value.slice(selectionStart, selectionEnd).toUpperCase()+
                 value.slice(selectionEnd);
      tick().then (()=> {
          event.target.selectionStart = selectionStart;
          event.target.selectionEnd = selectionEnd;
      });
     }
    afterUpdate(() => {

    })
</script>

<h1>App-6-5</h1>
{#each products as product}
<Product
        on:add-to-cart="{addToCart}"
        on:delete="{deleteProduct}"
        {...product}
/>
{/each}

<button on:click = "{()=>(showModal=true)}">Show Modal</button>

{#if showModal}
<Modal on:cancel="{()=>(showModal=false)}" on:close="{()=>(showModal=false)}"
    let: didAgreed={closeable}>
    <h1 slot="header">head</h1>
    <h1>WWW</h1>
    <button slot="footer" on:click = "{()=>(showModal=false)}" disabled={closeable}>Confirm</button>
</Modal>
{/if}

<textarea rows="5" value={text} on:keydown={transform} ></textarea>