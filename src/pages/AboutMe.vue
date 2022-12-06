<template>
  <main class="about">
    <article>
      <div class="flex">
        <pink-circle></pink-circle>
        <div class="passion flex">
          <h2>{{ aboutMe[0].title }}</h2>
          <h4>{{ aboutMe[0].description }}</h4>
        </div>
      </div>
      <p>{{ aboutMe[0].paragraph1 }}</p>
      <br /><br />
      <p>{{ aboutMe[0].paragraph2 }}</p>
    </article>

    <article>
      <div class="flex">
        <blue-circle></blue-circle>
        <div class="passion flex">
          <h2>{{ aboutMe[1].title }}</h2>
          <h4>{{ aboutMe[1].description }}</h4>
        </div>
      </div>
      <p>{{ aboutMe[1].paragraph1 }}</p>
      <br /><br />
      <p>{{ aboutMe[1].paragraph2 }}</p>
    </article>
  </main>
  <div class="flex img-container">
    <img src="../assets/about1.png" alt="" />
    <img src="../assets/about2.png" alt="" />
  </div>
<base-heading>Now you know me better, right? :)</base-heading>
  <base-container>
    <router-link to="/case"><base-button>Case studies</base-button></router-link>
    <router-link to="/contact"><base-button>Contact me</base-button></router-link>
  </base-container>
</template>

<script>
export default {

  data() {
    return {
      aboutMe: [
        {
          title: "Background",
          description: "Something about myself",
          paragraph1:
            "I am Martyna and I come from Poland. My higher education started in my home country, where I got a bachelor degree in Scandinavian Studies. I wanted to experience and learn more, and that’s why I decided to move to Denmark to study there. I have always been interested in art and design, but when I started studying Multimedia Design, I became crazy fascinated about coding!",
          paragraph2:
            "Currently, I spend a lot of time learning about programming, because I feel that this is what I want to do in the future. But I also take great pleasure in combining web development and web design together, and I am dedicated to what I do. I am hard-working and persistent, when I have a task to do, I devote myself 100% to it.",
        },
        {
          title: "Passion",
          description: "Because what is life without that? ;)",
          paragraph1:
            "My biggest passion in life is traveling. I love the fact how free you can feel when you travel and how it shapes your personality. My best kind of trip is being around nature, especially mountains, without any special plan, and just following the adventure.",
          paragraph2:
            "I also love ski jumping! I am the happiest on a ski jumping hill, supporting my favorite athletes and having fun with my friends. Because that’s what ski jumping is all about – being a part of the community and enjoying the sport.",
        },
      ],
    };
  },
};
</script>

<style scoped>
.about article:first-child  div {
  padding-top: 4rem
}
main {
  padding: 10rem 0 0;
}
article {
  padding: 0rem 20rem 10rem;
}
.about,
.desc {
  padding-right: 40rem;
}
.about > article > div {
  flex-direction: row;
  gap: 1rem;
  margin-bottom: 3rem;
}

.about .btn--container,
.case > div {
  justify-content: center;
  margin-top: 5rem;
}

.passion {
  flex-direction: column;
}

article div {
  align-self: end;
}

.about svg {
  align-self: end;
}

.img-hidden {
  display: none;
}

.img-container {
  padding-left: 20rem;
  gap: 4rem;
}

img {
  width: 30rem;
}

.about h2 {
  margin-bottom: 0;
}

.about-btn {
  flex-direction: column;
  align-items: center;
  gap: 2rem;
  padding-bottom: 10rem;
}

@media (max-width: 1200px) {
  article {
    padding: 10rem 20rem 0 10rem;
  }

  .about {
    padding-right: 0
  }

  .img-container {
    padding: 10rem 0 0 10rem
  }
}

@media (max-width: 544px) {
article {
  padding: 5rem
}

.about article:first-child  div {
  padding-top: 0
}

.img-container {
  flex-direction: column;
  padding:5rem
}

p {
  font-size: 1.6rem
}

.about article:first-child  {
  padding-bottom: 5rem
}
}
</style>
