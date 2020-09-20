<template>
  <div class="home">
    <div class="flex flex-col h-screen items-center justify-center">
      <button type="button" class="btn btn-outline-danger mb-2" >{{count}}</button>
      <div class="mb-2">
        <button type="button" class="btn btn-warning" @click="min">-</button>
        <button type="button" class="btn btn-primary" @click="add">+</button>
      </div>
    <button v-show="!isFresh" type="button" class="btn btn-secondary btn-sm " @click="zero">
      清除</button>
  </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue';

export default {
  name: 'Home',
  data() {
    return { // 變數
      name: 'Jonathan',
      count: 0,
      isFresh: true,
    };
  },
  methods: { // function
    add() {
      if (this.count >= 0) {
        this.count += 1;
        this.isFresh = false;
      }
    // test
    },
    min() {
      if (this.count <= 0) {
        this.count = 0;
      } else {
        this.count -= 1;
        this.isFresh = false;
      }
    },
    zero() {
      this.count = 0;
      this.isFresh = true;
    },
  },
};
</script>
