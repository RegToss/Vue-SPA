<template>
  <div class="cartcontrol">
    <transition>
      <div class="cart-decrease" v-show="food.count>0" @click.stop.prevent="decreaseCart">
        <span class="inner inner1 icon-remove_circle_outline"></span>
      </div>
    </transition>
    <div class="cart-count" v-show="food.count>0">{{food.count}}</div>
    <div class="cart-add icon-add_circle" @click.stop.prevent="addCart"></div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Vue from 'vue';

  export default {
    props: {
      food: {
        type: Object
      }
    },
    methods: {
      //修改数据goods=>foods=>food的count，映射到原始数据中
      addCart(event) {
        if (!event._constructed) {
          return;
        }
        if (!this.food.count) { //如果没有count属性，则设置为1
          Vue.set(this.food, 'count', 1);
        } else {
          this.food.count++;
        }
        this.$bus.emit('add', event.target);
        this.$emit('event', event.target);
      },
      decreaseCart(event) {
        if (!event._constructed) {
          return;
        }
        if (this.food.count) {
          this.food.count--;
        }
      }
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "./cartcontrol.styl";
</style>
