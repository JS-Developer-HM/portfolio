<template>
  <section id="portfolio">
    <h1 class="portfolio text-center">Portfolio </h1>
    <div class="container">
      <div class="row">
        <div
          v-for="(item, i) in reactive.data"
          :key="i"
          class="col-lg-4 col-md-6 col-sm-12"
        >
          <a :href="item.url" class="site" target="_blank">
            <img :src="item.img" :alt="item.name" />
            <span>
              <span class="btn">{{ item.name }}</span>
            </span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  inject: ["reactive"],
  watch: {
    reactive(n) {
      console.log(n);
    },
  },
  mounted() {
    setTimeout(() => {
      console.log(this.reactive.data);
    }, 5000);
  },
};
</script>
