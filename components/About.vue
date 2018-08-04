<template>
  <nb-container>
    <nb-header>
      <nb-left>
        <nb-button transparent :on-press="() => navigation.goBack()">
          <nb-icon :name="'arrow-back'" />
        </nb-button>
      </nb-left>
      <nb-body>
        <nb-title>About</nb-title>
      </nb-body>
      <nb-right/>
    </nb-header>
    <nb-content>
      <view>
        <nb-h1> Daily Reflection App</nb-h1>
        <nb-text>Develop By TailorNG</nb-text>
        <nb-text>tailorngtech@gmail.com</nb-text>
      </view>
        <nb-button transparent :on-press="() => googleLogin()">
          <nb-text>Google SignIn</nb-text>
        </nb-button>
    </nb-content>
  </nb-container>
</template>

<script>
import firebase from 'firebase';
firebase.initializeApp({
  apiKey: "AIzaSyCHwzqDgzuQa3Ewj3Spr7oAj4fwa8ikmMI",
  authDomain: "reflection-app-c14fb.firebaseapp.com",
  databaseURL: "https://reflection-app-c14fb.firebaseio.com",
  projectId: "reflection-app-c14fb",
  storageBucket: "reflection-app-c14fb.appspot.com",
  messagingSenderId: "487865059549"
});
export default {
  props: {
    navigation: {
      type: Object
    }
  },
  mounted() {
    return firebase.database()
      .ref('/reflections')
      .once('value')
      .then(function(snapshot) {
        console.log(snapshot.val());
      })
      .catch(function(error) {
        console.log(error);
      });
  },
  methods: {
    googleLogin() {

    }
  }
}
</script>
