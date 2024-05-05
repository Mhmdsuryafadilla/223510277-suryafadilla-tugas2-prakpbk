<template>
  <div>
    <div class="container">
      <input type="text" v-model="inputText" @input="handleInput" class="input-field">
    
      <div class="output" :style="{ color: textColor, 'font-weight': isBold ? 'bold' : 'normal' }">
        Input teks Anda: {{ inputText }}
      </div>
      
      <div class="buttons">
        <button @click="toggleTextColor" class="toggle-btn">Toggle Warna Teks</button>
        <button @click="toggleBold" class="toggle-btn">Toggle Bold</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputText: '',
      isBold: false,
      textColor: 'black'
    };
  },
  methods: {
    handleInput(event) {
      this.inputText = event.target.value;
    },
    toggleTextColor() {
      const randomColor = '#' + Math.floor(Math.random()*16777215).toString(16);
      this.textColor = randomColor;
    },
    toggleBold() {
      this.isBold = !this.isBold;
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 500px;
  margin: 50px auto;
  padding: 20px;
  border: 2px solid #ddd;
  border-radius: 10px;
  background-color: #f9f9f9;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.input-field {
  padding: 10px;
  font-size: 16px;
  width: calc(100% - 22px);
  margin-bottom: 20px;
  border: 2px solid #ddd;
  border-radius: 5px;
}

.output {
  padding: 10px;
  font-size: 18px;
  transition: color 0.3s ease-in-out;
}

.buttons {
  margin-top: 20px;
  display: flex;
  justify-content: center;
}

.toggle-btn {
  padding: 10px 20px;
  margin: 0 10px;
  border: none;
  border-radius: 5px;
  font-size: 16px;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out, transform 0.2s ease-in-out;
}

.toggle-btn:hover {
  background-color: #4CAF50;
  color: white;
  transform: scale(1.05);
}

.toggle-btn:focus {
  outline: none;
}
</style>
