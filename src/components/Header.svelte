<script>
  import { fade } from 'svelte/transition'
  import AnimationLayer from './AnimationLayer.svelte'
  
  let initialSize = [window.innerHeight * 0.9, window.innerWidth]
  window.onresize = () => {
    initialSize = [window.innerHeight * 0.9, window.innerWidth]
  }

  let top = initialSize[0] / 2, left = initialSize[1] / 2
  const trackMouse = (e) => {
    top = e.clientY
    left = e.clientX
  }

  let show = false
  setTimeout(() => {
    show = true
  }, 800);
</script>

<AnimationLayer {top} {left} size={initialSize} depth={-1}/>
{#if show}
  <div transition:fade={{ delay: 400, duration: 1000 }} on:mousemove={trackMouse} >
    <h1>Colin Alexander</h1>
    <h2>Full-stack developer working in React, Node, and Ruby on Rails.</h2>
  </div>
{/if}

<style>
  div {
    position: absolute;
    top: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    background: radial-gradient(rgba(173, 216, 230, 0.3), rgba(173, 216, 230, 0.068));
    width: 100%;
    height: 90vh;
    color: white;
    margin: 0;
  }

  div > * {
    width: max-content;
    text-shadow: 0 0 8px rgba(0, 0, 0, 0.2);
  }

  h1 {
    font-size: 50px;
    font-weight: 500;
    margin-bottom: 5px;
    width: 70%;
  }

  h2 {
    font-size: 24px;
    width: 70%;
  }
</style>