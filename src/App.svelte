<script>
	import Header from './components/Header.svelte'
	import NavBar from './components/NavBar.svelte'
	import About from './components/About.svelte'
	import Portfolio from './components/Portfolio.svelte'
	import Contact from './components/Contact.svelte'

	import { fade } from 'svelte/transition'

	let scrollPosition = 0
	document.body.onscroll = () => {
		scrollPosition = window.scrollY
	}

	const scrollToTop = () => {
		window.history.pushState({}, "", "/")
		window.scrollTo(0, 0)
	}
</script>

<Header/>
<NavBar/>
<main>
	{#if scrollPosition > window.innerHeight * 0.9}
		<button in:fade="{{ duration: 500 }}" on:click={scrollToTop}>
			<img src="https://img.icons8.com/ios-filled/50/000000/up.png" alt="scroll to top">
		</button>
	{/if}
	<About/>
	<Portfolio/>
	<Contact/>
</main>

<style>
@import url('https://fonts.googleapis.com/css?family=Libre+Franklin:400,500,700&display=swap');

	/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

:global(html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video) {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
	width: 100%;
	box-sizing: border-box;
}

/* HTML5 display-role reset for older browsers */
:global(article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section) {
	display: block;
}

:global(body) {
	line-height: 1;
	font-family: 'Libre Franklin', sans-serif;
}

:global(ol, ul) {
	list-style: none;
}

:global(blockquote, q) {
	quotes: none;
}

:global(blockquote:before, blockquote:after,
q:before, q:after) {
	content: '';
	content: none;
}

:global(table) {
	border-collapse: collapse;
	border-spacing: 0;
}

:global(html) {
	scroll-behavior: smooth;
}

:global(section) {
	display: flex;
	align-items: center;
	justify-content: center;
	width: 100vw;
	min-height: 100vh;
	border-bottom: solid 2px black;
}

:global(section > *) {
	width: max-content;
}

button {
	display: flex;
	align-items: center;
	justify-content: center;
	position: fixed;
	background-color: rgba(0, 158, 211, 0.3);
	top: 10px;
	right: 10px;
	width: 45px;
	height: 45px;
	border: solid 1px black;
	border-radius: 60px;
	color: white;
}

button > img {
	width: 30px;
	height: 30px;
}

button:hover {
	transform: scale(1.05);
}

</style>