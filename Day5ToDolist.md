```HTML
<!DOCTYPE html>
<html lang="en">

<head>
  <title></title>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <script src="./vue2.js"></script>
  <style>

    #app{
            width:600px;
                margin:10px auto;
        }
          .tb{
              border-collapse:collapse;
              width: 100%;
          }
          .tb th{
              background-color: blueviolet;
              color:whitesmoke;
          }
  
          .tb td,.tb th{
              padding:5px;
              border:1px solid whitesmoke;
              text-align: center;
          }
  
          
      </style>
</head>

<body>
  
  <div class="text" style=" text-align:center;">ToDoList</div>

  <div id="app">
    <div class="add">
      要完成的事:<input type="text" v-model="newId">
      <input type="button" value="添加" @click="addData">
    </div>

    <div>
      <table class="tb">
        <tr>
          <th>具体任务</th>
          <th>删除操作</th>
        </tr>
        <tr v-for="(item,index) in list" :key="index">
          <td>{{item.id}}</td>
          <td>
            <button @click="delData(index)">删除</button>
          </td>
        </tr>
      
      </table>
    </div>
  </div>
</body>
<script>
  let vm = new Vue({
    el: '#app',
    methods: {
      delData(idx) {
        this.list.splice(idx, 1)
      },
      addData() {
        this.list.push({id: this.newId})
        this.newId = ''
      }
    }
  })
</script>

</html>
```
**尚未完成。。。**