<template>
  <div id="app">
    <Topbar class="topbar" />
    <main>
      <Editor class="editor" />
      <Preview class="preview" />
    </main>
  </div>
</template>

<script>
import Topbar from './components/Topbar'
import Editor from './components/Editor'
import Preview from './components/Preview'
export default {
  components: {
    Topbar, Editor, Preview
  }
}
</script>


<style lang="scss">
.icon {
       width: 1em; height: 1em;
       vertical-align: -0.15em;
       fill: currentColor;
       overflow: hidden;
    }

#app {
  display: flex;
  flex-direction: column;
  height: 100vh;
}

main {
  display: flex;
  flex: 1;
  >.editor {
    width: 35vw;
    margin:16px 8px 16px 16px;
  }
  >.preview {
    flex: 1;
    margin:16px 16px 16px 8px;
  }
}
</style>


