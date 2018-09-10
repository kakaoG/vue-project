<template>
  <article class="pie-chart">
    <div class="pie"
         :style="{
         '--size': size,
         '--rateBgColor': rateBgColor,
         animationDelay: `${-rate}s`,
         backgroundColor: bgColor}">
      <div class="rate"></div>
    </div>
    <slot></slot>
  </article>
</template>

<script>
export default {
  name: 'Pie',
  props: {
    size: {
      default: '200px',
      type: String
    },
    rate: {
      default: 0,
      type: Number
    },
    bgColor: {
      default: 'greenyellow',
      type: String
    },
    rateBgColor: {
      default: '#665',
      type: String
    }
  },
}
</script>

<style type="text/less" lang="css">
  .pie {
    --size: 200px;
    --rateBgColor: #665;
    --aniTime: 50s;
    position: relative;
    width: var(--size);
    height: var(--size);
    line-height: var(--size);
    border-radius: 50%;
    background: greenyellow linear-gradient(to right, transparent 50%, var(--rateBgColor) 0);
    text-align: center;
    overflow: hidden;
  }
  .pie .rate {
    position: absolute;
    width: 50%;
    height: 100%;
    top: 0;
    left: 50%;
    border-radius: 0 100% 100% 0;
    background-color: inherit;
    transform-origin: left;
    animation: spin var(--aniTime) linear infinite,
    bg calc(2*var(--aniTime)) step-end infinite;
    animation-delay: inherit;
    animation-play-state: paused;
  }

  @keyframes spin {
    to {
      transform: rotate(.5turn);
    }
  }

  @keyframes bg {
    50% {
      background-color: var(--rateBgColor);
    }
  }
</style>
