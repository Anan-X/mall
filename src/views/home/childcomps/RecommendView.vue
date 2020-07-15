<template>
  <div class="recommend">
    <div class="recommmend-item" v-for="(item, index) in recommends" :key="index">
      <a :href="item.link">
        <img :src="item.image" alt="">
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    recommends: {
      type: Array,
      default () {
        return []
      }
    }
  }
}
</script>

<style>
  .recommend{
    display: flex;
    width: 100%;
    text-align: center;
    font-size: 12px;
    padding: 10px 0 20px ;
    border-bottom: 6px solid #eee;
  }
  .recommmend-item {
    flex: 1;
  }
  .recommmend-item img {
    width: 65px;
    height: 65px;
  }
</style>