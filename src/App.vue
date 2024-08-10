<script setup></script>

<style>
* {
  font-family: Arial, Helvetica, sans-serif;
}
</style>

<template>
  <link
    href="https://fonts.googleapis.com/icon?family=Material+Icons"
    rel="stylesheet"
  />

  <mdui-layout style="height: 100%">
    <mdui-top-app-bar>
      <mdui-button-icon id="openButton" icon="menu"></mdui-button-icon>
      <mdui-top-app-bar-title>Study Area CN</mdui-top-app-bar-title>
      <div style="flex-grow: 1"></div>
    </mdui-top-app-bar>

    <mdui-navigation-drawer close-on-overlay-click class="navi-drawer">
      <mdui-list>
        <mdui-list-item
          end-icon="arrow_right"
          href="https://learn.study-area.org.cn"
          >开始学习</mdui-list-item
        >
        <mdui-list-item
          end-icon="arrow_right"
          href="https://forum.study-area.org.cn"
          >讨论区</mdui-list-item
        >
        <mdui-list-item
          end-icon="arrow_right"
          href="https://git.hmtsai.cn/study-area-cn/study-area-cn-homepage/"
          >查看本站源码</mdui-list-item
        >
      </mdui-list>
    </mdui-navigation-drawer>

    <component :is="'script'">
      const navigationDrawer = document.querySelector(".navi-drawer"); const
      openButton = document.getElementById("openButton");
      openButton.addEventListener("click", () => navigationDrawer.open =
      !navigationDrawer.open);
    </component>

    <mdui-layout-main>
      <mdui-card href="https://forum.study-area.org.cn/" clickable class="card">
        <h1>Study Area CN 讨论区</h1>
      </mdui-card>

      <mdui-card href="https://learn.study-area.org.cn/" clickable class="card">
        <h1>开始学习</h1>
      </mdui-card>

      <mdui-card
        href="https://git.hmtsai.cn/study-area-cn/study-area-cn-homepage/"
        clickable
        class="card"
      >
        <h1>查看本站源码</h1>
      </mdui-card>

      <mdui-card
        href="https://git.hmtsai.cn/study-area-cn/"
        clickable
        class="card"
      >
        <h1>本站Gitea</h1>
      </mdui-card>
    </mdui-layout-main>
  </mdui-layout>
</template>

<style>
h1 {
  padding-left: 15px;
}

mdui-layout-main {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

mdui-card {
  margin: 3px;
  width: calc(25% - 6px);
  height: 25%;
}

@media screen and (max-width: 640px) {
  mdui-card {
    width: calc(100% - 6px);
  }

  mdui-layout-main{
    flex-direction: column;
    flex-wrap: nowrap;
  }
}
</style>
