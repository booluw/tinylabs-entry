<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
$background: #E5E5E5;
$baseColor: #2BDA53;
$textColor: #013C61;
$colorFaint: #6A7E8A;
$borderRadius: 5px;
$boxShadow: 0px 7px 15px rgba(43, 218, 83, 0.2);
$border: 1px solid #E6E7EB;
$mainHeader: 36px;
$subHeader: 26px;
$thirdHeader: 22px;
$input: 20px;
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap');
* {
  box-sizing: border-box;
}
body {
  font-family: 'Roboto', sans-serif;
  line-height: 1.6;
  font-size: 16px;
  background-color: $background;//rgba($color: $baseColor, $alpha: .08);
  padding: 0;
  margin: 0;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color:  $textColor;
}
.mobile-flex {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 1rem 0;
}
.flex-container {
  position: relative;
  padding: 1rem;
  &--nopadding {
    padding: 0;
  }
  &--mobile-column {
    flex-direction: column;
    padding: 0;
    margin: 0;
    justify-content: flex-start;
    align-items: flex-start;
  }
  .flex__mobile-hidden {
    display: none;
  }
  .flex__main-footer {
    margin: 3rem 0 0;
  }
}
a {
  color: $baseColor;
  text-decoration: none;
}
.paragraph {
  color: $colorFaint;
  padding: 0;
  margin: 1rem 0;
  &--white {
    color: white;
    margin: 0;
  }
}
.heading {
  padding: 0;
  margin: 1rem 0;
  font-size: 34px;
  &--left {
    text-align: left;
  }
  &--main {
    font-size: $mainHeader;
  }
  &--small {
    font-size: 18px;
    font-weight: 500;
    margin: 0;
    padding: 0;
  }
  &-group {
    margin: 2.5rem 0;
  }
}
.my-form {
  background-color: white;
  padding: 1.5rem 2rem;
  border-radius: $borderRadius;
  box-shadow: 0px 20px 50px #EAEEE9;
  .btn {
    margin: 4rem 0 0;
    width: 100%;
  }
}
.input-group {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: flex-start;
  margin: .5rem 0 1.5rem;
  width: 100%!important;
  &__sub-group {
    display: flex;
    justify-content: space-between;
    align-items: stretch;
    padding: .7rem 0;
    border-bottom: $border;
    width: 100%;
    transition: .2s ease-in;
    background-color: white;
    &--border {
      border: 1px solid rgba(106, 126, 138, 0.4);
      .input-group__input {
        font-weight: normal;
        font-size: 16px;
      }
    }
    &:focus-within {
      border-color: $baseColor;
    }
  }
  &__label {
    font-size: 12px;
    color: $colorFaint;
  }
  &__input {
    border: none;
    outline: none;
    font-size: 14px;
    color: $textColor;
    flex-basis: 90%;
  }
}
.padded {
  margin: 1rem 0 0;
}
.radio {
  background-color: white;
  content: '';
  padding: .01rem .5rem;
  margin: 1rem .5rem;
  border-radius: 50%;
  position: relative;
  z-index: 1;
  cursor: pointer;
  &--active {
    background-color: $baseColor;
    &::before {
      z-index: -1;
      position: absolute;
      top: -.3rem;
      left: -.3rem;
      width: 100%;
      height: 100%;
      content: '';
      background-color: transparent;
      padding: .2rem;
      border-radius: 50%;
      border: .1rem solid $baseColor;
    }
  }
}

.btn {
  background-color: $baseColor;
  outline: none;
  border: 0;
  color: white;
  padding: .7rem 1.4rem;
  display: flex;
  justify-content: center;
  align-items: center;
  border-radius: $borderRadius;
  font-weight: normal;
  font-size: 18px;
  transition: .3s ease-in;
  cursor: pointer;
  &--primary {
    padding: .7rem 1rem;
    transform: translateY(-5px);
  }
  &:active {
    transform: translateY(0);
  }
  &:hover {
    opacity: .8;
  }
}
@media (min-width: 1200px) {
  .my-form {
    margin: 0 4rem;
    text-align: right;
    text-align: right;
    .btn {
      display: inline-flex;
      padding: 1rem 3rem;
      width: 47%;
      margin: 2.5rem 0 0;
    }
  }
  .heading-group {
    text-align: left;
    margin: 2rem 4rem;
  }
  .heading {
    font-size: 34px;
    &--small {
      font-size: 18px;
    }
  }
  .input-group {
    &__input {
      font-size: 20px;
    }
    &__label {
      font-size: 16px;
    }
  }
  .btn {
    font-size: 18px;
    padding: 1rem 3rem;
  }
  .flex-container {
    box-sizing: border-box;
    display: flex;
    padding: 0;
    align-items: stretch;
    justify-content: stretch;  
    &--mobile-column {
      flex-direction: row;
      justify-content: stretch;
      align-items: stretch;
      .input-group__sub-group {
        margin: 0 0 0 2rem;
      }
    }
    &--padded {
      padding: 1.2rem 0;
    }
    &--space-btw {
      justify-content: space-between;
     .input-group {
       flex-basis: 47%;
      }
    }
    &--align-center {
      align-items: center;
    }
    .flex__mobile-hidden {
      box-sizing: border-box;
      display: block;
      width: 35%;
      background: linear-gradient( transparent 30%, rgba(0,0,0,.9)), url('assets/login.png') no-repeat;
      background-size: 100% 100%;
      background-origin: padding-box;
      display: flex;
      justify-content: flex-end;
      align-items: center;
      flex-direction: column;
      padding: 0 3rem 2rem;
      color: white;
    }
    .flex__main {
      box-sizing: border-box;
      width: 65%;
      padding: .8rem 2rem;
      &-footer {
        justify-content: space-between;
        padding: 0;
        margin: 3rem 0 0;
      }
    }
  }  
  .mobile-flex {margin: 0;}
}
</style>
