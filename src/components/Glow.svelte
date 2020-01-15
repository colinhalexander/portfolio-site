<script>
  import { spring } from 'svelte/motion'

  export let size, top, left

  const glowSize = size[0] * 0.02

  let modTop = spring(top * size[0] / (window.innerHeight * 0.9), {
    stiffness: 0.05,
    damping: 0.8
  })
  
  let modLeft = spring(left * size[1] / window.innerWidth, {
    stiffness: 0.05,
    damping: 0.8
  })

  setInterval(() => {
    $modTop = top * size[0] / (window.innerHeight * 0.9) + marginOfError(size[0])
    $modLeft = left * size[1] / window.innerWidth + marginOfError(size[1])
  }, 1200)

  function marginOfError(scale) {
    return Math.random() * scale / 1.5 * (Math.random() > 0.5 ? -1 : 1)
  }
</script>

<div style={`height: ${glowSize}px;
             width: ${glowSize}px;
             top: ${$modTop}px;
             left: ${$modLeft}px;
             border-radius: ${glowSize[0] / 2}px`
            }
>
</div>

<style>
  div {
    position: absolute;
    background-color: rgba(255, 255, 255, 0.5);
    box-shadow: 0 0 15px 2px white;
  }
</style>