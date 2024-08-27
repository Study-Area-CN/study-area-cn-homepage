<script setup></script>

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
        <h1>Study Area CN</h1>
        <p class="desc">在这里，您将看不见八卦，看不见争吵，没有新闻，也没娱乐。</p>
        <p class="desc">本站仅能为阁下提供的就是您要学习的技术文件与心得经验的交流。本站的角色是一个网上的学习园地（Study Area）。</p>
      </div>

      <div class="links">
        <mdui-card href="https://forum.study-area.org.cn/" clickable class="card">
          <h1>Study Area CN 讨论区</h1>
        </mdui-card>

        <mdui-card href="https://learn.study-area.org.cn/" clickable class="card">
          <h1>开始学习</h1>
        </mdui-card>

        <mdui-card href="https://git.hmtsai.cn/study-area-cn/study-area-cn-homepage/" clickable class="card">
          <h1>查看本站源码</h1>
        </mdui-card>

        <mdui-card href="https://git.hmtsai.cn/study-area-cn/" clickable class="card">
          <h1>本站Gitea</h1>
        </mdui-card>
      </div>
    </mdui-layout-main>
  </mdui-layout>
</template>

<style>
*{
  padding: 0;
  margin: 0;
}

mdui-card h1 {
  padding: 0.2em 0.2em;
}

.header {
  margin-top: 4em;
  margin-bottom: 8em;
}

.header h1 {
  width: 100%;
  text-align: center;
}

.header .desc {
  margin: auto;
  width: 75%;
  text-align: center;
}

.links {
  height: 10em;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

mdui-card {
  margin: 3px;
  width: calc(25% - 6px);
  height: 8em;
}

@media screen and (max-width: 640px) {
  mdui-card {
    width: calc(100% - 6px);
  }

  .links {
    height:auto;
    flex-direction: column;
    flex-wrap: nowrap;
  }

  .header {
    margin-bottom:2em;
  }

  .header .desc {
    width: 90%;
  }
}
</style>
