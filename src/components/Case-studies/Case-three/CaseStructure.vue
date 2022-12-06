<template>
  <article class="details">
    <h4>{{ category[0].headings[1] }}</h4>
    <p>
      {{ category[0].description.one }}
    </p>
    <img
      :src="`../../assets/${category[0].images.one}`"
      class="development"
      alt=""
    />
 <h4>{{ category[0].headings[2] }}</h4>
    <p>
      {{ category[0].description.two }}
    </p>
    <p>
      {{ category[0].description.three }}
    </p>
    <img
      :src="`../../assets/${category[0].images.two}`"
      class="development"
      alt=""
    />
     <h4>{{ category[0].headings[3] }}</h4>
    <p>
      {{ category[0].description.four }}
    </p>
    <p>
      {{ category[0].description.five }}
    </p>
  </article>
</template>

<script>
export default {
  inject: ["category"],
};
</script>
