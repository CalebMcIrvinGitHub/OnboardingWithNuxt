<template>

    <div>
        <script src="https://cdnjs.cloudflare.com/ajax/libs/vue/1.0.18/vue.min.js"></script>
        <label for = "countries">Countries Dropdown</label>
        <select id="countries" @change = "populateStates()">
            <option id="default"></option>
        </select>
    
        <br>

        <label for = "states">States Dropdown</label>
        <select id="states">
        </select>


        <br>
        <hr>
        <br>
        
        <div class="container">
            <label for ="countryName">Name of country to add</label>
            <input type="text" id="countryName" ref = "countryName">
            <br>
            <label for="countryCode">Code of country to add</label>
            <input type="text" id="countryCode" ref = "countryCode">
            <br>
            <button id = "addCountryBTN" @click="addCountry()">Add Country</button>
        </div>

        <br>
        <hr>
        <br>

        <div class="container">
            <label for="stateName">Name of state to add</label>
            <input type="text" id="stateName">
            <br>
            <label for="stateCode">Code of state to add</label>
            <input type="text" id="stateCode">
            <br>
            <label for="countryAddTo">ID of country to add the state to</label>
            <select id="countryAddTo">
                <option id="default"></option>
            </select>
            <br>
            <button id = "addStateBTN" @click="addState()">Add State</button>
        </div>
        
    </div>

</template>


<script>
    import * as helper from '../components/helperMethods.js'

    export default {
        methods: {
            populateStates() {
                helper.populateStates();
            },
            addCountry() {
                helper.addCountry(this.$refs.countryName.value, this.$refs.countryCode.value);
            },
            addState() {
                helper.addState();
            }
        }, 
        beforeMount() {
            helper.populateCountries();
        }
    }
</script>