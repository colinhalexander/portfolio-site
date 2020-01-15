<script>
  import { fade } from 'svelte/transition'

  import Glow from './Glow.svelte'

  export let size, depth, top, left
</script>

<div class="animation-layer"
  style={`height: ${size[0]}px;
          width: ${size[1]}px;
          z-index: ${depth};`
        }
>
  {#if depth < -1}
    <Glow {top} {left} {size} />
  {/if}
  {#if size[0] > 10}
    <svelte:self
      {top}
      {left}
      size={depth < -1 ? size.map(n => n/1.1) : size}
      depth={depth - 1}
    />
  {/if}
</div>

<style>
  .animation-layer {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    background: rgba(0, 133, 194, 0.05);
    border-radius: 5px;
  }
</style>