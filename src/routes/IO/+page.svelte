<script>
	import Piece from '$lib/Piece.svelte'
	import Title from '$lib/Title.svelte'

	const components = [
		{props: {text: "Periféricos", href: "/IO/perifericos", className: "perifericos"}, color: "#4405A3"},
		{props: {text: "Controladores", href: "/IO/controladores", className: "controladores"}, color: "#477ED6"},
		{props: {text: "Portas", href: "/IO/portas", className: "portas"}, color: "#5E30C2"}];
</script>


<header>
	<Title text="I/O"/>

	<div id="IO">
		{#each components as comp}
			<Piece {...comp.props} --color={comp.color}/>
		{/each}
	</div>
</header>


<style>
	header {
		top: 0px;
		height: 60vw;
		width: 100vw;
		display: flex;
		flex-wrap: wrap;
		flex-direction: column;
		justify-content: flex-start;
		align-content: center;
	}

	#IO {
		height: 40vw;
		aspect-ratio: 2/1;
		background-color: #5547CC;
		border-radius: 2vw;
		box-shadow: rgb(0, 0, 0) 0px 20px 30px -10px;
	}
</style>