<template>
  <section>
    <div class="box">
      <div class="imageChar">
        <img :src="character.img" :alt="character.name">
      </div>
      <div class="info">
        <h5>{{ character.name }}</h5>
        <p class="font-weight-bold">{{ character.category }}</p>
        <p>{{ character.status }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    character: Object
  }
}
</script>

<style lang="scss" scoped>
.box {
  width: 100%;
  border: 1px solid red;

  .imageChar {
    padding: 10px;
    border: 1px solid blue;

    img {
      width: 100%;
    }

    .info {
      padding: 2px;

      border: 1px solid grey;

      h5 {
        text-transform: capitalize;
      }
    }
  }
}
</style>
