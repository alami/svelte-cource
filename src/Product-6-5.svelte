<script>
    export let title;
    export let price;
    import {createEventDispatcher} from "svelte";
    const dispatch = createEventDispatcher ();
    function addToCart() {
        dispatch('add-to-cart', {id:'p1'});
    }
</script>
<h2>Product-6-5</h2>
<article>
    <h1>{title}</h1>
    <h1>${price}</h1>
    <button on:click="{addToCart}">Add to Cart</button>
    <button on:click="{()=>{dispatch('delete', 'p1')}}">Delete</button>
</article>