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

<section>
	<h1>O COMPUTADOR</h1>
	<hr/>
	<blockquote>Você já parou para se perguntar <strong>o que</strong> é um computador?</blockquote>

	<p>Para os propósitos desse site, um computador é uma máquina programável capaz de processar dados e executar instruções. Sob a perspectiva da organização e arquitetura de computadores, ele é um sistema integrado composto por componentes físicos (hardware) e lógicos (software) que trabalham em conjunto para cumprir suas funções.</p>
	
	<p>Neste texto, exploraremos os fundamentos técnicos de um computador, desde sua definição até o básico de sua estrutura interna, passando pelos princípios da Arquitetura de Von Neumann — o modelo que ainda serve de base para a maioria dos computadores modernos - e uma breve história da evolução dos computadores.</p>

	<img class="small" alt="gif de um computador fofo" src="https://i.pinimg.com/originals/3d/74/68/3d7468d1bb523674726ba6934a396566.gif">
</section>

<section>
	<h2>Definição formal</h2>
	<hr/>

	<p>Um computador pode ser definido como:</p>

	<blockquote>"Um sistema eletrônico digital programável que recebe dados de <strong>entrada</strong> (input), <strong>processa-os</strong> mediante um conjunto de instruções <strong>armazenadas</strong> (programa), e produz resultados/<strong>saídas</strong> úteis (output)."</blockquote>

	<p>Essa definição abrange 3 elementos que são de nosso mais alto interesse:</p>

	<ol>
		<li><strong>Entrada/Saída (Input/Output):</strong> São, por exemplo, os cliques de um mouse ou as imagens exibidas em um monitor.</li>
		<li><strong>Processamento:</strong> É a manipulação de dados, basicamente o motivo de computadores existirem!</li>
		<li><strong>Memória:</strong> É onde as instruções e os dados necessários para um programa são armazenados.</li>
	</ol>

	<p>Não é a toa que essas são as 3 partes básicas do computador que estão sendo representadas no diagrama interativo no topo desta página.</p>

	<blockquote>Caso não tenha reparado ainda, você pode clicar nas partes do diagrama para "navegar" pelos componentes do computador. Vai lá e dá uma testada! Mas depois volte aqui para continuar sua leitura...</blockquote>

	<p>A organização dos computadores nestas 3 partes principais é chamada de <i>Modelo de Von Neumann</i>, pois foi proposta pelo matemático, físico e cientista da computação, John von Neumann, em 1945.</p>

	<img class="medium left" alt="foto de John von Neumann" src="https://www.economist.com/sites/default/files/images/2021/10/articles/main/20211009_bkp002.jpg">

	<p>Como você deve imaginar, estes componentes precisam estar interligados de alguma forma para que o computador funcione, e essa ligação é o trabalho do <strong><a href="https://pt.wikipedia.org/wiki/Barramento_(computa%C3%A7%C3%A3o)">barramento</a></strong>. Já que não temos uma página dedicada ao barramento, vamos dar a ele uma seção própria aqui nesta página.</p>
</section>

<section>
	<h2>O Barramento</h2>
	<hr/>

	<p>Você pode pensar no barramento como sendo o caminho pelo qual as informações são transmitidas quando precisam ir de um componente a outro. Nós podemos categorizar logicamente os tipos de barramento de acordo com os tipos de informações que eles transmitem:</p>

	<ul>
		<li><strong>Barramento de Dados (Data Bus):</strong> transporta dados entre CPU, memória e periféricos.</li>
		<li><strong>Barramento de Endereços (Adress Bus):</strong> carrega endereços de dados na memória.</li>
		<li><strong>Barramento de Controle (Control Bus):</strong> gerencia operações como leitura/escrita.</li>
	</ul>

	<p>Tenha em mente que essa separação é primariamente lógica, e não necessariamente é refletida na separação física do barramento. Existem placas que podem ter realmente esses 3 barramentos individuais, mas geralmente um barramento pode servir mais de uma função. Um exemplo clássico é o <a href="https://pt.wikipedia.org/wiki/Barramento_frontal">Front-Side Bus</a> (FSB) em computadores antigos, que conectava a CPU ao chipset norte (Northbridge). Ele combinava funções de dados, endereços e controle em um único barramento físico. Em sistemas modernos, o FSB foi substituído por tecnologias mais eficientes como o <a href="https://en.wikipedia.org/wiki/Intel_QuickPath_Interconnect">QuickPath Interconnect</a> (QPI) da Intel.

	<p>Outro exemplo importante é o <a href="https://pt.wikipedia.org/wiki/PCI_Express">PCI Express</a> (PCIe), o barramento padrão para placas de expansão atuais. Diferente dos barramentos paralelos tradicionais, o PCIe usa comunicação serial em múltiplas vias (lanes), onde cada via transmite pacotes que contêm dados, endereços e informações de controle de forma integrada.</p>

	<p>Também é importante notarmos que a forma como cada componente se relaciona com o barramento é diferente. A CPU envia dados pelos 3 barramentos, mas não recebe nada pelo barramento de endereços. De forma complementar, a memória e a E/S não enviam nada pelo barramento de endereços, só recebem. O caso da E/S na verdade é mais delicado, pois ela só recebe dados por este barramento em sistemas com <strong><i>memory-mapped I/O</i></strong>, ou seja, em sistemas nos quais dispositivos de E/S são "vistos" como endereços de memória. Além disso, os <strong>caches</strong> têm barramentos dedicados que fazem suas conexões com a CPU. Em suma:</p>

	<table>
		<caption>Acesso ao Barramento</caption>
		<thead>
		    <tr>
		    	<th scope="col">Componente</th>
		    	<th scope="col">Barramento de Dados</th>
		    	<th scope="col">Barramento de Endereços</th>
		    	<th scope="col">Barramento de Controle</th>
		    </tr>
		</thead>
		<tbody>
		 	<tr>
		  		<th scope="row">CPU</th>
		  		<td>bidirecional</td>
		  		<td>só envia</td>
		  		<td>bidirecional</td>
			</tr>
			<tr>
		  		<th scope="row">Memória</th>
		  		<td>bidirecional</td>
		  		<td>só recebe</td>
		  		<td>bidirecional</td>
			</tr>
			<tr>
				<th scope="row">I/O</th>
				<td>bidirecional</td>
				<td>só recebe*</td>
				<td>bidirecional</td>
		  	</tr>
		</tbody>
	</table>

	<blockquote>*em sistemas com memory-mapped I/O</blockquote>

	<h3>Características Importantes dos Barramentos</h3>

	<p>Alguns aspectos técnicos fundamentais sobre barramentos incluem:</p>
	
	<ul>
		<li><strong>Largura:</strong> Número de bits que podem ser transmitidos simultaneamente (ex: barramento de 32 ou 64 bits)</li>
		<li><strong>Clock:</strong> Frequência de operação que determina a velocidade de transferência</li>
		<li><strong>Taxa de Transferência:</strong> Largura × Frequência (ex: barramento de 64 bits a 100 MHz = 800 MB/s)</li>
		<li><strong>Arbitragem:</strong> Mecanismo para resolver conflitos quando múltiplos dispositivos tentam usar o barramento simultaneamente</li>
	</ul>

	<p>Algo interessante de ser apontado é que a largura do barramento de endereços determina o espaço máximo de endereçamento de memória. Em arquiteturas tradicionais, um barramento de endereços com <strong>n bits</strong> pode endereçar até <strong>2<sup>n</sup></strong> posições de memória. Por exemplo, sistemas com barramento de endereços de 32 bits teoricamente suportam até 4GB de memória (2<sup>32</sup> = 4.294.967.296 endereços). No entanto, na prática, sistemas 32-bit costumam ter limitações adicionais que reduzem esse valor para cerca de 3-3.5GB. A arquitetura 64-bit, com seu espaço de endereçamento de 2<sup>64</sup>, eliminou esse gargalo, permitindo acesso a exabytes de memória (embora implementações atuais geralmente usem apenas 48 bits para endereçamento físico, o que ainda permite 256TB).</p>
</section>

<section>
	<h2>Uma breve história dos computadores</h2>
	<hr/>
</section>

<style>
	#motherboard {
		height: 40vw;
		aspect-ratio: 2/1;
		background-color: #202040;
		border-radius: 2vw;
		box-shadow: rgb(0, 0, 0) 0px 20px 30px -10px;
	}
</style>