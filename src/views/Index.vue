<template>
  <div class="wrapper">
    <parallax class="page-header header-filter" :style="headerStyle">
      <div class="md-layout">
        <div class="md-layout-item">
          <div class="image-wrapper">
            <img :src="leaf4" alt="leaf4" class="leaf4" v-show="leafShow" />
            <img :src="leaf3" alt="leaf3" class="leaf3" v-show="leafShow" />
            <img :src="leaf2" alt="leaf2" class="leaf2" v-show="leafShow" />
            <img :src="leaf1" alt="leaf1" class="leaf1" v-show="leafShow" />
            <div class="brand">
              <h1>北邮自然语言处理研究小组</h1>
              <h3>热爱分享，是我们一贯坚持的作风</h3>
            </div>
          </div>
        </div>
      </div>
    </parallax>

    <div class="main main-raised" style="background: transparent; width: 60%; margin-left:20%; box-shadow: 0 0 0;">
      <el-row>
        <el-col :span="8" class="col-padding">
          <el-card style="">
            <div class="bg2">
              <img
              src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png"
              class="image"
              />
            </div>
            <div style="padding: 14px;">
              <span>情感分析</span>
              <div>
                用自然语言处理、文本挖掘以及计算机语言学等方法来识别和提取原素材中的主观信息
              </div>
            </div>
          </el-card>
        </el-col>
        <el-col :span="8" class="col-padding">
           <el-card>
            <div class="bg3">
              <img
                src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png"
                class="image"
              />
            </div>
            <div style="padding: 14px;">
              <div style="">知识图谱</div>
              <div class="bottom clearfix">
                用可视化技术描述知识资源及其载体，挖掘、分析、构建和显示知识及它们之间的相互联系。
              </div>
            </div>
          </el-card>
        </el-col>
        <el-col :span="8"  class="col-padding">
           <el-card>
             <div class="bg1">
                <img
                  src="https://images.ctfassets.net/wf5t1ptx352c/3Mxumaa3Au0tGjN7MGDoRq/20c7536e6f574290f3a50cf65da1911f/latest_scifact.svg"
                  class="image"
                />
             </div>
            <div style="padding: 14px;">
              <span>Chatbot</span>
              <div class="bottom clearfix">
                经由对话或文字进行交谈的计算机程序。能够模拟人类对话，通过图灵测试。
              </div>
            </div>
          </el-card>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import BasicElements from "./components/BasicElementsSection";
import Navigation from "./components/NavigationSection";

export default {
  components: {},
  name: "index",
  bodyClass: "index-page",
  props: {
    image: {
      type: String,
      default: require("@/assets/img/vue-mk-header.jpg")
    },
    leaf4: {
      type: String,
      default: require("@/assets/img/leaf4.png")
    },
    leaf3: {
      type: String,
      default: require("@/assets/img/leaf3.png")
    },
    leaf2: {
      type: String,
      default: require("@/assets/img/leaf2.png")
    },
    leaf1: {
      type: String,
      default: require("@/assets/img/leaf1.png")
    },
    signup: {
      type: String,
      default: require("@/assets/img/city.jpg")
    },
    landing: {
      type: String,
      default: require("@/assets/img/landing.jpg")
    },
    profile: {
      type: String,
      default: require("@/assets/img/profile.jpg")
    }
  },
  data() {
    return {
      firstname: null,
      email: null,
      password: null,
      leafShow: false
    };
  },
  methods: {
    leafActive() {
      if (window.innerWidth < 768) {
        this.leafShow = false;
      } else {
        this.leafShow = true;
      }
    }
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.image})`
      };
    },
    signupImage() {
      return {
        backgroundImage: `url(${this.signup})`
      };
    }
  },
  mounted() {
    this.leafActive();
    window.addEventListener("resize", this.leafActive);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.leafActive);
  }
};
</script>
<style lang="scss">
.section-download {
  .md-button + .md-button {
    margin-left: 5px;
  }
}
.image{
  width: 100%;
}
.col-padding{
  padding: 40px
}
.bg1{
  background: linear-gradient(154.92deg, rgb(53, 104, 211) 18.22%, rgb(41, 81, 165) 90.66%);
}
.bg2{
  background: linear-gradient(155.42deg, rgb(100, 86, 181) 17.77%, rgb(71, 60, 136) 95.72%);
}
.bg3{
  background: linear-gradient(154.61deg, rgb(0, 172, 215) 18.38%, rgb(0, 141, 177) 96.34%);
}


@media all and (min-width: 991px) {
  .btn-container {
    display: flex;
  }
}
</style>
