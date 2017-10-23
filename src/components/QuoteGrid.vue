<template>
    <div class="row">
        <!--ToDo: Use the Quote component selector-->
            <!--Loop through the quote and index in quotes-->
            <!--Add a click event with .native and set it equal to the deleteQuote method created below-->
            <!--Display the quote inside the appQuote component, in other words pass the data object to the slot in Quote.vue-->
        <quote
          v-for="(quote,index) in quotes"
          @click.native="deleteQuote(index)"
        >{{quote}}</quote>
    </div>
</template>

<script>
    // ToDo: import the Quote Component
    import Quote from './Quote.vue';

    export default {
        // ToDo: Create props of quote
        props: {
          quotes:{
            type: Array
          }
        },

        components: {
            // ToDo: Initiate the Quote Component with a Custom Selector
            Quote
        },
        methods: {
            // ToDo: Create a method deleteQuote that takes a paremeter of index
                // Emit and event listener named quotesDeleted and passes the index parameter
            deleteQuote(index){
              this.$emit('quoteDeleted',index);
            }
        }
    }
</script>
