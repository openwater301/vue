<template>
  <section>
    <ul>
      <li v-for="(todoItem, index) in propsdata" class="shadow">
        <i class="checkBtn fa fa-check" aria-hidden="true"></i>
        {{ todoItem }}
        <span class="removeBtn" type="button" @click="removeTodo(todoItem, index)">
          <i class="fa fa-trash-o" aria-hidden="true"></i>
        </span>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: ['propsdata'],  



  methods: {
    removeTodo(todoItem, index) {
      localStorage.removeItem(todoItem);
      this.todoItems.splice(index, 1);
    }
  }

}
</script>

<style scoped>
ul {
  list-style:none;
  padding-left:0;
  margin-top:0;
  text-align:left;
}
ul li {
  display:flex;
  min-height:50px; height:50px;
  line-height:50px;
  margin:0.5rem 0;
  padding:0 0.9rem;
  background-color:white;
  border-radius:5px;
}
.checkBtn{
  border:1px solid blue;
  line-height:45px;
  color:#62acde; 
  margin-right:50px;
}
.removeBtn{
  border:1px solid black;
  margin-left:auto;
  color:#de4343; 
}
</style>