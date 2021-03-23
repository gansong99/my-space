<template>
  <div class="contact-container">
    <ul>
      <li>
        <a href="">
          <div class="icon">
            <Icon :type="type" />
          </div>
          <span>{{typeName}}</span>
        </a>
        <div
          class="pop"
          v-if="srcImg"
        >
          <img
            :src="require('../../assets/'+srcImg)"
            alt=""
          >
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
import Icon from "@/components/Icon"
export default {
  components: {
    Icon
  },
  props: {
    type: {//展示项目
      type: String,
      // require: true,
    },
    typeName: {//展示项目的名字
      type: String,
      // require: true,
    },
    srcImg: {//展示项目的的二维码
      type: String,
    }
  },
  computed: {
  }
}
</script>

<style scoped lang="less">
@import '~@/styles/var.less';
.contact-container {
  padding: 3px 0 0;
  margin: 0;
  color: @gray;
  @itemHeight: 30px;
  ul {
    list-style: none;
    li {
      height: 30px;
      line-height: 30px;
      margin: 14px 0;
      position: relative;
      &:hover {
        .pop {
          transform: scaleY(1);
        }
      }
      a {
        display: flex;
        color: @gray;
        text-decoration: none;
        align-items: center;
        cursor: pointer;
        .icon {
          // font-size: 26px;
          width: 36px;
        }
      }
      .pop {
        position: absolute;
        left: 0;
        bottom: @itemHeight;
        margin: 0 0 5px 0;
        border-radius: 5px;
        padding: 10px 15px;
        background: #fff;
        transform: scaleY(0);
        transform-origin: center bottom;
        transition: 0.5s;
        img {
          width: 150px;
          height: 150px;
        }
        &::after {
          content: '';
          width: 10px;
          height: 10px;
          bottom: -5px;
          position: absolute;
          left: 50%;
          background: #fff;
          transform: translateX(-50%) rotate(45deg);
        }
      }
    }
  }
}
</style>