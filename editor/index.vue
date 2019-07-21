<template>
  <div class="component-editor">
    <el-form size="mini" label-width="100px">
      <el-form-item label="选择种类">
        <div class="sty">
          <div class="imgSty" v-for="i in titleStyleMap" :key="i.type" @click="chooseType(i.type)">
            <img :src="i.img" alt="">
          </div>
        </div>
      </el-form-item>
      <el-form-item label="标题名称">
        <el-input type="input" v-model="componentInfo.name" placeholder="请输入标题名称"></el-input>
      </el-form-item>
      <el-form-item label="图标颜色">
        <el-color-picker v-model="componentInfo.iconColor" show-alpha></el-color-picker>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
  export default {
    name: 'maliangeditor',
    props: {
      componentInfo: { // 固定字段，收集所有属性值
        type: [Object],
        default () {
          return {
            type: 2
          }
        }
      }
    },
    data: function () {
      return {
        titleStyleMap: [
          {
            type: 1,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhbne4/cd089b7b-7d98-4711-ad8e-ba2d1e2173d6.cms/images/5fae81ca-32ce-458c-9d02-977af5397daf.png?x-oss-process=image/resize,w_560/crop,h_560'
          },{
            type: 2,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhbijy/3e1fe003-aa08-49bc-9199-0d706287ae92.cms/images/eea1430d-9f2e-4159-905f-226a94e1b11a.png?x-oss-process=image/resize,w_560/crop,h_560'
          },{
            type: 3,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhbdmc/8f372f08-91c2-4fc0-b274-7eae4cefd934.cms/images/780333bf-59bf-4687-9a4c-e9c88ac8b2c3.png?x-oss-process=image/resize,w_560/crop,h_560'
          },{
            type: 4,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhb8ft/19ec09fa-8297-4e06-93bd-c8b172f8a151.cms/images/3cae0c1f-1f03-4aa9-a81e-0d0df8fdf159.png?x-oss-process=image/resize,w_560/crop,h_560'
          },{
            type: 5,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhb3ie/abe1bd58-d1b4-4818-9f04-dc83de079cfc.cms/images/ceb2a9e2-c2a9-4fb4-a9ff-ba4b7f03d951.png?x-oss-process=image/resize,w_560/crop,h_560'
          },
          {
            type: 6,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhau5a/5d31b2b1-81f5-400b-953b-b971265a3ad6.cms/images/176c7628-4bb3-40d2-a353-400f7f4c4eca.png?x-oss-process=image/resize,w_560/crop,h_560'
          },
          {
            type: 7,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhake6/f6e957e2-fed7-48de-889a-1ae66aa8d5b6.cms/images/22f004b5-c9fa-44ce-a9f6-90cf6d3ff543.png?x-oss-process=image/resize,w_560/crop,h_560'
          },{
            type: 8,
            img: 'https://gw.alipayobjects.com/os/q/cms/images/jnlhafsy/594e4200-6ba9-49ba-b6ea-1e8ad54f6ffa.cms/images/92d7fe39-e883-4d3c-ac33-2f2962f30c38.png?x-oss-process=image/resize,w_560/crop,h_560'
          }
        ]
      }
    },
    computed: {
    },
    watch: {
      componentInfo: {
        hanlder: function (v) {
          console.log('editor index', v)
        },
      }
    },
    mounted: function () {
    },
    methods: {
      chooseType (type) {
        this.componentInfo.type = type
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" type="text/stylus" scoped>
  .component-editor {
    .sty{
      // border 1px solid #ddd
      height 250px
      overflow hidden
      overflow-y auto
      .imgSty {
        width 400px
        height 42px
        cursor pointer
        margin-bottom 10px
        img {
          height 40px
        }
      }
    }
  }
</style>
