<script setup>
   import { ref, computed } from 'vue';

const name = ref('');
const email = ref('');
const phone = ref('');
const message = ref('');

const isValidEmail = computed(() => {
  const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  return emailPattern.test(email.value);
});

const isValidPhone = computed(() => {
  const phonePattern = /^\d{3}-\d{3}-\d{4}$/;
  return phonePattern.test(phone.value);
});

const errors = ref({
  name: '',
  email: '',
  phone: '',
  message: ''
});

const send = () => {
  validateForm();
  if (!Object.values(errors.value).some(error => error !== '')) {
    // Form submission logic goes here
    alert('Form Submitted!')
    console.log('Form submitted successfully!');
    clearInputs();
  }
};

const validateForm = () => {
  errors.value.name = !name.value ? 'Name is required' : '';
  errors.value.email = !email.value ? 'Email is required' : '';
  errors.value.phone = !phone.value ? 'Phone is required' : '';
  errors.value.message = !message.value ? 'Message is required' : '';
};
const clearInputs = () => {
  name.value = '';
  email.value = '';
  phone.value = '';
  message.value = '';
};
</script>

<template>
    <!-- ============================================ -->
<!--                   Contact                    -->
<!-- ============================================ -->

<section id="contact-1150">
    <div class="cs-container">
        <div class="cs-content">
            <span class="cs-topper">Contact Us</span>
            <h2 class="cs-title">We Love to Hear from Our Happy Customers</h2>
        </div>
        <div class="cs-contact-group">
            <picture class="cs-picture">
                <!--Mobile Image-->
                <source media="(max-width: 600px)" srcset="https://csimg.nyc3.cdn.digitaloceanspaces.com/Images/People/group.jpg">
                <!--Tablet and above Image-->
                <source media="(min-width: 601px)" srcset="https://csimg.nyc3.cdn.digitaloceanspaces.com/Images/People/group.jpg">
                <img loading="lazy" decoding="async" src="https://csimg.nyc3.cdn.digitaloceanspaces.com/Images/People/group.jpg" alt="people" width="630" height="300">
            </picture>
            <p class="cs-contact-text">
                Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellat optio sapiente ex blanditiis enim non dolorum ipsum assumenda, libero nihil harum officia consequuntur aliquid deleniti! Eveniet id a obcaecati iure! 
            </p>
            <ul class="cs-ul">
                <li class="cs-li">
                    <picture class="cs-icon-wrapper">
                        <img aria-hidden="true" src="https://csimg.nyc3.cdn.digitaloceanspaces.com/Icons/mech-phone.svg" alt="phone icon" class="cs-icon" width="40" height="40" decoding="async">
                    </picture>
                    <div class="cs-flex-group">
                        <span class="cs-header">Phone</span>
                        <a href="tel:888-4565-789
                        " class="cs-link">+1 (888) 4565 789
                        </a>
                    </div>
                </li>
                <li class="cs-li">
                    <picture class="cs-icon-wrapper">
                        <img aria-hidden="true" src="https://csimg.nyc3.cdn.digitaloceanspaces.com/Icons/mech-pin.svg" alt="address icon" class="cs-icon" width="40" height="40" decoding="async">
                    </picture>
                    <div class="cs-flex-group">
                        <span class="cs-header">Address</span>
                        <a href="#" class="cs-link">2553 Woodbridge Lane, Boston Ware 120</a>
                    </div>
                </li>
            </ul>
        </div>
        <!--Form-->
        <form @submit.prevent="send" class="cs-form" id="cs-form-1150" method="post">

<label for="name" class="cs-label">Name</label>
<input v-model="name" class="cs-input" type="text" id="name-1150" name="name" placeholder="Name">
<div v-if="errors.name" class="error">{{ errors.name }}</div>

<label for="email" class="cs-label cs-email">Email</label>
<input class="cs-input" type="email" id="email-1150" name="email" placeholder="Email" v-model="email">
<div v-if="errors.email" class="error">{{ errors.email }}</div>
<div v-if="email && !isValidEmail" class="error">Invalid email format</div>

<label for="phone" class="cs-label cs-phone">Phone</label>
<input class="cs-input" type="tel" id="phone-1150" name="phone" placeholder="000-000-0000" v-model="phone">
<div v-if="errors.phone" class="error">{{ errors.phone }}</div>
<div v-if="phone && !isValidPhone" class="error">Invalid phone number format</div>

<label for="message" class="cs-label">Message</label>
<textarea class="cs-input cs-textarea" name="message" id="message-1150" placeholder="Write message..." v-model="message"></textarea>
<div v-if="errors.message" class="error">{{ errors.message }}</div>

<button class="cs-button-solid cs-submit" type="submit">Send</button>
</form>
        <!--Bounce Graphic-->
        <img class="cs-graphic cs-graphic1" loading="lazy" decoding="async" src="https://csimg.nyc3.cdn.digitaloceanspaces.com/Images/MISC/bounce.svg" alt="bounce" width="208" height="124">
        <!--Coin Graphic-->
        <img class="cs-graphic cs-graphic2" loading="lazy" decoding="async" src="https://csimg.nyc3.cdn.digitaloceanspaces.com/Images/MISC/coin.svg" alt="bounce" width="205" height="161">
    </div>
</section>
                                
</template>

<style scoped>
    /*-- -------------------------- -->
<---          Contact           -->
<--- -------------------------- -*/

.error {
  color: red;
  margin-top: 5px;
}
/* Mobile - 360px */
@media only screen and (min-width: 0rem) {
    #contact-1150 {
        padding: var(--sectionPadding);
        background-color: #f7f7f7;
        position: relative;
        z-index: 1;
    }
    #contact-1150 .cs-container {
        width: 100%;
        /* changes to 1280px at desktop */
        max-width: 44rem;
        margin: auto;
        display: flex;
        justify-content: center;
        align-items: stretch;
        flex-direction: column;
        column-gap: auto;
        /* 48px - 80px */
        row-gap: clamp(3rem, 6vw, 5rem);
        position: relative;
    }
    #contact-1150 .cs-content {
        /* set text align to left if content needs to be left aligned */
        text-align: center;
        width: 100%;
        display: flex;
        flex-direction: column;
        /* centers content horizontally, set to flex-start to left align */
        align-items: center;
    }

    #contact-1150 .cs-topper {
        color: #767676;
    }
    #contact-1150 .cs-title {
        max-width: 23ch;
        margin: 0;
    }
    #contact-1150 .cs-picture {
        width: 100%;
        /* 240px - 300px */
        height: clamp(15rem, 35vw, 18.75rem);
        margin: 0 0 1.5rem;
        border-radius: 1.5rem;
        /* clips image corners */
        overflow: hidden;
        display: block;
        position: relative;
    }
    #contact-1150 .cs-picture img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        position: absolute;
        top: 0;
        left: 0;
    }
    #contact-1150 .cs-contact-text {
        font-size: 1rem;
        line-height: 1.5em;
        text-align: left;
        margin: 0 0 1.5rem;
        color: var(--bodyTextColor);
    }
    #contact-1150 .cs-ul {
        width: 100%;
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        gap: 1.5rem;
        position: relative;
    }
    #contact-1150 .cs-li {
        list-style: none;
        display: flex;
        justify-content: flex-start;
        align-items: flex-start;
        gap: 1.25rem;
    }
    #contact-1150 .cs-li:hover .cs-icon-wrapper {
        transform: scale(1.1);
    }
    #contact-1150 .cs-header {
        font-size: 1.25rem;
        font-weight: 700;
        line-height: 1.2em;
        margin-bottom: 0.75rem;
        color: var(--headerColor);
        display: block;
    }
    #contact-1150 .cs-link {
        font-size: 1rem;
        line-height: 1.5em;
        text-decoration: none;
        color: #767676;
        display: block;
        position: relative;
    }
    #contact-1150 .cs-link:hover {
        text-decoration: underline;
    }
    #contact-1150 .cs-icon-wrapper {
        width: 3.75rem;
        height: 3.75rem;
        margin: 0;
        border-radius: 50%;
        border: 1px solid #bababa;
        display: flex;
        justify-content: center;
        align-items: center;
        /* prevents flexbox from squishing it */
        flex: none;
        transition: transform 0.3s;
    }
    #contact-1150 .cs-icon {
        width: 1.5rem;
        height: auto;
        display: block;
    }
    #contact-1150 .cs-form {
        width: 100%;
        /* 24px - 48px top and bottom */
        /* 16px - 32px left and right */
        padding: clamp(1.5rem, 5.18vw, 3rem) clamp(1rem, 4vw, 2rem);
        /* prevents flexbox from affecting height and width */
        box-sizing: border-box;
        background-color: #fff;
        border-radius: 1rem;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        align-items: center;
        gap: 0.75rem;
    }
    #contact-1150 .cs-label {
        /* 14px - 16px */
        font-size: clamp(0.875rem, 1.5vw, 1rem);
        width: 100%;
        color: var(--headerColor);
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        gap: 0.25rem;
    }
    #contact-1150 .cs-input {
        font-size: 1rem;
        width: 100%;
        height: 3.5rem;
        padding: 0;
        padding-left: 1.5rem;
        color: var(--headerColor);
        background-color: #f7f7f7;
        border-radius: 0.5rem;
        border: none;
        /* prevents padding from adding to height and width */
        box-sizing: border-box;
    }
    #contact-1150 .cs-input::placeholder {
        color: #7d799c;
        opacity: 0.6;
    }
    #contact-1150 .cs-textarea {
        min-height: 7.5rem;
        padding-top: 1.5rem;
        margin-bottom: 0.75rem;
        font-family: inherit;
    }
    #contact-1150 .cs-button-solid {
        font-size: 1rem;
        /* 46px - 56px */
        line-height: clamp(2.875em, 5.5vw, 3.5em);
        text-decoration: none;
        font-weight: 700;
        text-align: center;
        margin: 0;
        color: #1a1a1a;
        border: none;
        min-width: 9.375rem;
        padding: 0 1.5rem;
        background-color: var(--secondary);
        border-radius: 0.25rem;
        overflow: hidden;
        display: inline-block;
        position: relative;
        z-index: 1;
        /* prevents padding from adding to the width */
        box-sizing: border-box;
        transition: color 0.3s;
    }
    #contact-1150 .cs-button-solid:before {
        content: "";
        position: absolute;
        height: 100%;
        width: 0%;
        background: #000;
        opacity: 1;
        top: 0;
        left: 0;
        z-index: -1;
        border-radius: 0.25rem;
        transition: width 0.3s;
    }
    #contact-1150 .cs-button-solid:hover {
        color: #fff;
    }
    #contact-1150 .cs-button-solid:hover:before {
        width: 100%;
    }
    #contact-1150 .cs-submit {
        width: 100%;
        min-width: 17.6875rem;
        border-radius: 0.5rem;
    }
    #contact-1150 .cs-submit:hover {
        cursor: pointer;
    }
    #contact-1150 .cs-graphic {
        display: none;
    }
    #contact-1150 .cs-graphic1 {
        width: 13rem;
        height: auto;
        position: absolute;
        left: -7.5rem;
        top: 8.625rem;
    }
    #contact-1150 .cs-graphic2 {
        width: 12.8125rem;
        height: auto;
        position: absolute;
        right: -9.75rem;
        top: 0.5rem;
    }
}
/* Desktop - 1024px */
@media only screen and (min-width: 64rem) {
    #contact-1150 .cs-container {
        max-width: 80rem;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-between;
    }
    #contact-1150 .cs-contact-group {
        width: 50%;
        max-width: 39.375rem;
    }
    #contact-1150 .cs-form {
        width: 46%;
        max-width: 36.125rem;
    }
    #contact-1150 .cs-submit {
        width: auto;
    }
}
/* Large Desktop - 1500px */
@media only screen and (min-width: 93.75rem) {
    #contact-1150 .cs-graphic {
        display: block;
    }
}

                                
</style>