<script lang="ts" setup>
import SubProjectCard from "./components/SubProjectCard.vue";

const sub_projects = [
  {
    desc: "知识从不是少数人的专利，让知识自由的在世界上流淌，为每个人创造价值。",
    name: "Learning",
    href: "https://learn.study-area.org.cn/",
  },
  {
    desc: "让知识与感想突破地域的界限，即时在网络上流通。",
    name: "Discussing",
    href: "https://forum.study-area.org.cn/",
  },
  {
    desc: "用爱发电，很难长久。为我们的项目贡献一份力量，我们才能走得更远。",
    name: "Contributing",
    href: "https://git.hmtsai.cn/",
  },
];
</script>

<style>
* {
  font-family: Arial, Helvetica, sans-serif;
}
</style>

<template>
  <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet" />

  <mdui-layout style="height: 100%">
    <mdui-top-app-bar>
      <mdui-button-icon id="openButton" icon="menu"></mdui-button-icon>
      <mdui-top-app-bar-title>Study Area CN</mdui-top-app-bar-title>
      <div style="flex-grow: 1"></div>
    </mdui-top-app-bar>

    <mdui-navigation-drawer close-on-overlay-click class="navi-drawer">
      <mdui-list>
        <mdui-list-item end-icon="arrow_right" href="https://learn.study-area.org.cn">开始学习</mdui-list-item>
        <mdui-list-item end-icon="arrow_right" href="https://forum.study-area.org.cn">讨论区</mdui-list-item>
        <mdui-list-item end-icon="arrow_right"
          href="https://git.hmtsai.cn/study-area-cn/study-area-cn-homepage/">查看本站源码</mdui-list-item>
      </mdui-list>
    </mdui-navigation-drawer>

    <component :is="'script'">
      const navigationDrawer = document.querySelector(".navi-drawer"); const
      openButton = document.getElementById("openButton");
      openButton.addEventListener("click", () => navigationDrawer.open =
      !navigationDrawer.open);
    </component>

    <mdui-layout-main>
      <div class="header">
        <div class="header-mover">
          <h1>Study Area CN</h1>
          <p class="desc">在这里，您将看不见八卦，看不见争吵，没有新闻，也没娱乐。</p>
          <p class="desc">本站仅能为阁下提供的就是您要学习的技术文件与心得经验的交流。本站的角色是一个网上的学习园地（Study Area）。</p>
        </div>
      </div>

      <div>
        <SubProjectCard v-for="item in sub_projects" :name="item.name" :desc="item.desc" :href="item.href">
        </SubProjectCard>
      </div>

      <div class="footer">
        <h3>Study Area CN Team  2024 - Forever</h3>
      </div>
    </mdui-layout-main>
  </mdui-layout>
</template>

<style scoped>
*{
    font-family: "Source Han Serif CN VF";
}
</style>
