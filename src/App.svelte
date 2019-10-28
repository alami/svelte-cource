<script>
	let age=30;function incrementAge () { age += 1;}
	let name='Max'; function changeName () { name = 'MAXIMILIAN';}
	$: uppercaseName = name.toUpperCase();
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age+1}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<button on:click="{changeName}">Change Name</button>
