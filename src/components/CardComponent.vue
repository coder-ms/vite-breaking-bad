<template>
  <div class="cardChar">
    <div class="box">
      <div class="imageChar">
        <img :src="character.img" :alt="character.name">
      </div>
      <div class="info">
        <h6>{{ character.name }}</h6>
        <p class="font-weight-bold">{{ character.category }}</p>
        <p>{{ character.status }}</p>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    character: Object
  }
}
/*
import { store } from '../store';
import CardComponent from './CardComponent.vue';
export default {
  name: "CharacterList",
  components: { CardComponent },
  data() {
    return {
      store
    }
  }
}
*/
</script>

<style lang="scss" scoped>
.cardChar {
  .box {
    width: 100%;

    .imageChar {
      margin-bottom: 10px;

      img {
        width: 100%;
      }

      .info {
        padding: 5px;
        margin-top: 10px;

        h6 {
          text-transform: capitalize;
          font-weight: 700;
        }

        p {
          font-size: 14px;
          color: rgb(221, 220, 220);
        }
      }
    }
  }
}
</style>
