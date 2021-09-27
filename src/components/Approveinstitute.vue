<template>
   <div>
   
       <div>    
         <NavBar />
       </div>
     
       <div>
        <b-container>
          <h1>Approve Institute</h1><br><br>
            <b-table-simple  responsive >      
              <b-thead head-variant="dark">
               <b-tr>
                <b-th>College ID</b-th>
                <b-th>College Name</b-th>
                <b-th>College Status</b-th>
               </b-tr>
              </b-thead>
            </b-table-simple><br>
            <i>no information to display</i><br><br><br>
            
            <div class="text-center">
                <b-button type="button" variant="outline-danger " class="mx-5"><router-link to="/adminlogin">Back</router-link></b-button>
            </div><br>
              
        </b-container>
       </div>
       
       <div>  
       <Footer />
     </div>
</div>
</template>

<script>

import NavBar from './Navbar'
import Footer from './Footer'
export default {
  name: 'Approveinstitute',
  components:{
        NavBar,
        Footer
  },
  }
</script>


<style scoped>
 
thead {
  text-align: center;
  padding: 3px;
  background-color: black;
  color: white;
}
  
</style>
