<template>
  <div>
    <Navbar />
    <div class="hello row">
      <div class="col s10 maxHeight">
        <div class="increaseHeight">
          <div
            class="row dFlex"
            v-for="(n,index) in posts"
            :key="index"
            :class="{flexEnd: check(index)}"
          >
            <img
              src="https://images.unsplash.com/photo-1569767346430-22119296c052?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=500&q=60"
              :class="{right: check(n)}"
            />
            <div class="card maxW">
              <div class="card-stacked">
                <div class="card-content">
                  <p>{{n.message}}</p>
                  <hr />
                  <p>{{calculateTime(n.time,index)}}</p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <Create />
      </div>
      <div class="col s2 noPaddingRight">
        <Online />
      </div>
    </div>
  </div>
</template>

<script>
import Online from "@/components/Online.vue";
import Create from "@/components/CreatePost.vue";
import Navbar from "@/components/NavBar.vue";
export default {
  name: "posts",
  components: {
    Online,
    Create,
    Navbar
  },
  data() {
    return {
      posts: [
        {
          displayName: "asd",
          message: "hello there",
          time: 1569235599431
        },
        {
          displayName: "there",
          message: "general",
          time: 1569821610409
        }
      ],
      time: new Date().getTime()
    };
  },
  methods: {
    check(n) {
      if (n % 2 == 0) return true;
      else return false;
    },
    calculateTime(t, i) {
      let date = new Date().getTime();
      let temp = date - t;
      if (temp < 86400000) {
        if (temp < 3600000) {
          return new Date(temp).getMinutes() + " minutes ago";
        } else {
          let msg = "";
          let hour = new Date().getHours() - new Date(t).getHours();
          if (hour == 1)
            return new Date().getHours() - new Date(t).getHours() + " hour ago";
          else {
             
            if (new Date(t).getHours() > 12)
              return (
                24 -
                new Date(t).getHours() +
                new Date().getHours() +
                " hours ago"
              );
            else return new Date().getHours() - new Date(t).getHours() + " hours ago";
          }
        }
      }
      if (temp < 2628000000) {
       if(new Date().getMonth() < new Date(t).getMonth() )
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.right {
  order: 1;
}
.flexEnd {
  justify-content: flex-end;
}
.maxW {
  margin-left: 10px;
  margin-right: 10px;
  max-width: 10%;
  border-radius: 20%;
  background: rgb(249, 247, 247);
}

img {
  margin-top: auto;
  margin-bottom: 15px;
  border-radius: 50%;
  width: 70px;
  height: 70px;
}
.dFlex {
  display: flex;
  padding: 0 20px;
}
.increaseHeight {
  height: 95%;
  overflow-y: auto;
  overflow-x: hidden;
}
.hello {
  margin-bottom: 0;
  height: calc(100vh - 64px);
}
.noPaddingRight {
  padding: 0;
}
.maxHeight {
  height: calc(100vh - 64px);
  padding: 0;
}
</style>
