<template>
  <div class="flex flex-wrap gap-5 p-5 items-center justify-center">
    <section class="playground" />

    <!-- source: Claire Parker-Jones @ dev.to "How to Create a Polka Dot Background with CSS" -->
    <section class="dots" />
    <!-- source: T. Afif @ CSS Challenges -->
    <section class="blocks" />
    <section class="rhomboid" />
    <section class="honeycomb" />
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style>
section {
  display: flex;
  width: 63vw;
  aspect-ratio: 16 / 9;
}
.playground {
  background-image: repeating-radial-gradient(#0000 0% 12%, #c39f76 13% 26%);
  background-size: 100px 100px;
  background-position: center;
}

.dots {
  background-image: radial-gradient(#999999 0.05rem, #f2f2f2 0.05rem);
  background-position: center;
  background-size: 1rem 1rem;
  // background-repeat: no-repeat;
}

.blocks {
  --s: 84px; /* control the size*/
  /* the colors */
  --c1: #f2f2f2;
  --c2: #cdcbcc;
  --c3: #999999;
  /* */
  --_g: 0 120deg, #0000 0;
  background: conic-gradient(
      from 0deg at calc(500% / 6) calc(100% / 3),
      var(--c3) var(--_g)
    ),
    conic-gradient(
      from -120deg at calc(100% / 6) calc(100% / 3),
      var(--c2) var(--_g)
    ),
    conic-gradient(
      from 120deg at calc(100% / 3) calc(500% / 6),
      var(--c1) var(--_g)
    ),
    conic-gradient(
      from 120deg at calc(200% / 3) calc(500% / 6),
      var(--c1) var(--_g)
    ),
    conic-gradient(
      from -180deg at calc(100% / 3) 50%,
      var(--c2) 60deg,
      var(--c1) var(--_g)
    ),
    conic-gradient(
      from 60deg at calc(200% / 3) 50%,
      var(--c1) 60deg,
      var(--c3) var(--_g)
    ),
    conic-gradient(
      from -60deg at 50% calc(100% / 3),
      var(--c1) 120deg,
      var(--c2) 0 240deg,
      var(--c3) 0
    );
  background-size: calc(var(--s) * 1.732) var(--s);
  /* sqrt(3) = 1.732 */
  // background-repeat: no-repeat;
}

.rhomboid {
  --c1: #ff847c;
  --c2: #e84a5f;
  --c3: #fecea8;
  --c4: #99b898;

  background: conic-gradient(
      from 45deg at 75% 75%,
      var(--c3) 90deg,
      var(--c1) 0 180deg,
      #0000 0
    ),
    conic-gradient(from -45deg at 25% 25%, var(--c3) 90deg, #0000 0),
    conic-gradient(from -45deg at 50% 100%, #0000 180deg, var(--c3) 0),
    conic-gradient(
      from -45deg,
      var(--c1) 90deg,
      var(--c2) 0 225deg,
      var(--c4) 0
    );
  background-size: 150px 150px; /* control the size here */
  // background-repeat: no-repeat;
}

.honeycomb {
  --s: 200px; /* control the size */

  background: repeating-conic-gradient(
        from 30deg,
        #0000 0 120deg,
        #3c3c3c 0 180deg
      )
      calc(0.5 * var(--s)) calc(0.5 * var(--s) * 0.577),
    repeating-conic-gradient(
      from 30deg,
      #1d1d1d 0 60deg,
      #4e4f51 0 120deg,
      #3c3c3c 0 180deg
    );
  background-size: var(--s) calc(var(--s) * 0.577);
  /* 0.577 = tan(30deg)*/
}
</style>
