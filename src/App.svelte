<script>
  import marked from "marked";
  let source = "#New document";
  $: markdown = marked(source);
</script>

<style>
  .header {
    height: 10vh;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .header-title {
    margin: 0;
  }
  .markdown-editor {
    width: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: space-evenly;
  }
  .markdown-editor_left-panel,
  .markdown-editor_right-panel {
    width: 50%;
    border: solid 1px black;
    height: 90vh;
  }

  .markdown-editor_right-panel {
    overflow: auto;
  }
  .markdown-editor_source {
    border: none;
    width: 100%;
    height: 100%;
  }
  .markdown-editor_source:focus {
    outline: none;
  }

  .markdown-editor_output {
    width: 100%;
    padding: 0 2em;
  }
</style>

<header class="header">
  <h1 class="header-title">Svelte Powered Markdown</h1>
</header>
<div class="markdown-editor">
  <div class="markdown-editor_left-panel">
    <textarea bind:value={source} class="markdown-editor_source" />
  </div>

  <div class="markdown-editor_right-panel">
    <div class="markdown-editor_output">
      {@html markdown}
    </div>
  </div>
</div>
