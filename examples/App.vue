<template>
  <div class="app padding-medium">
    <a :href="link" class="ribbon">Fork me on Github</a>
    <p class="text-secondary">vtitle version: v{{ version }}</p>
    <el-divider></el-divider>
    <el-row class="text-left" type="flex">
      <el-col class="text-left" :span="24">
        <div class="flex-center-align">
          <label>Dark effect:</label>
          <p class="margin-left-large" v-title="title">
            touch me!
          </p>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Light effect:</label>
          <p class="margin-left-large" v-title.light="title">
            touch me!
          </p>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Show delay(200ms):</label>
          <p class="margin-left-large" v-title.delay="title">
            touch me and hold some time!
          </p>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Show delay(custom 1000ms):</label>
          <p
            class="margin-left-large"
            v-title.delay="title"
            title-delay-time="1000"
          >
            touch me and hold some time!
          </p>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Max width(100):</label>
          <p class="margin-left-large" v-title="title" title-max-width="100">
            touch me!
          </p>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Custom className:</label>
          <p
            class="margin-left-large"
            v-title="title"
            title-class-name="test-class"
          >
            touch me!
          </p>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Light effect:</label>
          <p class="margin-left-large" v-title.light="title">
            touch me!
          </p>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Overflow mode:</label>
          <p
            :class="{ 'text-ellipsis': overflowMode }"
            :style="{ width: overflowMode ? '90px' : 'auto' }"
            class="margin-left-large"
            v-title.overflow="title"
          >
            touch me! try toggle switch and touch me again!
          </p>
          <el-switch
            class="margin-left-large"
            v-model="overflowMode"
          ></el-switch>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Overflow and multiple mode:</label>
          <p
            :class="{ 'text-ellipsis-2': overflowAndMultipleMode }"
            :style="{ width: overflowAndMultipleMode ? '90px' : 'auto' }"
            class="margin-left-large"
            v-title.overflow.multiple="title"
          >
            touch me! try toggle switch and touch me again!
          </p>
          <el-switch
            class="margin-left-large"
            v-model="overflowAndMultipleMode"
          ></el-switch>
        </div>
        <el-divider></el-divider>
        <div class="flex-center-align">
          <label>Placement:</label>
          <p class="margin-left-large" v-title="title" title-placement="bottom">
            top(-start, -end), right(-start, -end), bottom(-start, -end),
            left(-start, -end)，default: top
          </p>
        </div>
        <el-divider></el-divider>
      </el-col>
    </el-row>
    <el-row>
      <el-col :span="24" class="code">
        <Highlight :code="code" lang="xml" />
      </el-col>
    </el-row>
  </div>
</template>

<script>
import VTitle from '../src';
import '../src/element-ui';

const version = require('../package').version;

export default {
  directives: {
    title: VTitle
  },
  data() {
    return {
      overflowMode: true,
      overflowAndMultipleMode: true,
      title: 'ABCDEFGABCDEFGABCDEFGABCDEFGABCDEFGABCDEFG',
      version,
      link: 'https://github.com/ilgei/vtitle',
      code: require('./template/example1').default
    };
  }
};
</script>

<style lang="scss">
.test-class {
  font-size: 20px;
}
</style>

<style lang="scss" scoped>
@import './styles/common-variables';
.app {
  .ribbon {
    top: 3.2em;
    right: -3.7em;
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    transform: rotate(45deg);
    color: #fff;
    display: block;
    padding: 0.6em 3.5em;
    position: fixed;
    text-align: center;
    text-decoration: none;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    background-color: green;
    z-index: 10000;
  }
  .el-col {
    padding: $spacing-medium;
    border-right: $border-base;
    &:last-of-type {
      border-right: 0;
    }
  }
  .code {
    overflow: hidden;
  }

  p {
    line-height: 1.3;
  }
  p.text-ellipsis-2 {
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 2; //这里是在第二行有省略号
    overflow: hidden;
  }
}
</style>
