<script>
import { writable, readable, derived, get   } from 'svelte/store';

const count = writable(2, () => {
    console.log('у нас пояявился 1-й подписчик');
    return () => console.log('у нас подписчиков не осталось(STOP)');
});

// count.subscribe(value => {
// console.log(value);
// }); // выведет '0'

//count.set(3); // выведет '1'
//count.update(n => n + 2); // выведет '2'

const unsubscribe = count.subscribe(value => {
    console.log(value);
});
unsubscribe();

const time = readable(new Date(), set => {
    const interval = setInterval(() => {
        set(new Date());
    }, 1000);

    return () => clearInterval(interval);
});
let t1 = time.subscribe(value => {
    console.log(value);
});

t1();

//const doubled = derived(count, $a => $a * 2);
const delayed = derived(count, ($a, set) => {
    setTimeout(() => set($a), 1000);
}, 'секундочку...');

const value = get(delayed);

</script>