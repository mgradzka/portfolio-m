<template>
  <article class="details">
    <h4>{{ category[2].headings[0] }}</h4>
    <p>
      {{ category[2].description.one }}
    </p>
    <p>
      {{ category[2].description.two }}
    </p>
    <img
      :src="`../../assets/${category[2].images.one}`"
      class="development"
      alt=""
    />
 <h4>{{ category[2].headings[1] }}</h4>
    <p>
      {{ category[2].description.three }}
    </p>
  
    <img
      :src="`../../assets/${category[2].images.two}`"
      class="development"
      alt=""
    />

     <h4>{{ category[2].headings[2] }}</h4>
    <p>
      {{ category[2].description.four }}
    </p>
      <base-heading>Let's work together on a new project!</base-heading>
  <base-container>
    <router-link to="/contact"
      ><base-button>Contact me</base-button></router-link
    >
    <router-link to="/case"><base-button>Other cases</base-button></router-link>
  </base-container>

 
  </article>
</template>

<script>
export default {
  inject: ["category"],
};
</script>
