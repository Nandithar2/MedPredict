<template>
    <div class="home">
      <h1>MedPredict-Health Diagnosis</h1>
      <section class="symptom-input">
        <h2>Enter your symptoms</h2>
        <textarea v-model="symptoms" placeholder="Describe your symptoms here..."></textarea>
        <button @click="submitSymptoms">Submit Symptoms</button>
      </section>
  
      <section v-if="predictions.length" class="predictions">
        <h2>Disease Predictions</h2>
        <ul>
          <li v-for="(prediction, index) in predictions" :key="index">
            <span>{{ prediction.name }} - Likelihood: {{ prediction.likelihood }}%</span>
            <button @click="explorePrediction(prediction)">Explore Further</button>
          </li>
        </ul>
      </section>

      <section>
        <h2>Recommendations</h2>
        <ul>Based on your symptoms, we recommend you to visit a doctor for further diagnosis.</ul>
        <button>Home Remedies</button>
      </section>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        symptoms: '',
        predictions: []
      };
    },
    methods: {
      submitSymptoms() {
        // Simulate ML model prediction based on symptoms
        this.predictions = [
          { name: 'Flu', likelihood: 75 },
          { name: 'Common Cold', likelihood: 60 },
          { name: 'COVID-19', likelihood: 40 }
        ];
      },
      explorePrediction(prediction) {
        // Navigate to the NLP-based confirmation page (to be built)
        alert(`You chose to explore: ${prediction.name}`);
      }
    }
  };
  </script>
  
  <style scoped>
  .home {
    margin: 2rem;
  }
  .symptom-input {
    margin-bottom: 2rem;
  }
  textarea {
    width: 80%;
    height: 100px;
    margin-bottom: 1rem;
  }
  button {
    background-color: #42b983;
    color: white;
    padding: 10px;
    border: none;
    cursor: pointer;
  }
  button:hover {
    background-color: #34997f;
  }
  .predictions ul {
    list-style: none;
    padding: 0;
  }
  .predictions li {
    margin-bottom: 1rem;
  }
  </style>
  