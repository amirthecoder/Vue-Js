<template>
 <div class="container">
<Header title="RealEstate reminder"/>
<Tasks @toggle-reminder="toggleReminder"
@delete-task="deleteTask" :tasks="tasks"/>
 </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'

export default {
  name: 'App',
  components: {
      Header,
      Tasks,
  },
  
  
  data (){

    return{
      tasks:[],
    }
  },

    methods:{
   deleteTask(id){ 
 
      if(confirm('Are you sure')){
        this.tasks = this.tasks.filter((task)=>task.id!==id)
     }    
   },
    toggleReminder(id){
       
           this.tasks = this.tasks.map((task)=>
           this.id==id ?{ ...task, reminder: !task.
          reminder}:task) 
        

        
 
     },
  },

  created(){
    this.tasks=
  [
     {
      id:1,
      text:'1000 bayview avenue',
      day: 'March 15  at 7.00pm',
      reminder:true,
    },
    {
      id:2,
      text:'7676 yonge street',
      day: 'March 18  at 5.00pm',
      reminder:false,
    },
    {
      id:3,
      text:'7676 dandas square',
      day: 'MArch 21  at 6.00pm',
      reminder:true,
    }
  ]
  }

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}
</style>
