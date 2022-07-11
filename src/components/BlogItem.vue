<template>
  <li class="blog-item" v-for="(post, index) in posts" :key="index">
    <RouterLink to="/post">
      <article>
        <img :src="post.photo" alt="image" :height="getRandomInt(200, 400)" />
        <div class="content">
          <span class="tag">{{ post.tag }}</span>
          <h2 class="title">{{ post.title }}</h2>
          <p class="body">{{ post.body }}</p>
          <span class="button">Read More</span>
        </div>
      </article>
    </RouterLink>
  </li>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { RouterLink } from 'vue-router';

interface Post {
  title: string;
  body: string;
  tag?: string;
  photo: string;
}

const posts: Post = ref([
  {
    title: 'Prečo je čistý kód taký dôležitý?',
    body: 'Čistý kód sa dobre číta a vyzná sa v ňom nielen osoba, ktorá ho napísala, ale aj hocikto iný. Kód je prehľadný, bez chýb a duplicít. Dá sa ľahko rozšíriť a na to, aby ho ostatní pochopili, nie je potrebný žiaden komentár. ',
    tag: 'know-how',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2022/05/shutterstock_1851882700small-1920x1280.png',
  },
  {
    title: 'Veľký prehľad videokonferenčných aplikácií',
    body: 'Neviete ktorá aplikácia je tá správna pre vaše potreby? Veríme, že daný prehľad aplikácií, ich plusov a mínusov, vám pomôže zorientovať sa a vybrať si to, čo vám najviac vyhovuje.',
    tag: 'know-how',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2021/05/Confcall_apps2-1920x1280.jpg',
  },
  {
    title: 'Aj váš marketing sa dá automatizovať, časť 1',
    body: 'Asi ste už počuli o automatizácii procesov v priemysle alebo vo výrobe. Je to jedna z najhorúcejších tém pre firmy, ktoré sa rozhodli opustiť tradičný model fungovania a začali s digitálnou transformáciou. Ale počuli ste o tom, že automatizovať môžete aj váš marketing?',
    tag: 'marketing',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2020/07/AI_marketing_1-1920x1261.jpg',
  },
  {
    title: '6 krokov, ktoré vám pomôžu vybudovať lepšiu firmu, časť 1.',
    body: 'Jasne zadefinované strategické a hodnotové smerovanie vašej spoločnosti môže byť rozhodujúcim faktorom na ceste k úspechu. ',
    tag: 'novinky',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2020/12/a-1920x1280.jpg',
  },
  {
    title: 'Veľký prehľad videokonferenčných aplikácií',
    body: 'Neviete ktorá aplikácia je tá správna pre vaše potreby? Veríme, že daný prehľad aplikácií, ich plusov a mínusov, vám pomôže zorientovať sa a vybrať si to, čo vám najviac vyhovuje.',
    tag: 'know-how',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2021/05/Confcall_apps2-1920x1280.jpg',
  },
  {
    title: 'Aj váš marketing sa dá automatizovať, časť 1',
    body: 'Asi ste už počuli o automatizácii procesov v priemysle alebo vo výrobe. Je to jedna z najhorúcejších tém pre firmy, ktoré sa rozhodli opustiť tradičný model fungovania a začali s digitálnou transformáciou. Ale počuli ste o tom, že automatizovať môžete aj váš marketing?',
    tag: 'marketing',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2020/07/AI_marketing_1-1920x1261.jpg',
  },
  {
    title: 'Prečo je čistý kód taký dôležitý?',
    body: 'Čistý kód sa dobre číta a vyzná sa v ňom nielen osoba, ktorá ho napísala, ale aj hocikto iný. Kód je prehľadný, bez chýb a duplicít. Dá sa ľahko rozšíriť a na to, aby ho ostatní pochopili, nie je potrebný žiaden komentár. ',
    tag: 'know-how',
    photo:
      'https://www.scrtechnologies.sk/wp-content/uploads/2022/05/shutterstock_1851882700small-1920x1280.png',
  },
]);

function getRandomInt(min: number, max: number): number {
  min = Math.ceil(min);
  max = Math.floor(max);
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
</script>

<style scoped lang="scss">
$content-text: #020500;
$button-text-hover: #ff002c;

.blog-item {
  width: 33.3333333333%;
  padding: 0.625em; // 20/16

  a {
    text-decoration: none;
    text-align: center;

    &:hover,
    &:focus {
      .title,
      .button {
        color: $button-text-hover;
      }
    }
  }

  img {
    width: 100%;
    object-fit: cover;
  }

  .content {
    margin-top: 1em;
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

  .body {
    font-size: 0.8em;
    line-height: 1.4em;
    font-weight: 300;
    padding: 0 0.5em;
  }

  .button {
    display: inline-block;
    font-size: 0.625em; // 10/16
    font-weight: 600;
    padding: 1em 1.5em;
    transition: all 0.3s ease-in-out;
    margin-top: 1.875em;
  }
}

@media (max-width: 768px) {
  .blog-item {
    width: 50%;
  }
}

@media (max-width: 380px) {
  .blog-item {
    width: 100%;
  }
}
</style>
