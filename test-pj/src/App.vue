<template>
  <div id="app">
    <div class="body">
      <div class="list">
        <p>Todo List</p>
        <input type="text" v-model="addText">
        <button @click="addToDo()">追加</button>
      </div>
        <ul class="form" v-for="todo in todos" :key="todo">
          <li>
            {{todo.text}}
          </li>
              <button class="edit" @click="editToDo()">更新</button>
              <button class="delete" @click="deleteItem(todo)">削除</button>
        </ul>
    </div>
  </div>
</template>

<script>
export default{
  data(){
    return{
      addtext:"",
      todos:[],
    };
  },
  methods:{
    addToDo(){
      if(this.addText){
        this.todos.push({
          'text':this.addText
        });
        this.addText='';
      }
    },
    deleteItem(todo){
      this.todos.splice(todo, 1);
    }
  }
}
</script>


<style>
html, body, div, span, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
abbr, address, cite, code,
del, dfn, em, img, ins, kbd, q, samp,
small, strong, sub, sup, var,
b, i,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, figcaption, figure,
footer, header, hgroup, menu, nav, section, summary,
time, mark, audio, video {
    margin:0;
    padding:0;
    border:0;
    outline:0;
    font-size:100%;
    vertical-align:baseline;
    background:transparent;
}

body {
    line-height:1;
}

article,aside,details,figcaption,figure,
footer,header,hgroup,menu,nav,section {
    display:block;
}

nav ul {
    list-style:none;
}

blockquote, q {
    quotes:none;
}

blockquote:before, blockquote:after,
q:before, q:after {
    content:'';
    content:none;
}

a {
    margin:0;
    padding:0;
    font-size:100%;
    vertical-align:baseline;
    background:transparent;
}

/* change colours to suit your needs */
ins {
    background-color:#ff9;
    color:#000;
    text-decoration:none;
}

/* change colours to suit your needs */
mark {
    background-color:#ff9;
    color:#000;
    font-style:italic;
    font-weight:bold;
}

del {
    text-decoration: line-through;
}

abbr[title], dfn[title] {
    border-bottom:1px dotted;
    cursor:help;
}

table {
    border-collapse:collapse;
    border-spacing:0;
}

/* change border colour to suit your needs */
hr {
    display:block;
    height:1px;
    border:0;  
    border-top:1px solid #cccccc;
    margin:1em 0;
    padding:0;
}

input, select {
    vertical-align:middle;
}

html{
  background-color:#191970;
}



.body{
  position:relative;
  top:300px;
  left:520px;
  background-color:#fff;
  width:30%;
  height:auto;
  border-radius:20px;
  padding:30px;

  
}

.list{
  position:relative;
  top:20%;
  left:10%;
}

p{
  font-weight:bold;
  font-size:25px;
  line-height:1.5em;
  margin-bottom:0.5em;
}

input{
  height:30px;
  width:65%;
  border-radius:4px;
  border-color:#dcdcdc;
}

button{
  height:35px;
  width:60px;
  margin-left:14px;
  border-radius:4px;
  background-color:#fff;
  color:#ff69b4;
  border-color:#ff69b4;
  cursor: pointer;
  transition:0.4s ease;
}

button:hover{
  color:#fff;
  background-color:#ff69b4;
}

.body li{
  border:1px solid #c0c0c0;
  padding:9px 0 9px 0;
  height:16px auto;
  width:47%;
  border-radius:4px;
}

.form{
  display:flex;
  position:relative;
  top:20px;
  left:45px;
}

.edit{
  height:35px;
  width:60px;
  margin:14px;
  border-radius:4px;
  background-color:#fff;
  color:#ffa500;
  border-color:#ffa500;
  cursor: pointer;
  transition:0.4s ease;
  position:relative;
  bottom:14px;
  left:7px;
}

.edit:hover{
  color:#fff;
  background-color:#ffa500;
}

.delete{
  height:35px;
  width:60px;
  margin-left:14px;
  border-radius:4px;
  background-color:#fff;
  color:#00bfff;
  border-color:#00bfff;
  cursor: pointer;
  transition:0.4s ease;
}

.delete:hover{
  color:#fff;
  background-color:#00bfff;
}
</style>
