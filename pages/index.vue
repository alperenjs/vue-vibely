<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">vue-vibely</h1>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--green"
        >
          Documentation
        </a>
        <nuxt-link class="button--grey" to="/second" >
          Hello!
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "default",
  components: {},
    head() {
    return {
      link: [
        {
          // rel: "stylesheet",
          // type: "text/css",
          // href: "/content/css/bootstrap.min.css",
        },
      ],
      script: [],
      title: "Vue Vibely",
      meta: [
        {
          hid: "tags",
          name: "tags",
          content: "vue, vibely",
        },
      ],
      bodyAttrs: {},
    };
  },
   data() {
    return {

    }
    },
    methods:{

    }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
