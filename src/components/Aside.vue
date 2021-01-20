<template>
  <aside class="aside">
    <div class="extra">
      <div class="img"><img :src="getImgUrl(items.extra)" width="200px" /></div>
      <div class="extraInfo">
        <h4>Дополнительные преимущества</h4>
        <p>—Lorem ipsum dolor sit amet, consectetur adipiscing</p>
        <p>—Guis nostrud exercitation ullamco laboris nisi ut aliquip</p>
        <p>—Voluptate velit esse cillum dolore eu fugiat nulla pariatur</p>
        <p>
          —Laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
          dolor
        </p>
      </div>
    </div>

    <div class="feedback">
      <div class="img">
        <img :src="getImgUrl(items.feedback)" width="200px" />
      </div>
      <div class="feedbackInfo">
        <h4>Отзывы</h4>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi ut
          aliquip ex ea commodo consequat. Duis aute irure dolor in
          reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
          pariatur.
        </p>
      </div>
    </div>
  </aside>
</template>

<script>
export default {
  name: "Aside",

  data() {
    return {
      items: {
        extra: "fifth.jpg",
        feedback: "sixth.jpg",
      },
    };
  },
  methods: {
    getImgUrl(pic) {
      return require(`../assets/${pic}`);
    },
  },
};
</script>

<style>
.aside {
  display: flex;
  justify-content: space-between;
  padding: 1em;
}
.extra,
.feedback {
  display: flex;
  flex: 0 0 50%;
  text-align: left;
}
.img {
  margin: 2%;
}
.extraInfo > p {
  margin: 0;
}

@media only screen and (max-width: 1200px) {
  .aside {
    flex-direction: column;
  }
}
</style>
