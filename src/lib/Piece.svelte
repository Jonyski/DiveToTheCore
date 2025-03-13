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
	}

	a:hover {
		transform: scale(1.05);
		box-shadow: rgba(0, 0, 25, 0.6) 0px 25px 35px -15px;
	}


	/*------------------------------
	    MOTHERBOARD COMPONENTS 
	 -----------------------------*/
	.CPU {
		margin: 3vw 0vw 0vw 3vw;
		width: 35vw;
		height: 14vw;
		line-height: 14vw;
	}

	.mem {
		margin: 22vw 3vw 0vw 3vw;
    	width: 35vw;
    	height: 14vw;
    	line-height: 14vw;

	}

	.IO {
		margin: 3vw 60vw;
		width: 16.5vw;
		height: 33vw;
		line-height: 32vw;
	}


	/*------------------------------
	         IO COMPONENTS 
	 -----------------------------*/
	 .perifericos {
	 	margin: 21.5vw 0vw 0vw 42vw;
	 	width: 35vw;
	 	height: 14vw;
	 	line-height: 14vw;
	 }

	 .controladores {
	 	margin: 21.5vw 0vw 0vw 3vw;
	 	width: 35vw;
	 	height: 14vw;
	 	line-height: 14vw;
	 }

	 .portas {
	 	margin: 3vw 0vw 0vw 3vw;
	 	width: 74vw;
	 	height: 14vw;
	 	line-height: 14vw;
	 }


	 /*------------------------------
	         IO COMPONENTS 
	 -----------------------------*/
	 .MMU {
	 	margin: 3vw 0vw 0vw 3vw;
    	width: 20vw;
    	height: 34vw;
    	line-height: 14vw;
	 }

	 .RAM {
		 margin: 3vw 0vw 0vw 42vw;
	     width: 35vw;
	     height: 14vw;
	     line-height: 14vw;
	 }

	 .secundaria {
	 	margin: 20vw 0vw 0vw 25.5vw;
 	    width: 51.5vw;
 	    height: 17vw;
 	    line-height: 14vw;
	 }

	 .memCache {
		margin: 3vw 0vw 0vw 25.5vw;
    	width: 14vw;
    	height: 14vw;
    	line-height: 14vw;
	 }
</style>