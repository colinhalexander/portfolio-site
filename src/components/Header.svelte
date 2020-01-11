<script>
  import { fade } from 'svelte/transition'
  import AnimationLayer from './AnimationLayer.svelte'

  let initialSize = [window.innerHeight * 0.9, window.innerWidth]
  
  window.onresize = () => {
    initialSize = [window.innerHeight * 0.9, window.innerWidth]
  }

  let show = false
  setTimeout(() => {
    show = true
  }, 200);
</script>

<AnimationLayer size={initialSize} depth={-1}/>
{#if show}
  <div transition:fade={{delay: 400, duration: 1000}}>
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
    align-items: flex-start;
    justify-content: center;
    width: 100%;
    height: 90vh;
    color: white;
    padding-left: 5%;
    margin: 0;
  }

  div > * {
    width: 90%;
  }

  h1 {
    font-size: 40px;
    font-weight: 500;
    margin-bottom: 5px;
  }

  h2 {
    font-size: 24px;
    width: 70%;
  }
</style>