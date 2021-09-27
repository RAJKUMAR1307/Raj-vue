<template>
  <div>
   <b-container>
   
   <!--popup start for Add Faculty--> 
    <div >
       <b-modal id="modal-4" title="Add Faculty" hide-footer>
          <b-form ref="form" @submit.stop.prevent="onSubmit">
          
            <b-form-group id="example-input-group-14"  label="Faculty name:" label-for="example-input-1">
                  <b-form-input  id="example-input-14" name="example-input-14" v-model="$v.form.fn.$model"
                                 :state="validateState('fn')" placeholder="Enter your Faculty name">
                  </b-form-input> 
          
                  <b-form-invalid-feedback  id="input-14-live-feedback">This is a required field and must be at least 6 characters.
                  </b-form-invalid-feedback>
            </b-form-group><br>
            
            <b-form-group label="Qualification:" >
                 <b-form-input id="example-input-15"  name="example-input-15" v-model="$v.form.qua.$model" 
                           :state="validateState('qua')" placeholder="Enter your Qualification">
                 </b-form-input>
                             
                 <b-form-invalid-feedback  id="input-15-live-feedback">This is a required field and must be at least 2 characters.
                 </b-form-invalid-feedback>
            </b-form-group><br>
            
            <b-form-group label="Experience:">
               <b-form-input id="example-input-16"  name="example-input-16" v-model="$v.form.ex.$model" 
                    :state="validateState('ex')" type="number" placeholder="Enter your Experience" >
               </b-form-input>
            
               <b-form-invalid-feedback  id="input-16-live-feedback">This is a required field and must be 1 numbers.
               </b-form-invalid-feedback>
            </b-form-group><br>
            
            <b-form-group label="Skill set:">
                <b-form-input id="example-input-17"  name="example-input-17" v-model="$v.form.ss.$model" 
                    :state="validateState('ss')" type="password" placeholder="Enter your Skill set" >
                </b-form-input>
               
                <b-form-invalid-feedback  id="input-17-live-feedback">This is a required field and must be at least 6 characters.
                </b-form-invalid-feedback>
            </b-form-group><br>
            
         
            
            
            
            
            <div class="text-center">
              <b-button type="submit" variant="outline-success">Submit</b-button>
              <b-button variant="outline-danger" class="mx-3" @click="resetForm()">Reset</b-button>
            </div>
         </b-form>
       </b-modal>
    </div>
    <!--popup end for Add Faculty--> 
    
    
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
        fn: null,
        qua: null,
        ex: null,
        ss: null
      }
    };
  },
  validations: {
    form: {
      qua: {
        required,
        minLength: minLength(2)
      },
      fn: {
        required,
        minLength: minLength(6)
      },
      ex: {
        required,
        minLength: minLength(1),
        maxLength: maxLength(2),
      },
      ss: {
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
        fn: null,
        qua: null,       
        ex: null,
        ss: null,
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

      alert("Faculty added successfully !!!");
      location.reload();
    }
  }
};
 

</script>
