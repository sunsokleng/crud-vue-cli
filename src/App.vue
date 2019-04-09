 <template>
  <div id="app">
    <label>FirstName</label>
    <input type="text" v-model="firstname"><br/>
    <label>LastName</label>
    <input type="text" v-model="lastname"><br/>
    <button @click="handleSave()">Save</button>
   
   <ul :key= 'index' v-for = "(list, index) in lists">
     
     {{list.firstname}} {{list.lastname}}
     <button @click="handleDelete(index)">Delete</button>
     <button @click="handleUpdate(index)">Update</button>
   </ul>
  </div>
</template>

<script>
export default {  
  
  data() {
    return {
      firstname: "",
      lastname: "",
      lists:[]
    }
  },
  
 methods:{
   
   handleSave(){
     const {firstname, lastname}=this;
     this.lists.push({firstname, lastname})
     //this.lists.push({firstname:this.firstname, lastname:this.lastname});
     this.handleClear();
   },

    handleDelete(index){
      this.lists.splice(index,1);
    },
    
    handleUpdate(index){
      this.firstname=this.lists[index].firstname;
      this.lastname=this.lists[index].lastname;
      this.lists.splice(index,1);
    },
    
    handleClear(){
     this.firstname = "";
     this.lastname = "";
   }
 }
}
</script>

