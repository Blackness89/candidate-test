
<script>

export default {
    data() {
    return {
        users: [],
        selectedBloodGroup: '',
		selectedHairColor: '',
        search: '',
    };
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

computed: {
    bloodGroupOptions() {
      // get unique blood group values from users
    return Array.from(new Set(this.users.map(user => user.bloodGroup)));
    },
    hairColorOptions() {
      // get unique hair color values from users
    return Array.from(new Set(this.users.map(user => user.hair)));
    },
},

}

</script>




<template>
    <div class="all-label">
    <!-- Dropdown filters -->
    <label for="bloodGroup">Blood Group:</label>
    <select v-model="selectedBloodGroup" id="bloodGroup">
        <option v-for="option in bloodGroupOptions" :key="option" :value="option">
        {{ option }}
        </option>
    </select>

    <label for="hairColor">Hair Color:</label>
    <select v-model="selectedHairColor" id="hairColor">
        <option v-for="option in hairColorOptions" :key="user" :value="hair">
        {{ option }}
        </option>
    </select>

    <!-- Search input -->
    <input v-model="search" placeholder="Search...">

    <table class="table-auto">

    </table>
    </div>




    <div>
    <table >
        <thead>
        <tr class="head-list">
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


