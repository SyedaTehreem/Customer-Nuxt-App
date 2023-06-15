<template>
    <div>
      <!-- Render the EditCustomer component here -->
      <EditCustomer :customerId="customerId" />
    </div>
  </template>
  
  <script>
  import EditCustomer from '~/components/EditCustomer.vue';
  
  export default {
    components: {
      EditCustomer,
    },
  
    // Access the customer ID from the route params
    computed: {
      customerId() {
        return this.$route.params.id;
      },
    },
  };
  </script>
  