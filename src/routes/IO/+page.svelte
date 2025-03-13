<script>
	import Piece from '$lib/Piece.svelte'

	const components = [
		{props: {text: "Periféricos", href: "/IO/perifericos", className: "perifericos"}, color: "#566BE3"},
		{props: {text: "Controladores", href: "/IO/controladores", className: "controladores"}, color: "#4C3AB0"},
		{props: {text: "Portas", href: "/IO/portas", className: "portas"}, color: "#672CC7"}];
</script>

<div id="header">
	<h1>I/O</h1>

	<div id="IO">
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

	#IO {
		height: 40vw;
		aspect-ratio: 2/1;
		background-color: #4040C0;
		border-radius: 2vw;
		box-shadow: rgb(0, 0, 0) 0px 20px 30px -10px;
	}
</style>