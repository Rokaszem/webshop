<template>
  <div class="container">
    <div class="filter"><h3>Filtering</h3></div>
    <div class="list-products">
      <Item :item="item" class="item" v-for="item of items" :key="item.id" />
    </div>
    <div class="pages">
      <span class="page-btn" v-for="n in listL" :key="n">
        <router-link to="#">{{ n }}</router-link>
      </span>
    </div>
  </div>
</template>

<script>
import Item from "@/components/Item.vue";
export default {
  components: {
    Item,
  },
  data() {
    return {
      allItem: [],
      items: [],
      listL: 0,
    };
  },
  methods: {
    async getData() {
      try {
        let response = await fetch("https://fakestoreapi.com/products");
        this.allItem = await response.json();
        this.listL = (this.allItem.length/8).toFixed(0);
        let from, to;
        if (this.$route.query.cpage != null && this.$route.query.cpage > 1) {
          to = this.$route.query.cpage * 8;
          from = to - 8;
        } else {
          to = 8;
          from = 0;
        }
        this.items = this.allItem.slice(from, to);
        console.log(this.listL);
      } catch (error) {
        console.log(error);
      }
    },
  },
  created() {
    this.getData();
    console.log(this.$route.query);
  },
};
</script>

<style>
.container {
  width: 80%;
  margin: 50px auto;
  display: flex;
  flex-direction: column;
}
.list-products {
  display: flex;
  justify-content: space-evenly;
  flex-wrap: wrap;
}
.filter {
  background-color: cadetblue;
  padding: 10px 0 10px 30px;
  margin-bottom: 30px;
  border-radius: 5px;
}
</style>