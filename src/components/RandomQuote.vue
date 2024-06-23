<script setup>
import { ref, onMounted } from "vue";
const quotes = ref([
    {
        text: "The only limit to our realization of tomorrow is our doubts of today.",
        author: "Franklin D. Roosevelt",
    },
    {
        text: "In the end, we will remember not the words of our enemies, but the silence of our friends.",
        author: "Martin Luther King Jr.",
    },
    {
        text: "The best way to predict the future is to create it.",
        author: "Peter Drucker",
    },
    {
        text: "It does not matter how slowly you go as long as you do not stop.",
        author: "Confucius",
    },
    {
        text: "Success is not final, failure is not fatal: It is the courage to continue that counts.",
        author: "Winston Churchill",
    },
    {
        text: "Believe you can and you're halfway there.",
        author: "Theodore Roosevelt",
    },
    {
        text: "Act as if what you do makes a difference. It does.",
        author: "William James",
    },
    {
        text: "What you get by achieving your goals is not as important as what you become by achieving your goals.",
        author: "Zig Ziglar",
    },
    { text: "Dream big and dare to fail.", author: "Norman Vaughan" },
    {
        text: "You miss 100% of the shots you don’t take.",
        author: "Wayne Gretzky",
    },
]);

const currentQuote = ref({ text: "", author: "" });

const getRandomQuote = () => {
    const randomIndex = Math.floor(Math.random() * quotes.value.length);
    currentQuote.value = quotes.value[randomIndex];
};

//it will be show when component add to DOM
onMounted(getRandomQuote);
</script>

<template>
    <div class="quote-generator">
        <h1 class="app-title">Random Quote Generator</h1>
        
        <blockquote class="quote-container">
            <p>{{ currentQuote.text }}</p>
            <cite>--{{ currentQuote.author }}</cite>
        </blockquote>

        <button @click="getRandomQuote" class="quote-button">Random Quote</button>
    </div>
</template>

<style scoped>
.quote-generator {
    max-width: 400px;
    margin: 50px auto;
    padding: 20px;
    text-align: center;
    border: 1px solid #ccc;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.app-title {
    font-size: 24px;
    margin-bottom: 20px;
    color: #333;
}

.quote-container {
    background-color: #f9f9f9;
    padding: 20px;
    border-radius: 8px;
    border: 1px solid #ddd;
    margin-bottom: 20px;
}

p {
    font-size: 18px;
    margin-bottom: 10px;
}

cite {
    font-style: normal;
    color: #777;
}

.quote-button {
    padding: 10px 20px;
    font-size: 16px;
    background-color: #3498db;
    color: #fff;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

.quote-button:hover {
    background-color: #2980b9;
}
</style>
