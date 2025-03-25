<script>
	import Piece from '$lib/Piece.svelte'
	import Title from '$lib/Title.svelte'

	const components = [
		{props: {text: "ALU", href: "/CPU/ALU", className: "ALU"}, color: "#f72874"},
		{props: {text: "CU", href: "/CPU/CU", className: "CU"}, color: "#f2275a"},
		{props: {text: "Regristradores", href: "/CPU/registradores", className: "reg"}, color: "#db1446"},
		{props: {text: "Decodificador de Instruções", href: "/CPU/DI", className: "DI"}, color: "#c7243c"},
		{props: {text: "Clock", href: "/CPU/clock", className: "clock"}, color: "#eb3434"},
		{props: {text: "Cache", href: "/CPU/cache", className: "cpuCache"}, color: "#ed4126"}];
</script>


<header>
	<Title text="CPU"/>

	<div id="CPU">
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

	#CPU {
		height: 40vw;
		aspect-ratio: 2/1;
		background-color: #DB425E;
		border-radius: 2vw;
		box-shadow: rgb(0, 0, 0) 0px 20px 30px -10px;
	}
</style>