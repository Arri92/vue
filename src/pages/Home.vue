
<template>
<div class="mt-10">
  <v-row
  class=" mx-auto px-16">
<v-text-field
            label="Login"
            class="px-10"
            placeholder="Login"
            outlined
            clearable
            v-model="userName"
            type="text"
          ></v-text-field>
<v-text-field
            label="Hasło"
            class="px-10"
            placeholder="Hasło"
            outlined
            clearable
            v-model="userPass"
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :type="show1 ? 'text' : 'password'"
            @click:append="show1 = !show1"
          ></v-text-field>     
<v-btn
 color="primary"
 class="mx-auto mt-2 "
 @click="but" 
 elevation="3" 
>zaloguj</v-btn>
  </v-row>
</div>
</template>

<script>
import {mapActions} from "vuex";

export default {
  name: 'Home',
  components: {},
  data: () => ({
     usersPass: '',
     usersName: '',
     show1: false,
      rules: {
        required: value => !!value || 'Required.',
        min: v => v.length >= 8 || 'Min 8 characters',
        emailMatch: () => (`The email and password you entered don't match`),
      },
    }
  ),
  mounted(){
  this.usersName = this.$store.getters.getUsersName
  this.usersPass = this.$store.getters.getUsersPass
  },
   methods: {
     ...mapActions([
       'setLogged'
     ]),
    but(){
      if(this.userName===this.usersName && this.userPass===this.usersPass){
        this.setLogged(this.userName)
        this.$router.push("/Tlog")
      }else{
        this.$router.push("/Flog")
      }
     
    }
  }

  }

</script>


