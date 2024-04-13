<template>
  <NavBar />
      <div class="row">
        <div class="col-3">
          <UserProfileInfo @follow="follow" @unfollow="unfollow" :user="user" />
          <UserProfileWrite @post_a_post="post_a_post" />
        </div>
        <div class="col-9">
          <UserProfilePosts :posts="posts" />
        </div>
      </div>
</template>

<script>
import UserProfileInfo from '../components/UserProfileInfo';
import UserProfilePosts from '../components/UserProfilePosts';
import UserProfileWrite from '../components/UserProfileWrite';
import 'bootstrap/dist/css/bootstrap.css';
import 'bootstrap/dist/js/bootstrap';
import NavBar from '@/components/NavBar';
import { reactive } from 'vue';

export default {
  name: 'UserList',
  components: {
      UserProfileInfo,
      UserProfilePosts,
    UserProfileWrite,
    NavBar
  },
  setup() {
    const user = reactive({
      id: 1,
      username: "yanxuecan",
      lastName: "Yan",
      firstName: "Xuecan",
      followerCount: 0,
      is_followed: false,
    });

    const posts = reactive({
      count: 3,
      posts: [
        {
          id: 1,
          userId: 1,
          content: "今天上了web课真开心",
        },
        {
          id: 2,
          userId: 1,
          content: "今天上了算法课，更开心了",
        },
        {
          id: 3,
          userId: 1,
          content: "今天上了acwing ，开心极了",
        },
      ]
    });

    const follow = () => {
      if (user.is_followed) return;
      user.is_followed = true;
      user.followerCount ++ ;
    };

    const unfollow = () => {
      if (!user.is_followed) return;
      user.is_followed = false;
      user.followerCount -- ;
    };

    const post_a_post = (content) => {
      posts.count ++ ;
      posts.posts.unshift({
        id: posts.count,
        userId: 1,
        content: content,
      })
    };

    return {
      user,
      follow,
      unfollow,
      posts,
      post_a_post
    }
  }
}
</script>

<style scoped>
</style>