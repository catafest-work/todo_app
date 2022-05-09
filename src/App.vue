<template>
<div id="wrapper">
  <input v-model="item_title">
  <button @click="addItem">Add</button>
  <!-- ':' for bind and '@' for event -->
  <ListItem 
    v-for="(item, index) in item_list" 
    :key="index" 
    :title="item"
    @delete-item="delItem(index)" 
  />
  <button @click="greet">Greet</button>
</div>
</template>

<script>

  import ListItem from './components/List_Item.vue'
  export default {
    components: {
      ListItem
    },

    data () {
        return {
          item_title: '',
          item_list: [] // array list
        }
      },

      methods: {
        addItem () 
        {
          this.item_list.push(this.item_title)
          this.item_title = ''
        },
        delItem (n) {
          // n is index of item list 
          this.item_list.shift(n,1)
        },
        greet() {
      // `this` inside methods points to the current active instance
      alert(`Hello ${this.name}!`)
      // `event` is the native DOM event
      if (event) {
        alert(event.target.tagName)
      }
    }
      }
  }
</script>