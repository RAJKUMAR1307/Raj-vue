<template>
   <div>
     
       <div>    
         <NavBar />
       </div>
       
       <div>           
           <h1>Students List</h1>
       </div>
       
       
       <b-container>
          <b-table-simple class="table table-striped table-bordered" responsive>
            <b-thead>
                <b-tr>
                    <b-th>Name</b-th>
                    <b-th>Email</b-th>
                    <b-th>Mobile number</b-th>
                    <b-th>Role</b-th>
                </b-tr>
            </b-thead>
            <b-tbody>
                <b-tr v-for="user in users" :key="user.id">
                    <b-td>{{user.firstName}} {{user.lastName}}</b-td>
                    <b-td>{{user.email}}</b-td>
                    <b-td>{{user.number}}</b-td>
                    <b-td>{{user.role}}</b-td>
                </b-tr>
            </b-tbody>
         </b-table-simple>
      </b-container>
      
            <div class="text-center">
                <b-button type="button" variant="outline-danger " class="mx-5"><router-link to="/adminlogin"> <span>Back</span> </router-link></b-button>
            </div><br>

       <div>  
         <Footer />
       </div>
   
  </div>
</template>

<script>

  
  import NavBar from "./Navbar"
  import Footer from './Footer'
  export default {
       name: "Viewstudents",
  components: {
    NavBar,
    Footer
  },
    data() {
      return {
        users: [
                { firstName: 'Frank', lastName: 'Murphy', email: 'frank.murphy@test.com', number: '9876646777', role: 'User' },
                { firstName: 'Vic', lastName: 'Reynolds', email: 'vic.reynolds@test.com', number: '9876646888', role: 'Admin' },
                { firstName: 'Gina', lastName: 'Jabowski', email: 'gina.jabowski@test.com', number: '9876649977', role: 'Admin' },
                { firstName: 'Jessi', lastName: 'Glaser', email: 'jessi.glaser@test.com', number: '9876646007', role: 'User' },
                { firstName: 'Jay', lastName: 'Bilzerian', email: 'jay.bilzerian@test.com', number: '9876645557', role: 'User' }
            ]
      }
    }
  }
</script>
<style scoped>
 
thead {
  text-align: center;
  background-color: black;
  color: white;
}

  
</style>
