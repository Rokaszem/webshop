<template>
  <div>
    <div class="details">
      <div class="image-container">
        <img :src="item.image" />
      </div>
      <p class="title">{{ item.title }}</p>
      <p class="description">{{ item.description }}</p>
      <p>{{ item.price }}$</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Item",
  props: ["item"],
  methods: {
    addCart() {},
  },
};
</script>

<style>
.item {
  width: 25%;
  display: flex;
  align-content: center;
  flex-direction: column;
  flex-wrap: wrap;
}
.details {
  height: 50vh;
  display: inline-block;
}
.image-container {
  height: 50%;
  width: 100%;
}
.image-container > img {
  max-width: 100%;
  max-height: 100%;
  object-fit: cover;
}
p {
  max-width: 200px;
}
.description {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}
@media (max-width: 1050px) {
  .item {
    width: 50%;
  }
}
@media (max-width: 660px) {
  .item {
    width: 100%;
  }
}
</style>