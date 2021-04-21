<template>
  <section class="container">
    <div>
      <input 
        v-model="search"
        type="text"
        placeholder="Find the title..."
      >
      <ul class="list">
        <li 
          v-for="(post, index) in filteredList"
          :key="index"
          class="item"
        >
          <input
            :class="{ active: !post.active }"
            type="button"
            class="item-quote-icon"
            @click="toggleActive(post)"
          >
          <a
            :style="{'background-image': `url(${post.img})`}"
            :href="post.img"
            target="_blank"
            class="item-link"
          >
            <img 
              :src="post.img"
              :alt="post.title"
              width="600"
              height="800"
            >
          </a>
          <div
            :class="{ active: !post.active }"
            class="item-content"
          >
            <h2>{{ post.title }}</h2>
            <p>-</p>
            <q>{{ post.quote }}</q>
            <p>-</p>
            <h5>{{ post.author }}</h5>
          </div>
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      search: '',
      posts: [
        {
          "title": "Clear the air",
          "img": "clear-the-air.png",
          "quote": "Best way to clear the air is to have it all out in the open.",
          "author": "Harper Lee",
          "active": "false"
        },
        {
          "title": "Love your family",
          "img": "love-your-family.png",
          "quote": "You go through life wondering what is it all about but at the end of the day it's all about family.",
          "author": "Rod Stewart",
          "active": "false"
        },
        {
          "title": "Join the dance",
          "img": "join-the-dance.png",
          "quote": "The only way to make sense out of change is to plunge into it, move with it, and join the dance.",
          "author": "Alan Watts",
          "active": "false"
        },
        {
          "title": "Stress less",
          "img": "stress-less.png",
          "quote": "It is not a daily increase, but a daily decrease. Hack away at the inessentials.",
          "author": "Bruce Lee",
          "active": "false"
        },
        {
          "title": "Watch the sky",
          "img": "watch-the-sky.png",
          "quote": "I never get tired of the blue sky.",
          "author": "Vincent van Gogh",
          "active": "false"
        },
        {
          "title": "Enjoy life",
          "img": "enjoy-life.png",
          "quote": "I finally figured out the only reason to be alive is to enjoy it.",
          "author": "Rita Mae Brown",
          "active": "false"
        },
        {
          "title": "Listen to your heart",
          "img": "listen-to-your-heart.png",
          "quote": "Your heart knows the way. Run in that direction.",
          "author": "Rumi",
          "active": "false"
        },
        {
          "title": "Take your time",
          "img": "take-your-time.png",
          "quote": "Nature does not hurry, yet everything is accomplished.",
          "author": "Laozi",
          "active": "false"
        },
        {
          "title": "Go with the flow",
          "img": "go-with-the-flow.png",
          "quote": "Those who flow as life flows know they need no other force.",
          "author": "Laozi",
          "active": "false"
        },
        {
          "title": "Take it easy",
          "img": "take-it-easy.png",
          "quote": "Take it easy driving - the life you save may be mine.",
          "author": "James Dean",
          "active": "false"
        },
        {
          "title": "Thank you",
          "img": "thank-you.png",
          "quote": "Thank you for brightening my world.",
          "author": "Someone close to you",
          "active": "false"
        },
        {
          "title": "Live the dream",
          "img": "live-the-dream.png",
          "quote": "For my part I know nothing with any certainty, but the sight of the stars makes me dream.",
          "author": "Vincent van Gogh",
          "active": "false"
        },
        {
          "title": "Breathe in and out",
          "img": "breathe-in-and-out.png",
          "quote": "When people ask me what the most important thing is in life, I answer: Just breathe.",
          "author": "Yoko Ono",
          "active": "false"
        },
        {
          "title": "Do what youlove",
          "img": "do-what-youlove.png",
          "quote": "This is the real secret of life — to be completely engaged with what you are doing in the here and now. And instead of calling it work, realize it is play.",
          "author": "Alan Watts",
          "active": "false"
        },
        {
          "title": "Let it be",
          "img": "let-it-be.png",
          "quote": "Let it be, let it be, Let it be, let it be, whisper words of wisdom, let it be.",
          "author": "The Beatles",
          "active": "false"
        },
        {
          "title": "Don't worry",
          "img": "dont-worry.png",
          "quote": "Cause when you worry your face will frown and that will bring everybody down. So don't worry, be happy. Don't worry, be happy now",
          "author": "Bobby McFerrin",
          "active": "false"
        },
        {
          "title": "Love blue",
          "img": "love-blue.png",
          "quote": "The sun is up, the sky is blue It's beautiful, and so are you",
          "author": "John Lennon, Beatles Lyrics",
          "active": "false"
        },
        {
          "title": "Create your own quotes",
          "img": "create-your-own-quotes.png",
          "quote": "You can speak well if your tongue can deliver the message of your heart.",
          "author": "John Ford",
          "active": "false"
        },
        {
          "title": "You will find it",
          "img": "you-will-find-it.png",
          "quote": "Happiness is where we find it, but rarely where we seek it.",
          "author": "Jean Antoine Petit-Senn",
          "active": "false"
        },
        {
          "title": "Bake a cake",
          "img": "bake-a-cake.png",
          "quote": "Food is a universal language that brings people together.",
          "author": "A piece of cake",
          "active": "false"
        },
      ]
    }
  },
  computed: {
    filteredList() {
      return this.posts.filter(post => {
        return post.title.toLowerCase().includes(this.search.toLowerCase())
      })
    }
  },
  methods: {
    toggleActive: function(post) {
      post.active = !post.active
    }
  }
}
</script>

<style>
.list {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  padding: 0;
  margin: 0;
}

.item {
  width: 100%;
  flex-basis: 100%;
  position: relative;
  overflow: hidden;
}

@media screen and (min-width: 480px) {
  .item {
    width: 50%;
    flex-basis: 50%;
  }
}

@media screen and (min-width: 768px) {
  .item {
    width: 33.333333%;
    flex-basis: 33.333333%;
  }
}
@media screen and (min-width: 1280px) {
  .item {
    width: 25%;
    flex-basis: 25%;
  }
}
@media screen and (min-width: 1600px) {
  .item {
    width: 20%;
    flex-basis: 20%;
  }
}

.item-quote-icon {
  border: 0;
  background-color: transparent;
  background-image: url(../assets/quote.svg);
  background-size: 35px;
  background-position: center;
  background-repeat: no-repeat;
  outline: none;
  z-index: 2;
  position: absolute;
  top: 0.25rem;
  left: 0.25rem;
  width: 50px;
  height: 50px;
  cursor: pointer;
  transition: background 0.25s ease-in-out;
}

.item-quote-icon.active {
  background-image: url(../assets/quote-alt.svg);
}

.item-link {
  display: block;
  background-position: 50% 50%;
  background-repeat: no-repeat;
  background-size: cover;
}

.item-link img {
  vertical-align: bottom;
  width: 100%;
  height: auto;
}

.item-content {
  z-index: 1;
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  padding: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.95);
  transform: translateY(100%);
  transition: transform 0.25s ease-in-out;
}

.item-content.active {
  transform: translateY(0);
}

.item-content q {
  text-align: center;
  font-size: 1.25rem;
}

.item-content h5 {
  font-size: 1rem;
}
</style>
