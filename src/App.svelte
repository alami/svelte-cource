<script>
	let age=30;
	let name='Max';
	$: uppercaseName = name.toUpperCase();
	//$: console.log(name);
	$: if (name === 'Maximilian' ) {//|| name === 'MAXIMILIAN'
		console.log('It is run!');
		age = 31;
	}
	function incrementAge () { age += 1;}
	function changeName () { name = 'Maximilian';}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click="{incrementAge}">Change Age</button>
<button on:click="{changeName}">Change Name</button>
