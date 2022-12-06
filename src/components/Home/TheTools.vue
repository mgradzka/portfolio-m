<template>
  <div class="tools flex">
    <div class="tools-container--1 flex">
      <div class="tools-container flex">
        <font-awesome-icon icon="fa-brands fa-html5" class="fa-brands" />
        <span>HTML</span>
      </div>
      <div class="tools-container flex">
        <font-awesome-icon icon="fa-brands fa-css3-alt" class="fa-brands" />
        <span>CSS</span>
      </div>
      <div class="tools-container flex">
        <!-- <i class="fa-brands fa-js"></i> -->
        <font-awesome-icon icon="fa-brands fa-js" class="fa-brands" />
        <span>JS</span>
      </div>
      <div class="tools-container flex">
        <font-awesome-icon icon="fa-brands fa-vuejs" class="fa-brands" />
        <span>VUE.JS</span>
      </div>
    </div>
    <div class="tools-container--1 flex">
      <div class="tools-container flex">
        <font-awesome-icon icon="fa-brands fa-node-js" class="fa-brands" />
        <span>NODE.JS</span>
      </div>
      <div class="tools-container flex">
        <font-awesome-icon icon="fa-brands fa-github" class="fa-brands" />
        <span>GITHUB</span>
      </div>
      <div class="tools-container flex">
        <font-awesome-icon icon="fa-brands fa-git-alt" class="fa-brands" />
        <span>GIT</span>
      </div>
      <div class="tools-container flex">
        <font-awesome-icon icon="fa-brands fa-figma" class="fa-brands" />
        <span>FIGMA</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    setPink() {},
  },
};
</script>

<style scoped>
.tools {
  background-color: var(--mainbackground);
  flex-flow: row;
  gap: 5rem;
  justify-content: center;
  padding-bottom: 10rem;
}

.tools-container--1 {
  gap: 5rem;
}

.tools-container {
  flex-direction: column;
  gap: 0.5rem;
}

.tools-container span {
  font-size: 1rem;
  text-align: center;
}

.fa-brands:hover,
span:hover {
  color: var(--pinkdark);
  transition: 0.4s;
  -webkit-transition: 0.4s;
  -moz-transition: 0.4s;
  -ms-transition: 0.4s;
  -o-transition: 0.4s;
}

@media (max-width: 1200px) {
  .tools-container span {
    font-size: 1.4rem;
  }
}

@media (max-width: 544px) {
  .tools {
    flex-direction: column;
    align-items:center;
    gap:4rem;
    padding-bottom:4rem
  }

  .tools-container--1 {
    gap:4rem
  }

  span {
    font-size: 1.4rem
  }
}
</style>
