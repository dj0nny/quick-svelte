<script>
export let appTitle
export let done
export let undone
</script>

<style>
#header {
  display: flex;
  border-bottom: 1px solid #000;
  flex-direction: row;
}

#header .app-name {
  flex: 1;
  text-align: center
}

#header .stats {
  flex: 2;
  text-align: center;
  margin-top: 15px;
}

</style>

<div id="header">
  <div class="app-name">
    <h1>{appTitle}</h1>
  </div>
  <div class="stats">
    <div class="done">
      <strong>Todo completed: </strong>{done}
    </div>
    <div class="undone">
      <strong>Todo uncompleted: </strong>{undone}
    </div>
  </div>
</div>