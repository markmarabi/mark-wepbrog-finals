<script setup>
import { ref } from 'vue'

import img1 from '@/assets/mnm.jpg'
import img2 from '@/assets/linkedin.jpg'
import img3 from '@/assets/broom1.jpg'
import img4 from '@/assets/experience.jpg'
import img5 from '@/assets/education.jpg'
import img6 from '@/assets/arrow.jpg'
import img7 from '@/assets/checkmark.jpg'
import img8 from '@/assets/renato.jpg'
import img9 from '@/assets/apc.jpg'
import img10 from '@/assets/email.jpg'

const email = ref('')
const message = ref('')
const successMessage = ref('')

function submitForm() {
  successMessage.value = 'Thank you! Your message has been sent.'
  email.value = ''
  message.value = ''
}
</script>

<template>
  <div id="app">
    <header>
      <h1>Resources</h1>
    </header>

    <main>
      <p>Here are the resources I used to create my personal profile website:</p>
      <ul>
        <li>
          <a href="https://www.youtube.com/watch?v=Jq_Zebxa-YI&t=416s" target="_blank">
            YouTube Tutorial 1
          </a>
        </li>
        <li>
          <a href="https://github.com/Ade-mir/html-css-js-portfolio-tutorial-2" target="_blank">
            GitHub Repository
          </a>
        </li>
        <li>
          <a href="https://tangerine-hummingbird-1479b6.netlify.app/" target="_blank">
            Netlify Example
          </a>
        </li>
        <li>
          <a href="https://www.youtube.com/watch?v=ldwlOzRvYOU&t=339s" target="_blank">
            YouTube Tutorial 2
          </a>
        </li>
        <li>
          <a href="https://fonts.google.com/selection/embed" target="_blank">
            Google Fonts
          </a>
        </li>
      </ul>

      <div class="image-gallery">
        <img :src="img1" alt="My Photo" />
        <img :src="img2" alt="LinkedIn" />
        <img :src="img3" alt="Broom" />
        <img :src="img4" alt="Experience" />
        <img :src="img5" alt="Education" />
        <img :src="img6" alt="Arrow" />
        <img :src="img7" alt="Checkmark" />
        <img :src="img8" alt="Renato" />
        <img :src="img9" alt="APC" />
        <img :src="img10" alt="Email" />
      </div>
    </main>

    <section id="contact" style="margin-top: 3rem;">
      <h2>Connect with Me</h2>
      <form id="contactForm" @submit.prevent="submitForm">
        <label>Email:</label>
        <input v-model="email" type="email" placeholder="Enter your email" required />

        <label>Message:</label>
        <textarea v-model="message" rows="4" placeholder="Type your message..." required></textarea>

        <button type="submit">Send Message</button>
      </form>

      <p v-if="successMessage" style="color: green; margin-top: 10px;">
        {{ successMessage }}
      </p>
    </section>

    <footer>
      <p>&copy; 2025 Mark Lyster Marabi</p>
    </footer>
  </div>
</template>

<style scoped>
form {
  max-width: 500px;
  margin: 2rem auto;
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0,0,0,0.1);
}
input, textarea {
  width: 100%;
  padding: 0.8rem;
  margin-bottom: 1rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-size: 1rem;
}
button {
  width: 100%;
  padding: 1rem;
  background-color: #ff3333;
  color: white;
  border: none;
  border-radius: 5px;
  font-weight: 600;
  cursor: pointer;
}
button:hover {
  background-color: #cc0000;
}
.image-gallery {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 2rem;
}
.image-gallery img {
  width: 150px;
  height: auto;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.2);
}
</style>
