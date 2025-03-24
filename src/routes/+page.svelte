<script>
	import Piece from '$lib/Piece.svelte'
	import Title from '$lib/Title.svelte'

	const components = [
		{props: {text: "CPU", href: "/CPU", className: "CPU"}, color: "#DB425E"},
		{props: {text: "Memória", href: "/memoria", className: "mem"}, color: "#EBD44D"},
		{props: {text: "I/O", href: "/IO", className: "IO"}, color: "#5547CC"}];
</script>


<header>
	<Title text="DIVE TO THE CORE"/>

	<div id="motherboard">
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

	#motherboard {
		height: 40vw;
		aspect-ratio: 2/1;
		background-color: #202040;
		border-radius: 2vw;
		box-shadow: rgb(0, 0, 0) 0px 20px 30px -10px;
	}
</style>