<!--
 * @Descripttion: 
 * @version: 
 * @Author: JohnsonZzp
 * @Date: 2020-06-12 15:25:07
 * @LastEditors: JohnsonZzp
 * @LastEditTime: 2020-06-12 17:05:02
--> 
<!--  -->
<template>
  <div id="wrapper">
    <transition-group name="list" tag="ul" mode="out-in">
      <li v-for="(item,index) in piclist" :key="item.url" :style="config[index]">
        <img :src="item.url">
      </li>
    </transition-group>
    <a href="javascript:;" id="arrLeft" class="prev" @click="turnleft"></a>
    <a href="javascript:;" id="arrRight" class="next" @click="turnright"></a>
  </div>
</template>

<script>
export default {
  data() {
    return {
      piclist: [
        { url: 'http://dummyimage.com/1745x492/e3c933' },
        { url:'http://dummyimage.com/1745x492/e3c933'  },
        { url: 'http://dummyimage.com/1745x492/e3c933'  },
        { url: 'http://dummyimage.com/1745x492/e3c933'  },
  //      { url: 'http://dummyimage.com/1745x492/e3c933'  },
      ],
      //文件图片配置
      config: [
        {
          position: "absolute",
          width: "400px",
          top: "20px",
          left: "50px",
          opacity: 0.2,
          zIndex: 2,
          transition: "1s"
        },
        {
          position: "absolute",
          width: "800px",
          top: "100px",
          left: "200px",
          opacity: 1,
          zIndex: 4,
          transition: "1s"
        },
        {
          position: "absolute",
          width: "400px",
          top: "20px",
          left: "750px",
          opacity: 0.2,
          zIndex: 2,
          transition: "1s"
        }
      ],
      previous: 0,
      now: Date.now()
    };
  },
  methods: {
  //实现点击按钮切换的动画，设置时间参数防止多次点击
    turnleft: function() {
      this.now = Date.now();
      if (this.now - this.previous > 1000) {
        this.config.push(this.config.shift());
        this.previous = this.now;
      }
    },
    turnright: function() {
      this.now = Date.now();
      if (this.now - this.previous > 1000) {
        this.config.unshift(this.config.pop());
        this.previous = this.now;
      }
    }
  }
};


</script>
<style scoped lang="scss">
 * {
  margin: 0;
  padding: 0;
}
#wrapper {
  margin: auto;
  height: 500px;
  width: 79%;
  position: relative;
}
ul {
  list-style: none;
}
li img {
  height: 500px;
  width: 100%;
}
.prev,
.next {
  position: absolute;
  height: 60px;
  width: 60px;
  border-radius: 50%;
  top: 50%;
  margin-top: -56px;
  overflow: hidden;
  text-decoration: none;
  background-color: aqua;
  z-index: 5;
  opacity: 1;
}
.prev {
  left: 0;
}
.next {
  right: 0;
}
.picleft {
  width: 400;
  top: 20;
  left: 50;
  opacity: 0.2;
  z-index: 2;
}
.piccenter {
  width: 800;
  top: 100;
  left: 200;
  opacity: 1;
  z-index: 4;
}
.picright {
  width: 400;
  top: 20;
  left: 750;
  opacity: 0.2;
  z-index: 2;
}

</style>