<template>
      <footer class="flex">
        <span>&#169;2022 Martyna Grądzka</span>
        <div class="flex">
          <a
            href="https://www.linkedin.com/in/martyna-gradzka/"
            target="_blank"
            class="uppercase"
            >Linkedin</a
          >
          <a
            href="https://github.com/mgradzka"
            target="_blank"
            class="uppercase"
            >Github</a
          >
        </div>
      </footer>
</template>

<script>
export default {
    
}
</script>

<style scoped>
footer {
  background-color: var(--greyfont);
  padding: 2rem 5rem;
  justify-content: space-between;
  margin-top: auto
}

footer span,
footer a {
  color: white;
  font-size: 1.2rem;
}
footer div {
  gap: 4rem;
}

</style>