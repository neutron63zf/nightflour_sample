<template>
  <div class="page-container">
    <md-app md-waterfall md-mode="fixed" class="app">
      <md-app-toolbar class="md-primary">
        <!--<div class="md-toolbar-row">
          <div class="md-toolbar-section-start">
            <md-button class="md-icon-button" @click="menuVisible = !menuVisible">
              <md-icon>menu</md-icon>
            </md-button>
            <span class="md-display-1">My Title</span>
          </div>

          <div class="md-toolbar-section-end">
            <md-button class="md-icon-button">
              <md-icon>more_vert</md-icon>
            </md-button>
          </div>
        </div>-->
        <md-button class="md-icon-button" @click="menuVisible = !menuVisible">
          <md-icon>menu</md-icon>
        </md-button>
        <span class="md-display-1">試作品（ver. 0.0.0）</span>

        <!--<div class="md-toolbar-row md-toolbar-offset">
          <span class="md-display-1">My Title</span>
        </div>-->
      </md-app-toolbar>

      <md-app-drawer :md-active.sync="menuVisible" md-parent="full">
        <md-toolbar class="md-transparent" md-elevation="0">
          Navigation
        </md-toolbar>

        <md-list>
          <md-list-item>
            <md-icon>move_to_inbox</md-icon>
            <span class="md-list-item-text">Inbox</span>
          </md-list-item>

          <md-list-item>
            <md-icon>send</md-icon>
            <span class="md-list-item-text">Sent Mail</span>
          </md-list-item>

          <md-list-item>
            <md-icon>delete</md-icon>
            <span class="md-list-item-text">Trash</span>
          </md-list-item>

          <md-list-item>
            <md-icon>error</md-icon>
            <span class="md-list-item-text">Spam</span>
          </md-list-item>
        </md-list>
      </md-app-drawer>

      <md-app-content class="content">
        <md-card>
            <md-card-header>
              <div class="md-title">Step 1 : 実行場所</div>
            </md-card-header>

            <md-card-content class="card">
              <p>
                Q1. 企画の実行場所を選択してください。
              </p>
              <md-field>
                <label for="movie">企画の実行場所</label>
                <md-select v-model="place" name="place" id="place">
                  <md-option value="outdoor">屋外</md-option>
                  <md-option value="indoor">屋内（安田講堂含む）</md-option>
                  <md-option value="stage">ステージ</md-option>
                </md-select>
              </md-field>
            </md-card-content>

        </md-card>

        <md-button class="md-raised button">送信</md-button>
      </md-app-content>
    </md-app>
  </div>
</template>

<style lang="scss" scoped>
.page-container, .app {
  height: 100%;
}

.md-app {
  border: 1px solid rgba(#000, 0.12);
}

p {
  font-size: 1.5em;
}

.card {
  margin: 16px;
}

.button {
  margin: 16px;
}
</style>

<script>
export default {
  name: "Waterfall",
  data: () => ({
    menuVisible: false,
    place: ''
  })
};
</script>
