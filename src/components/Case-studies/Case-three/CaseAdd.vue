<template>
  <article class="details">
    <h4>{{ category[1].headings[1] }}</h4>
    <p>
      {{ category[1].description.one }}
    </p>
    <p>
      {{ category[1].description.two }}
    </p>
    <img
      :src="`../../assets/${category[1].images.one}`"
      class="development"
      alt=""
    />
 <h4>{{ category[1].headings[2] }}</h4>
    <p>
      {{ category[1].description.three }}
    </p>
  
    <img
      :src="`../../assets/${category[1].images.two}`"
      class="development"
      alt=""
    />
 
  </article>
</template>

<script>
export default {
  inject: ["category"],
};
</script>
