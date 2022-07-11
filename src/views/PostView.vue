<template>
  <article class="post">
    <header>
      <h1>As a Designer, I Refuse to Call People 'Users'</h1>
    </header>
    <div class="container">
      <main class="body">
        <img src="https://picsum.photos/720/360?random=1" alt="image" />

        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. A, beatae
          consequuntur corporis dignissimos est fugiat iure, magni, molestiae
          odit omnis quas quia quibusdam quidem quos reiciendis saepe totam
          veritatis voluptatum?
        </p>

        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cupiditate
          doloremque exercitationem explicabo fugit ipsa libero modi repellat
          reprehenderit sed voluptas! Accusantium commodi consequatur culpa
          facere illum inventore nobis recusandae voluptatibus.
        </p>

        <blockquote>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Beatae
          deserunt doloribus earum et illo incidunt inventore molestias, numquam
          odit possimus quaerat quas qui quis reiciendis reprehenderit
          repudiandae rerum sapiente! Quidem!
        </blockquote>

        <img src="https://picsum.photos/720/360?random=2" alt="image" />

        <p>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores
          assumenda at beatae culpa doloremque maxime porro provident sint.
          Assumenda est facilis id ipsum, mollitia nihil odit quidem quod
          reprehenderit suscipit?
        </p>
      </main>
    </div>
  </article>
</template>

<style scoped lang="scss">
$post-header-bg: #fdefe6;
$text-color: #020500;
$blockquote-bg: #fdefe6;

.post {
  display: flex;
  flex-direction: column;

  .container {
    max-width: 720px;
    margin: 0 auto;
  }

  header {
    background-color: $post-header-bg;
    text-align: center;
    margin-bottom: 3em;

    h1 {
      font-weight: 600;
      font-size: 1.3333333333em; // 30/24
      margin: 3.3333333333em 0; // 80/24
    }
  }

  .body {
    img {
      margin: 1em 0;
    }

    p {
      margin-bottom: 1em;
    }

    blockquote {
      font-weight: 600;
      font-style: italic;
      line-height: 1.4em;
      padding: 1em;
      background-color: $blockquote-bg;
    }
  }
}

@media (max-width: 768px) {
  .post {
    font-size: 14px;
    .body {
      margin: 0 2em;
    }
  }
}
</style>
