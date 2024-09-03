<template>
    <nav class="navbar">
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <div>
            <ul>
                <li><router-link to="/history">History</router-link></li> 
                <li><router-link to="/settings">Settings</router-link></li>
            </ul>
        </div>
      </ul>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'Navbar'
  };
  </script>
  
  <style scoped>
.navbar {
  background-color: #42b983;
  padding: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* Flex container for left and right sections */
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  width: 100%;
  display: flex;
  justify-content: space-between; /* Space between left and right sections */
  align-items: center;
}

.left {
  margin-right: auto; /* Pushes the left section to the left */
}

.right-links {
  display: flex;
  gap: 20px; /* Space between right-side links */
}

.navbar a {
  color: white;
  text-decoration: none;
  font-size: 1.2rem;
}

.navbar a:hover {
  text-decoration: underline;
}
</style>