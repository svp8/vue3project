<template>
  <div class="header">
    <h1 class="header__title">Base</h1>
    <nav class="header__nav">
      <a class="link header__nav__item">Profile</a>

      <div v-if="isLoggedIn" class="header__nav__item test">
        <img @click="openUserMenu" class="avatar" src="../assets/logo.png" />
        <div v-if="isUserMenuOpen" class="popup">
          <ul class="popup_box">
            <li class="popup_box__row">
              <span>Settings</span>
            </li>
            <li @click="signOut" class="popup_box__row">
              <span>Sign out</span>
            </li>
          </ul>
        </div>
      </div>
      <div v-else class="header__nav__item">
        <button @click="signOut" class="button header__nav__item">
          Sign in
        </button>
        <button class="button button-up header__nav__item">
          Sign up
        </button>
      </div>
    </nav>
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const isUserMenuOpen = ref(true);
    const isLoggedIn = ref(true);
    const openUserMenu = () => {
      isUserMenuOpen.value = !isUserMenuOpen.value;
    };
    const signOut = () => {
      isLoggedIn.value = !isLoggedIn.value;
    };
    return {
      isUserMenuOpen,
      isLoggedIn,
      openUserMenu,
      signOut,
    };
  },
};
</script>

<style lang="scss" scoped>
.test {
  display: flex;
  align-items: center;
}
.header {
  display: flex;
  padding: 7px;
  align-items: center;
  justify-content: space-between;
  &__title {
    font-weight: 600;
  }
  &__nav {
    color: rgb(4, 12, 12);
    display: flex;
    align-items: center;
    &__item {
      margin-right: 7px;
      cursor: pointer;
    }
  }
}
.popup {
  position: absolute;

  width: 200px;
  background: rgb(182, 112, 247);
  top: 55px;
  right: 10px;
  border-radius: 3px;
  &_box {
    display: flex;
    flex-direction: column;
    text-align: left;
    &__row {
      padding: 14px 10px;
    }
  }
}
.avatar {
  position: relative;
  border: 0.5px solid rgb(174, 82, 236);
  border-radius: 19px;
  object-fit: cover;
  width: 35px;
}
.link {
  font-weight: 500;
  font-size: 18px;
  cursor: pointer;
}
.button{
  border: 0.5px solid purple;
  font-size: 16px;
  &-up{
    background-color:rgb(182, 112, 247);
  }
}
</style>