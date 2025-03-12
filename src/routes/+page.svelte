<script>
	import Piece from '$lib/Piece.svelte'

	const components = [
		{props: {text: "CPU", href: "/CPU", className: "CPU"}, color: "#F04040"},
		{props: {text: "Memória", href: "/Memoria", className: "mem"}, color: "#40D040"},
		{props: {text: "I/O", href: "/IO", className: "IO"}, color: "#4040C0"}];
</script>

<div id="header">
	<h1>DIVE TO THE CORE</h1>

	<div id="motherboard">
		{#each components as comp}
			<Piece {...comp.props} --color={comp.color}/>
		{/each}
	</div>
	
</div>



<style>
	#header {
		top: 0px;
		height: 60vw;
		width: 100vw;
		display: flex;
		flex-wrap: wrap;
		flex-direction: column;
		justify-content: flex-start;
		align-content: center;
	}

	h1 {
		height: 8vw;
		font-size: 6vw;
		color: white;
		text-align: center;
		margin: 3vh 0vh;
	}

	#motherboard {
		height: 40vw;
		aspect-ratio: 2/1;
		background-color: #202040;
		border-radius: 2vw;
		box-shadow: rgb(0, 0, 0) 0px 20px 30px -10px;
	}
</style>