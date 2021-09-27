<template>
  <div>
   <b-container>
   
   <!--popup start for Update Faculty--> 
    <div >
       <b-modal id="modal-5" title="Update Faculty" hide-footer>
          <b-form ref="form" @submit.stop.prevent="onSubmit">
          
            <b-form-group id="example-input-group-18"  label="Faculty name:" label-for="example-input-1">
                  <b-form-input  id="example-input-18" name="example-input-18" v-model="$v.form.fn1.$model"
                                 :state="validateState('fn1')" placeholder="Enter your Faculty name">
                  </b-form-input> 
          
                  <b-form-invalid-feedback  id="input-18-live-feedback">This is a required field and must be at least 6 characters.
                  </b-form-invalid-feedback>
            </b-form-group><br>
            
            <b-form-group label="Qualification:" >
                 <b-form-input id="example-input-19"  name="example-input-19" v-model="$v.form.qua1.$model" 
                           :state="validateState('qua1')" placeholder="Enter your Qualification">
                 </b-form-input>
                             
                 <b-form-invalid-feedback  id="input-19-live-feedback">This is a required field and must be at least 2 characters.
                 </b-form-invalid-feedback>
            </b-form-group><br>
            
            <b-form-group label="Experience:">
               <b-form-input id="example-input-20"  name="example-input-20" v-model="$v.form.ex1.$model" 
                    :state="validateState('ex1')" type="number" placeholder="Enter your Experience" >
               </b-form-input>
            
               <b-form-invalid-feedback  id="input-20-live-feedback">This is a required field and must be 1 numbers.
               </b-form-invalid-feedback>
            </b-form-group><br>
            
            <b-form-group label="Skill set:">
                <b-form-input id="example-input-21"  name="example-input-21" v-model="$v.form.ss1.$model" 
                    :state="validateState('ss1')" type="password" placeholder="Enter your Skill set" >
                </b-form-input>
               
                <b-form-invalid-feedback  id="input-21-live-feedback">This is a required field and must be at least 6 characters.
                </b-form-invalid-feedback>
            </b-form-group><br>
            
         
            
            
            
            
            <div class="text-center">
              <b-button type="submit" variant="outline-success">Submit</b-button>
              <b-button variant="outline-danger" class="mx-3" @click="resetForm()">Reset</b-button>
            </div>
         </b-form>
       </b-modal>
    </div>
    <!--popup end for Update Faculty--> 
    
    
   </b-container>
  </div>
</template>

<script>

import { validationMixin } from "vuelidate";
import { required, minLength, maxLength } from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],
  data() {
    return {
      
      form: {
        fn1: null,
        qua1: null,
        ex1: null,
        ss1: null
      }
    };
  },
  validations: {
    form: {
      qua1: {
        required,
        minLength: minLength(2)
      },
      fn1: {
        required,
        minLength: minLength(6)
      },
      ex1: {
        required,
        minLength: minLength(1),
        maxLength: maxLength(2),
      },
      ss1: {
        required,
        minLength: minLength(6)
      },
    }
  },
  methods: {
    validateState(fn) {
      const { $dirty, $error } = this.$v.form[fn];
      return $dirty ? !$error : null;
    },
    
    resetForm() {
      this.form = {
        fn1: null,
        qua1: null,       
        ex1: null,
        ss1: null,
      };

      this.$nextTick(() => {
        this.$v.$reset();
      });
    },
    onSubmit() {
      this.$v.form.$touch();
      if (this.$v.form.$anyError) {
        return;
      }

      alert("Faculty Updated successfully !!!");
      location.reload();
    }
  }
};
 

</script>
