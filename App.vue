<template>
  <view class="container">
    <app-loading v-if="!isAppReady"> </app-loading>
    <app-navigation v-if="isAppReady"></app-navigation>
  </view>
</template>

<script>
import React from "react";
import Vue from "vue-native-core";
import { VueNativeBase } from "native-base";

import { AppLoading } from "expo";

import { StackNavigator, DrawerNavigator } from "vue-native-router"
import MainScreen from './Main';
import ReflectionsListScreen from './components/ReflectionsList';
import ViewReflectionScreen from './components/ViewReflection';

import SideBarScreen from './components/SideBar';
import CreateReflectionScreen from './components/CreateReflection';
import AboutScreen from './components/About';
import FeedbackScreen from './components/Feedback';

// registering all native-base components to the global scope of the Vue
Vue.use(VueNativeBase);
const Drawer = DrawerNavigator(
  {
    CreateReflection: CreateReflectionScreen,
    Main: ReflectionsListScreen,
    About: AboutScreen,
    Feedback: FeedbackScreen
  },
  {
    initialRouteName: "Main",
    contentOptions: {
      activeTintColor: "#e91e63"
    },
    contentComponent: props => {
      return <SideBarScreen {...props} />;
    }
  }
);

const AppNavigation = StackNavigator(
  {
    Drawer: { screen: Drawer },
    ViewReflection: ViewReflectionScreen
  },
  {
    initialRouteName: "Drawer"
  }
)
export default {
  components: { AppNavigation, AppLoading },
  data: function() {
    return {
      isAppReady: false
    };
  },
  created: function() {
    this.loadFonts();
  },
  methods: {
    loadFonts: async function() {
      try {
        this.isAppReady = false;
        await Expo.Font.loadAsync({
          Roboto: require("native-base/Fonts/Roboto.ttf"),
          Roboto_medium: require("native-base/Fonts/Roboto_medium.ttf"),
          Ionicons: require("@expo/vector-icons/fonts/Ionicons.ttf")
        });
        this.isAppReady = true;
      } catch (error) {
        console.log("some error occured", error);
        this.isAppReady = true;
      }
    }
  }
}

// import firebase from 'firebase';
// firebase.initializeApp({
//   apiKey: "AIzaSyCHwzqDgzuQa3Ewj3Spr7oAj4fwa8ikmMI",
//   authDomain: "reflection-app-c14fb.firebaseapp.com",
//   databaseURL: "https://reflection-app-c14fb.firebaseio.com",
//   projectId: "reflection-app-c14fb",
//   storageBucket: "reflection-app-c14fb.appspot.com",
//   messagingSenderId: "487865059549"
// });


</script>
<style>
  .container {
    flex: 1;
  }
</style>
