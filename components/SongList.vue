<template>
  <div class="wrapper">
    <h1 style="font-weight: bold">⭐🎸🎉🎤⚡<br />Concert 50 ans Marion<br />⭐🎸🎉🎤⚡</h1>
    <div class="listpage">
      <ul class="list">
        <li
          v-for="(s, index) in songs"
          :key="index"
          :data-first-letter="s.name.charAt(0)"
        >
          <a
            class="song"
            :href="`https://stately-meringue-48b151.netlify.app/note/${s.id}?directory=marion`"
            rel="nofollow"
          >
            <span>{{ s.name }}</span>
            <span>{{ s.artist }}</span>
            <img
              class="lazy"
              :data-src="`https://aeovnsnhjq.cloudimg.io/v7/_funlive_/artists/${s.id}.jpg?width=80&height=80`"
              src="/blank.gif"
            />
          </a>
        </li>
      </ul>
    </div>
    <h2>Et / ou ?</h2>
    <div class="listpage">
      <ul class="list">
        <li
          v-for="(s, index) in songs2"
          :key="index"
          :data-first-letter="s.name.charAt(0)"
        >
          <a
            class="song"
            :href="`https://stately-meringue-48b151.netlify.app/note/${s.id}?directory=marion`"
            rel="nofollow"
          >
            <span>{{ s.name }}</span>
            <span>{{ s.artist }}</span>
            <img
              class="lazy"
              :data-src="`https://aeovnsnhjq.cloudimg.io/v7/_funlive_/artists/${s.id}.jpg?width=80&height=80`"
              src="/blank.gif"
            />
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import songsJson from '../data/json/index.json';
import songs2Json from '../data/json/index2.json';

export default {
  data() {
    return {
      songs: songsJson,
      songs2: songs2Json,
    };
  },
  mounted() {
    window.LazyLoadInstance.update();
  },
  methods: {},
};
</script>

<style lang="postcss" scoped>
body {
  padding: 0;
  margin: 0;
  font-family: sans-serif;
  font-weight: 400;
}
.random {
  padding: 10px 20px;
  margin: 0 0 40px 20px;
  font-size: 1em;
}
.songchoice {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 100%;
  background: var(--primaryColor);
  & > button {
    position: absolute;
    top: 0px;
    right: 0px;
    width: 40px;
    height: 40px;
    background: rgba(0, 0, 0, 0.5);
    border: none;
    @media screen and (--tablet) {
      display: none;
    }
    &::after,
    &::before {
      width: 15px;
      height: 2px;
      content: '';
      position: absolute;
      top: calc(50% - 2px);
      left: 50%;
      background: white;
    }
    &::after {
      transform: translateX(-50%) rotate(45deg);
    }
    &::before {
      transform: translateX(-50%) rotate(-45deg);
    }
  }
  & > .choices {
    flex: 1 1 100%;
    text-align: center;
    & > img {
      width: 80%;
    }
    & > button,
    & > a {
      width: calc(100% - 10px);
      text-align: center;
      padding: 15px 0;
      text-decoration: none;
      display: block;
      margin: 0 0 5px 5px;
      background: var(--secondaryColor);
      color: white;
      border-radius: 4px;
    }
  }
  & > .back {
    flex: 0 0 60px;
    @media screen and (--tablet) {
      display: none;
    }
    & > button {
      width: calc(100% - 10px);
      height: calc(100% - 10px);
      margin: 5px 0 0 5px;
      border: var(--secondaryColor) 1px solid;
      background: none;
      color: var(--secondaryColor);
      border-radius: 4px;
    }
  }
}
.listpage {
  position: relative;
  padding: 0 0 100px 0;
  @media screen and (--tablet) {
    display: flex;
    flex-direction: row-reverse;
    gap: 10px;
  }
}
ul.list {
  list-style-type: none;
  margin: 0;
  padding: 0;
  position: relative;
  width: 100%;
  li {
    background: rgba(255, 255, 255, 0.1);
    color: white;
    margin: 0 0 10px 0;
    .song {
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 0 10px 0 95px;
      text-decoration: none;
      color: white;
      position: relative;
      height: 80px;
      & > img {
        position: absolute;
        width: auto;
        height: 100%;
        top: 0;
        left: 0;
      }
      & > span {
        &:nth-child(1) {
          display: block;
          font-weight: bold;
          font-size: 1.1em;
          line-height: 1.1em;
          padding: 5px 0 5px;
        }
        &:nth-child(2) {
          opacity: 0.7;
        }
        &.nota {
          color: red;
        }
      }
    }
    .ad {
      display: block;
      border-radius: 5px;
      padding: 30px;
      text-decoration: none;
      color: white;
      position: relative;
      text-align: center;
      @media screen and (--desktop) {
        padding: 20px;
      }
      &MainText {
        font-family: 'Geomanist';
        text-transform: uppercase;
        color: white;
        font-size: 1.5em;
        line-height: 1.5em;
      }
      &Button {
        display: inline-block;
        padding: 4px 15px;
        margin: 10px 0 0 0;
        border-radius: 5px;
        border: 2px solid white;
        font-weight: bold;
      }
    }
  }
}
</style>
