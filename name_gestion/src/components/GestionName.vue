
<script setup>
import { ref, reactive, computed, watch } from 'vue'

const names = reactive(['Emil, Hans', 'Mustermann, Max', 'Tisch, Roman',
  'Alice, Brown','Egg, Green','Bob, Python'])
const selected = ref('')
const prefix = ref('')
const first = ref('')
const last = ref('')

const filteredNames = computed(() =>
    names.filter((n) =>
        n.toLowerCase().startsWith(prefix.value.toLowerCase())
    )
)

watch(selected, (name) => {
  ;[last.value, first.value] = name.split(', ')
})

function create() {
  if (hasValidInput()) {
    const fullName = `${last.value}, ${first.value}`
    if (!names.includes(fullName)) {
      names.push(fullName)
      first.value = last.value = ''
    }
  }
}

function update() {
  if (hasValidInput() && selected.value) {
    const i = names.indexOf(selected.value)
    names[i] = selected.value = `${last.value}, ${first.value}`
  }
}

function del() {
  if (selected.value) {
    const i = names.indexOf(selected.value)
    names.splice(i, 1)
    selected.value = first.value = last.value = ''
  }
}

function hasValidInput() {
  return first.value.trim() && last.value.trim()
}
</script>

<template>
  <div class="container">

    <div class="search-box">
      <input v-model="prefix" placeholder="Filter prefix" class="search-input">
    </div>

    <div class="content-wrapper">
      <select size="5" v-model="selected">
        <option v-for="name in filteredNames" :key="name">{{ name }}</option>
      </select>

      <div class="form-container">
        <div class="input-group">
          <label>Name: <input class="input-label" v-model="first"></label>
          <label>Surname: <input class="input-label" v-model="last"></label>
        </div>
      </div>

      <div class="buttons">
        <button class="btn" @click="create">Create</button>
        <button class="btn" @click="update">Update</button>
        <button class="btn" @click="del">Delete</button>
      </div>

    </div>



  </div>
</template>

<style scoped>
.search-box {
  padding-bottom: 10px;
}
.search-input {
  width: 200px;
}

select {
  float: left;
  margin: 0 2px 2px 0;
  width: 200px;
  height: 120px;

}

.input-group {
  display: flex;
  gap: 5px;
  flex-direction: column;
  padding-bottom: 10px;
  padding-left: 10px;
}


.buttons {
  padding: 5px;
  margin: 5px;
}
.btn {
  background-color: lightgreen;
  color: black;
  border-radius: 8px;
  border-color: honeydew;
  padding: 3px;
  margin-left: 5px;
}



</style>