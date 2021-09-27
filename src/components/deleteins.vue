<template>
  <div>
    <div>    
       <NavBar />
     </div>
     <div>    
       <b-container>
         <h1>Colleges</h1>
        </b-container>
     </div>
     
     <div>
        <b-container>
            <b-table-simple responsive>      
              <b-thead>
               <b-tr>
                <b-th>College ID</b-th>
                <b-th>College Name</b-th>
                <b-th>Action</b-th>
               </b-tr>
              </b-thead>
              <b-tbody>
               <b-tr>
                <b-td>4477</b-td>
                <b-td>SRM</b-td>
                <b-td><a href="">View</a> / <a href="">delete</a></b-td>
               </b-tr>
               <b-tr>
                <b-td>0477</b-td>
                <b-td>KLN</b-td>
                <b-td><a href="">View</a> / <a href="">delete</a></b-td>
               </b-tr>
               <b-tr>
                <b-td>9843</b-td>
                <b-td>LDC</b-td>
                <b-td><a href="">View</a> / <a href="">delete</a></b-td>
               </b-tr>
               <b-tr>
                <b-td>6577</b-td>
                <b-td>MKU</b-td>
                <b-td><a href="">View</a> / <a href="">delete</a></b-td>
               </b-tr>
              </b-tbody>
            </b-table-simple><br>
           
            
            <div class="text-center">
                <b-button type="button" variant="outline-danger " class="mx-5"><router-link to="/adminlogin"> Back </router-link></b-button>
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
  name: 'adminlogin',
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
table {
 border: 50px;
}
  
</style>
