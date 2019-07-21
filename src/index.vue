<template>
  <div class="component">
    <span class="marker" v-if="[1, 2].indexOf(type) < 0">
      <span :class="classObject" class="icon" :style="{backgroundColor: iconColor}"></span>
    </span>
    <span class="content" :class="{sty1: type == 1}">{{name}}</span>
    <span class="marker marker_r" v-if="type >= 6">
      <span :class="classObject" class="icon" :style="{backgroundColor: iconColor}"></span>
    </span>
  </div>
</template>

<script>
  import {VueExtend} from 'godspen-lib'

  export default {
    mixins: [VueExtend.mixin],
    name: 'title',
    label: process.env.LABEL,
    style: process.env.STYLE,
    props: {
      name: {
        type: String,
        default: '标题',
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
      iconColor: {
        type: String,
        default: '#6260e1',
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
      type: {
        type: Number,
        default: 1,
        editer: {
          ignore: true // 忽略，码良基础在编辑器中不显示
        }
      },
    },
    computed: {
      classObject () {
        return {
          icon_3: this.type == 3,
          icon_4: this.type == 4,
          icon_5: this.type == 5,
          icon_6: this.type == 6,
          icon_7: this.type == 7,
          icon_8: this.type == 8,
        }
      }
    },
    editorMethods: {
    },
    methods: {
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" type="text/stylus" scoped>
.component{
  display flex
  padding 8px 16px
  .marker {
    display: flex;
    box-align: center;
    align-items: center;
  }
  .content {
    margin 0 8px
  }
  .icon {
    background-color: #6260e1;
  }
  .icon_3{
    width: 4px;
    height: 16px;
    border-radius: 2rem 0 0 2rem;
  }
  .icon_4{
    width: 8px;
    height: 8px;
    background-color: #fff;
    border: 2px solid #6260e1;
    border-radius: 50%;
    box-sizing: border-box;
  }
  .icon_5{
    width: 6px;
    height: 6px;
    border-radius: 50%;
  }
  .icon_6 {
    width 16px
    height 2px
    border-radius 1.5px
  }
  .icon_7 {
    width 6px
    height 6px
    transform: rotate(45deg);
  }
  .icon_8 {
    width 2px
    height 14px
    transform: rotate(30deg);
  }
  .sty1 {
    display inline-block
    width 100%
    text-align center
  }
}
</style>
