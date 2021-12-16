<template>
    <div id="tlog">
  <div color="secondary"><span class="secondary--text">witaj {{ this.getUsersName }}</span></div>
  <router-link to="/">Logout</router-link>
  </div>
</template>

<script>
import { mapGetters} from "vuex";

import {mapActions} from "vuex";


export default {
    out(){
        this.userName = ""
        this.setLogout(this.userName)
        this.$router.push("/")
      },
  
  name: 'Tlog',
  methods: {
     ...mapActions([
       'setLogout'
     ]),
  },
  components: {},
   computed: {
    ...mapGetters([
      'getUsersName',
    ])
  }
};
</script>
