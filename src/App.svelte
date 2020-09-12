<script>
	let clientWidth = document.body.clientWidth;
</script>

<style>
  .container {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    overflow: hidden;
  }
  .target-container {
    position: absolute;
    width: 150px;
    height: 150px;
    animation: moving 1s infinite linear;
  }

  @keyframes moving {
    0% {
      transform: translate3d(0%, 0, 0);
    }
    25% {
      transform: translate3d(25%, 0, 0);
    }
    50% {
      transform: translate3d(50%, 0, 0);
    }
    75% {
      transform: translate3d(75%, 0, 0);
    }
    100% {
      transform: translate3d(100%, 0, 0);
    }
  }
</style>

<div class="container">
  {#each [...Array(Math.ceil((clientWidth * 2) / 150)).keys()] as _, i}
    <div class="target-container" style=" left: {-clientWidth + 150 * i}px;">
      <svg viewBox="0 0 10 10" xmlns="http://www.w3.org/2000/svg">
        <g>
          <circle cx="5" cy="5" r="4" fill="red" />
          <circle cx="5" cy="5" r="3" fill="white" />
          <circle cx="5" cy="5" r="2" fill="red" />
          <circle
            on:click={() => console.log('hit')}
            cx="5"
            cy="5"
            r="1"
						fill="gold"/>
						<!-- <text x="5" y="5.5" text-anchor="middle" font-size="1.7" >A</text> -->

        </g>
      </svg>
    </div>
  {/each}
</div>
