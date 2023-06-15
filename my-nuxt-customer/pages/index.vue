<template>
  <div>
    <Navbar @navigateToAbout="loadAbout" @navigateToHome="loadHome"
     @navigateToCustomer="loadCustomer" @navigateToEditCustomer="loadEditCustomer"
     @navigateToAddCustomer="loadAddCustomer"
      />
    
    <Home v-if="showHome" />
    <About v-if="showAbout" />
    <CustomerList v-if="showCustomer" />
    <EditCustomer v-if="showEditCustomer" />
    <AddCustomer v-if="showAddCustomer" />    
    

  </div>
</template>

<script>
import Navbar from '~/components/Navbar.vue';
import Home from '~/components/Home.vue';
import About from '~/components/About.vue';
import CustomerList from '~/components/CustomerList.vue';
import AddCustomer from '~/components/AddForm.vue';
import EditCustomer from '~/components/EditCustomer.vue';
//==================
export default {
  components: {
    Navbar,
    About, 
    Home,
    CustomerList,
    EditCustomer,
    AddCustomer,
   
  },
  data() {
    return {
      showAbout: false, 
      showHome: true,
      showCustomer: false,
      showEditCustomer: false,
      showAddCustomer: false,
    };
  },
  methods: {
    loadAbout() {
      this.showAbout = true;
      this.showHome = false; // Ensure only one component is shown at a time
      this.showCustomer = false;
      this.showEdiCustomer = false;
      this.showAddCustomer = false;
    },
    loadHome() {  //alert('Home');
      this.showHome = true;
      this.showAbout = false; // Ensure only one component is shown at a time
      this.showCustomer = false;
      this.showEdiCustomer = false;
      this.showAddCustomer = false;

    },
    loadCustomer() {  //alert('Home');
      this.showHome = false;
      this.showAbout = false; // Ensure only one component is shown at a time
      this.showCustomer = true;
      this.showEdiCustomer = false;
      this.showAddCustomer = false;

    },
    loadEditCustomer() {
    this.showHome = false;
    this.showAbout = false;
    this.showCustomer = false;
    this.showEdiCustomer = true;
    this.showAddCustomer = false;

  },
  loadAddCustomer() {
    this.showHome = false;
    this.showAbout = false;
    this.showCustomer = false;
    this.showEdiCustomer = false;
    this.showAddCustomer = true;

  },
  }
};
</script>
