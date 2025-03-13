<script>
	let { href, text, className } = $props()

</script>

<a {href} class={className}>
	{text}
</a>

<style>
	a {
		color: white;
		background-color: var(--color);
		position: absolute;
		text-align: center;
		border-radius: 1vh;
		box-shadow: rgba(0, 0, 25, 0.75) 0px 20px 30px -10px;
		font-size: 2vw;
		text-decoration: none;
		transition-duration: 0.3s;
		font-family: "Inconsolata", monospace;
		font-optical-sizing: auto;
		font-weight: 300;
		font-style: normal;
		font-variation-settings: "wdth" 100;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	a:hover {
		transform: scale(1.05);
		box-shadow: rgba(0, 0, 25, 0.2) 0px 25px 35px -15px;
	}


	/*------------------------------
	    MOTHERBOARD COMPONENTS 
	 -----------------------------*/
	.CPU {
		margin: 3vw 0vw 0vw 3vw;
		width: 35vw;
		height: 14vw;	
	}

	.mem {
		margin: 22vw 3vw 0vw 3vw;
    	width: 35vw;
    	height: 14vw;
	}

	.IO {
		margin: 3vw 60vw;
		width: 16.5vw;
		height: 33vw;	
	}


	/*------------------------------
	         IO COMPONENTS 
	 -----------------------------*/
	.perifericos {
		margin: 21.5vw 0vw 0vw 42vw;
		width: 35vw;
		height: 14vw;	 
	}

	.controladores {
		margin: 21.5vw 0vw 0vw 3vw;
		width: 35vw;
		height: 14vw;	 
	}

	.portas {
		margin: 3vw 0vw 0vw 3vw;
		width: 74vw;
		height: 14vw;	 
	}

	.perifericos, .controladores, .portas {
		box-shadow: rgba(20, 0, 100, 0.5) 0px 20px 30px -10px;
	}
	/*------------------------------
	       MEMORY COMPONENTS 
	-----------------------------*/
	.MMU {
		margin: 3vw 0vw 0vw 3vw;
    	width: 20vw;
    	height: 34vw;	 
    }

	.RAM {
		margin: 3vw 0vw 0vw 42vw;
	    width: 35vw;
	    height: 14vw;	 
	}

	.secundaria {
		margin: 20vw 0vw 0vw 25.5vw;
 	   width: 51.5vw;
 	   height: 17vw;	 
 	}

	.memCache {
		margin: 3vw 0vw 0vw 25.5vw;
    	width: 14vw;
    	height: 14vw;	 
    }

	.MMU, .RAM, .secundaria, .memCache {
		color: black;
		box-shadow: rgba(120, 0, 20, 0.6) 0px 20px 30px -15px;
	}

	.MMU:hover, .RAM:hover, .secundaria:hover, .memCache:hover {
		color: black;
		box-shadow: rgba(120, 0, 20, 0.4) 0px 20px 35px -15px;
	}


	/*------------------------------
	        CPU COMPONENTS 
	-----------------------------*/
	.ALU {
		margin: 3vw 0vw 0vw 3vw;
		width: 21vw;
		height: 34vw;	 
	}

	.CU {
		margin: 3vw 0vw 0vw 27vw;
    	width: 10vw;
    	height: 14vw;	 
    }

	.reg {
		margin: 19vw 0vw 0vw 27vw;
		width: 19vw;
		height: 18vw;	 
	}

	.DI {
		margin: 3vw 0vw 0vw 40vw;
    	width: 20vw;
    	height: 14vw;
	}

	.clock {
		margin: 3vw 0vw 0vw 63vw;
    	width: 14vw;
    	height: 14vw;
	}

	.cpuCache {
		margin: 19vw 0vw 0vw 49vw;
    	width: 28vw;
    	height: 18vw;
	}

	.ALU, .CU, .reg, .DI, .clock, .cpuCache {
		box-shadow: rgba(80, 0, 20, 0.4) 0px 20px 35px -15px;
	}

</style>