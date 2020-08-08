1<template>
  <section class="flex-container">
    <div class="flex__mobile-hidden">
      <h3 class="heading--small" style="margin: 1rem 0;">No Hazzles</h3>
      <p class="paragraph paragraph--white">
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quas, reprehenderit.
      </p>
      <div class="padded">
        <span class="radio radio--active"></span>
        <span class="radio"></span>
      </div>
    </div>
    <div class="flex__main">
      <div class="heading-group">
        <h1 class="heading">Create your free account</h1>
        <h3 class="heading--small">Already registered? <a href="#">Sign in</a></h3>
      </div>
      <form class="my-form" @submit.prevent="submitForm()">
        <div class="flex-container flex-container--nopadding flex-container--space-btw">
          <div class="input-group">
            <label for="fname" class="input-group__label">First Name</label>
            <div class="input-group__sub-group">
              <input type="text" id="fname" placeholder="Your First Name" class="input-group__input" />
              <label for="fname">
                <svg width="16" height="18" viewBox="0 0 16 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M15 16.75V15C15 13.067 13.433 11.5 11.5 11.5H4.5C2.567 11.5 1 13.067 1 15V16.75" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M8 8C9.933 8 11.5 6.433 11.5 4.5C11.5 2.567 9.933 1 8 1C6.067 1 4.5 2.567 4.5 4.5C4.5 6.433 6.067 8 8 8Z" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </label>
            </div>
          </div>
          <div class="input-group">
            <label for="lname" class="input-group__label">Last Name</label>
            <div class="input-group__sub-group">
              <input type="text" id="lname" placeholder="Your Last Name" class="input-group__input" />
              <label for="lname">
                <svg width="16" height="18" viewBox="0 0 16 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M15 16.75V15C15 13.067 13.433 11.5 11.5 11.5H4.5C2.567 11.5 1 13.067 1 15V16.75" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                  <path fill-rule="evenodd" clip-rule="evenodd" d="M8 8C9.933 8 11.5 6.433 11.5 4.5C11.5 2.567 9.933 1 8 1C6.067 1 4.5 2.567 4.5 4.5C4.5 6.433 6.067 8 8 8Z" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </label>
            </div>
          </div>
        </div>
        <div class="input-group">
          <label for="email" class="input-group__label">Email</label>
          <div class="input-group__sub-group">
            <input type="email" id="email" placeholder="Your Email Address" class="input-group__input" />
            <label for="email">
              <svg width="17" height="17" viewBox="0 0 17 17" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M8.14328 11.0002C9.72123 11.0002 11.0004 9.72105 11.0004 8.14309C11.0004 6.56514 9.72123 5.28595 8.14328 5.28595C6.56532 5.28595 5.28613 6.56514 5.28613 8.14309C5.28613 9.72105 6.56532 11.0002 8.14328 11.0002Z" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                <path d="M11.0004 5.28596V8.85739C11.0004 10.0409 11.9598 11.0003 13.1433 11.0003C14.3267 11.0003 15.2861 10.0409 15.2861 8.85739V8.14311C15.2859 4.82375 12.9991 1.94198 9.76659 1.18761C6.5341 0.433237 3.20791 2.0051 1.73846 4.98148C0.269016 7.95786 1.0436 11.5543 3.60801 13.6619C6.17243 15.7695 9.85078 15.8327 12.4861 13.8145" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </label>
          </div>
        </div>
        <div class="input-group">
          <label for="password" class="input-group__label">Password</label>
          <div class="input-group__sub-group">
            <input type="password" id="password" placeholder="Password" class="input-group__input"/>
            <label for="password">
              <svg width="20" height="15" viewBox="0 0 20 15" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M1 7.54545C1 7.54545 4.27273 1 10 1C15.7273 1 19 7.54545 19 7.54545C19 7.54545 15.7273 14.0909 10 14.0909C4.27273 14.0909 1 7.54545 1 7.54545Z" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
                <path fill-rule="evenodd" clip-rule="evenodd" d="M9.99996 9.99997C11.3556 9.99997 12.4545 8.90103 12.4545 7.54543C12.4545 6.18982 11.3556 5.09088 9.99996 5.09088C8.64435 5.09088 7.54541 6.18982 7.54541 7.54543C7.54541 8.90103 8.64435 9.99997 9.99996 9.99997Z" stroke="#013C61" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
            </label>
          </div>
        </div>
        <button class="btn btn--primary">Continue</button>
      </form>
      <div class="flex-container flex__main-footer">
        <p class="paragraph">
          By signing up, you agree to our <a href="#">Terms</a> and <a href="#">Privacy and Policy</a>
        </p>
        <p class="paragraph">&copy; 2019 Tinylabs. All rights reserved.</p>
      </div>
    </div>
  </section>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Home',
  methods: {
    submitForm: function() {
      this.$router.push('/dashboard')
    }
  }
}
</script>
