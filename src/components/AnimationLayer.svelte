<script>
  export let size, depth
</script>

<div class="animation-layer"
  style={`height: ${size[0]}px;
          width: ${size[1]}px;
          z-index: ${depth};`
        }
>
  {#if size[0] > 10}
    <svelte:self size={size.map(n => n/1.1)} depth={depth - 1}/>
  {/if}
</div>

<style>
  .animation-layer {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgba(0, 94, 126, 0.5);
    box-shadow: 0 0 25px 5px rgba(173, 216, 230, 0.2);
  }
</style>