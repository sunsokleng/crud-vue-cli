 <template>
  <div id="app">
    <label>FirstName</label>
    <input type="text" v-model="firstname"><br/>
    <label>LastName</label>
    <input type="text" v-model="lastname"><br/>
    <button @click="handleSave()">Save</button>
   
   <ul v-bind:key= 'list' v-for = "list in lists">
     {{list.firstname}} {{list.lastname}}
   </ul>
  </div>
</template>

<script>

export default {  
  data() {
    return {
      lists:[
      {
        firstname:'',
        lastname: ''
      }
      ]
    }
  },
  
 methods:{
   handleSave(){
     this.lists.push({firstname:this.firstname, lastname:this.lastname});
     this.handleClear();
   },

   handleClear(){
     this.firstname = "";
     this.lastname = "";
   }
 }
}
</script>

