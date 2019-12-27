<template>
  <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
          <b-form-group>

                <b-countainer-fluied>

                    <b-row class="my-1">
                        <b-col sm="1">
                            <label for="input-firstName">First Name *:</label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input id="input-firstName" size="30"   
                            v-model="form.firstName"
                            required
                            placeholder="Enter FirstName"></b-form-input>
                            </b-col> 

                        <b-col sm="1">
                            <label for="input-lastName">Last Name * :</label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input id="input-lastName"  
                            v-model="form.lastName"
                            required
                            size="30"
                            placeholder="Enter lastname" >
                            </b-form-input>
                            </b-col>

                        </b-row>

                    
                </b-countainer-fluied>
        </b-form-group>

        <b-form-group >
             <b-countainer-fluied>

                    <b-row class="my-1">
                        <b-col sm="1">
                            <label for="input-email">Email *:</label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                    
                                v-model="form.email"
                                type="email"
                                required
                                placeholder="Enter email"
                                >
                                </b-form-input>
                            </b-col> 
                            
                        <b-col sm="1">
                            <label for="input-lastName">linkedin* :</label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                    
                            v-model="form.linkedin"
                            
                            placeholder=""
                            >
                            </b-form-input>
                            </b-col>
                    </b-row>
             </b-countainer-fluied>                        


                  
      </b-form-group>


      <b-form-group >
             <b-countainer-fluied>

                    <b-row class="my-1">
                        <b-col sm="1">
                            <label for="input-position">Position you applaying for *</label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                              
                                v-model="form.position"
                                required
                                placeholder=""
                    
                               
                            >
                                </b-form-input>
                            </b-col> 
                            
                        <b-col sm="1">
                            <label for="input-salaryrequirments">Salary Requirments * </label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                             v-model="form.requirments"
                             type="number"
                                
                             placeholder=""
                    
                          
                            >
                            </b-form-input>
                            </b-col>
                    </b-row>
             </b-countainer-fluied>                        


                  
      </b-form-group>


     <b-form-group>
         <b-countainer-fluid>
                <b-row class="my-1">
                        <b-col sm="1">
                            <label for="input-start">When can you start ?</label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                              
                            
                               v-model="form.start"

                                
                                placeholder=""
                               
                            >
                                </b-form-input>
                            </b-col> 
                            
                        <b-col sm="1">
                            <label for="input-salaryrequirments">Last comapny you  worked for  </label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                             
                              v-model="form.lastCompany"
                    
                          
                            >
                            </b-form-input>
                            </b-col>
                    </b-row>
               
         </b-countainer-fluid>




     </b-form-group>




<b-form-group>
         <b-countainer-fluid>
                <b-row class="my-1">
                        <b-col sm="1">
                            <label for="input-phone1">Mobile number *</label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                              
                            
                               v-model="form.phone1"
                                type="number"
                                
                                placeholder=""
                                required
                               
                            >
                                </b-form-input>
                            </b-col> 
                            
                        <b-col sm="1">
                            <label for="input-phone2">Alternative number </label>
                            </b-col>
                            <b-col sm="4">
                            <b-form-input
                             v-model="form.phone2"
                                type="number"
                                
                                placeholder=""
                                required
                          
                            >
                            </b-form-input>
                            </b-col>
                    </b-row>
               
         </b-countainer-fluid>




     </b-form-group>

     <b-form-group>
          <b-countainer-fluid>
                  <b-row class="my-1">
                        <b-col sm="2">
                            <label for="input-phone1">Are you willing to relocate? *</label>
                            </b-col>
                            <b-col sm="8">
                           <b-form-select 
                                v-model="form.when"
                                :options="whens"
                                
                                
                                >
                            </b-form-select>

                            </b-col> 
                  </b-row>
          </b-countainer-fluid>

      </b-form-group>


       <b-form-group>
          <b-countainer-fluid>
                  <b-row class="my-1">
                        <b-col sm="2">
                            <label for="input-CV">Upload Your CV *</label>
                            </b-col>
                            <b-col sm="8">
                         <b-form-file
                            v-model="file2"
                            :state="Boolean(file2)"
                            placeholder="Choose a file or drop it here..."
                            drop-placeholder="Drop file here..."
                            >
                            </b-form-file>
                             <div class="mt-3">Selected file: {{ file2 ? file2.name : '' }}</div>
                            

                            </b-col> 
                  </b-row>
          </b-countainer-fluid>

      </b-form-group>



      
      


     
















     



        

        <b-form-group label ="Reference / Comments / Questions" width:50%>
        
                <b-form-textarea
                        id="textarea"
                        v-model="text"
                        placeholder="Enter something..."
                        rows="3"
                        max-rows="6"
                >    
                </b-form-textarea>

        </b-form-group>






 
      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
   
  </div>
</template>

<script>
  export default {
    data() {
      return {
          
        form: {
          email: '',
          firstName: '',
          lastName:'',
          linkedin:'',
          position:'',
          requirments:'',
          text:'',
          file2:null,
          
          start:'',
          phone1:'',
          phone2:'',
          when: null,
          lastCompany:'',
          
        },
        whens: [{ text: 'Select One', value: null }, 'Yes', 'No', 'Not Sure', ],
        show: true
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.firstName = ''
        this.form.lastName=''
        this.form.linkedin=''
        this.form.position=''
        this.form.requirments=''
        this.form.start=''
        this.form.phone1=''
        this.form.phone2=''
        this.form.text=''
        this.form.when = null
        this.form.lastCompany=''
      
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>