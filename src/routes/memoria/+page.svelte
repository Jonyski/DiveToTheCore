<script>
	import Piece from '$lib/Piece.svelte'
	import Title from '$lib/Title.svelte'

	const components = [
		{props: {text: "RAM", href: "/memoria/RAM", className: "RAM"}, color: "#F0B030"},
		{props: {text: "MMU", href: "/memoria/MMU", className: "MMU"}, color: "#f3fa6e"},
		{props: {text: "Cache", href: "/memoria/cache", className: "memCache"}, color: "#FF8030"},
		{props: {text: "Memória Secundária", href: "/memoria/secundaria", className: "secundaria"}, color: "#F09030"}];
</script>

<div id="header">
	<Title text="MEMÓRIA"/>

	<div id="memoria">
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

	#memoria {
		height: 40vw;
		aspect-ratio: 2/1;
		background-color: #EBD44D;
		border-radius: 2vw;
		box-shadow: rgb(0, 0, 0) 0px 20px 30px -10px;
	}
</style>