
<script>

export default {
  data() {
    return {
      users: [],
    }
  },
    mounted() {
    

    this.fetchData();
    // Fetch data from the API here using axios
},

    methods: {
    async fetchData(){
        try {
            const response = await fetch('https://dummyjson.com/users');
            const data = await response.json();

            this.users = data.users;
            
            } catch (error) {
            console.error('Error fetching data', error);
        }
        
    },
},
}

</script>


<template>
    <div> Select your searching preference
        <div class="flex pr-3">
        <label for="dropdown">Select</label>
    <select id="dropdown" v-model="selectedOption">
        <option value="option1">FirstName</option>
        <option value="option2">LastName</option>
        <option value="option3">Email</option>
        <option value="option4">Phone</option>
        <option value="option5">Department</option>
        <option value="option6">City</option>
    </select>

    <label for="dropdown">Select</label>
    <select id="dropdown" v-model="selectedOption">
        <option value="option1">FirstName</option>
        <option value="option2">LastName</option>
        <option value="option3">Email</option>
        <option value="option4">Phone</option>
        <option value="option5">Department</option>
        <option value="option6">City</option>
    </select>

    <label for="dropdown">Select</label>
    <select id="dropdown" v-model="selectedOption">
        <option value="option1">FirstName</option>
        <option value="option2">LastName</option>
        <option value="option3">Email</option>
        <option value="option4">Phone</option>
        <option value="option5">Department</option>
        <option value="option6">City</option>
    </select>

    </div>
    </div>
    <div>
    <table class="flex flex-auto place-content-center">
        <thead>
        <tr>
            <th>FirstName</th>
            <th>LastName</th>
            <th>Email</th>
            <th>Phone</th>
            <th>Username</th>
            <th>Hair</th>
            <th>EIN</th>
            
            
            <!-- Add more table headers for other user attributes -->
        </tr>
        </thead>
        <tbody>
        <tr v-for="user in users" :key="user.id">
            <td>{{ user.firstName }}</td>
            <td>{{ user.lastName }}</td>
            <td>{{ user.email }}</td>
            <td>{{ user.phone }}</td>
            <td>{{ user.username }}</td>
            <td>{{ user.hair }}</td>
            <td>{{ user.ein }}</td>
            {{ data }}
        </tr>
        </tbody>
    </table>
    </div>
</template>
