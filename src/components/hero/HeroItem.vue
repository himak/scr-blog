<template>
  <li class="hero-item" v-for="post in posts" :key="post.id">
    <RouterLink to="/post">
      <article>
        <img :src="post.photo" alt="image" />
        <div class="content">
          <span class="tag">{{ post.tag }}</span>
          <h2 class="title">{{ post.title }}</h2>
          <span class="button">Read more</span>
        </div>
      </article>
    </RouterLink>
  </li>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { RouterLink } from 'vue-router';

interface Post {
  id: number;
  title: string;
  tag?: string;
  photo: string;
}

const posts: Post = ref([
  {
    id: 1,
    title: 'Prečo je čistý kód taký dôležitý?',
    tag: 'know-how',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2022/05/shutterstock_1851882700small-1920x1280.png',
  },
  {
    id: 2,
    title: 'Veľký prehľad videokonferenčných aplikácií',
    tag: 'know-how',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2021/05/Confcall_apps2-1920x1280.jpg',
  },
  {
    id: 3,
    title: 'Aj váš marketing sa dá automatizovať, časť 1',
    tag: 'marketing',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2020/07/AI_marketing_1-1920x1261.jpg',
  },
  {
    id: 4,
    title: '6 krokov, ktoré vám pomôžu vybudovať lepšiu firmu, časť 1.',
    tag: 'novinky',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2020/12/a-1920x1280.jpg',
  },
]);
</script>

<style scoped lang="scss">
$content-text: #fff;
$button-border: #fff;
$button-border-hover: #ff002c;
$button-text-hover: #ff002c;

.hero-item {
  width: 25%;

  a {
    text-decoration: none;
    text-align: center;

    &:hover,
    &:focus {
      img {
        transform: scale(1.02);
        transition: transform 0.3s ease-in-out;
      }

      .button {
        transition: all 0.3s ease-in-out;
        border-color: $button-border-hover;
        color: $button-text-hover;
      }
    }
  }

  article {
    position: relative;
  }

  img {
    width: 100%;
    object-fit: cover;
    transition: transform 0.3s ease-in-out;
  }

  .content {
    position: absolute;
    bottom: 3.75em; // 60/16
    color: $content-text;
    width: 100%;
  }

  .tag {
    font-size: 0.625em; // 10/16
    margin-bottom: 0.5em;
    display: inline-block;
    text-transform: uppercase;
  }

  .title {
    font-size: 1.25em;
    line-height: 1.25em;
    font-weight: 600;
    padding: 0 1em;
    margin-bottom: 1em;
    overflow: hidden;
    text-overflow: ellipsis;
    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
  }

  .button {
    font-size: 0.625em; // 10/16
    font-weight: 600;
    border: 1px solid $button-border;
    padding: 1em 1.5em;
    transition: all 0.3s ease-in-out;
  }
}

@media (min-width: 768px) {
  .hero-item {
    img {
      min-height: 560px;
    }
  }
}

@media (max-width: 768px) {
  .hero-item {
    img {
      height: 280px;
    }
  }
}
</style>
