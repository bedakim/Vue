<template>
  <section class="recipes">
    <div id="Post">
      <div class="search-wrapper">
        <input type="text" v-model="data.search" placeholder="Search title..">
        <label>Search title:{{data.search}}</label>
      </div>
      <Recipe
        v-for="post in computed.filteredList"
        :key="post.id"
        :thumbnail="post.img"
        :title="post.title"
        :link="post.link"
        :previewText="post.author"
      />
    </div>
  </section>
</template>

<script>
import Recipe from "@/components/Recipe";
import { Promise, resolve, reject } from "q";
class Post {
  constructor(id, title, link, author, img) {
    this.id = id;
    this.title = title;
    this.link = link;
    this.author = author;
    this.img = img;
  }
}
export default {
  components: {
    Recipe
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          el: "#Post",
          data: {
            search: "",
            postList: [
              new Post(
                "1",
                "Angular.js",
                "https://angularjs.org/",
                "Sam",
                "https://angularjs.org/img/ng-logo.png"
              ),
              new Post(
                "2",
                "Ember.js",
                "http://emberjs.com/",
                "Rachel",
                "http://www.gravatar.com/avatar/0cf15665a9146ba852bf042b0652780a?s=200"
              ),
              new Post(
                "3",
                "Meteor.js",
                "https://www.meteor.com/",
                "Chris",
                "http://hacktivist.in/introduction-to-nodejs-mongodb-meteor/img/meteor.png"
              )
            ]
          },
          computed: {
            filteredList() {
              return this.postList.filter(post => {
                return post.title
                  .toLowerCase()
                  .includes(this.search.toLowerCase());
                console.log("tk", data.search);
              });
              console.log("tka", data.search);
            }
          }
        });
      }, 1500);
    });
  }
};
</script>



<style lang="scss">
// html,
// body {
//   display: flex;
//   align-items: center;
//   justify-content: center;
//   flex-direction: column;
//   margin-top: 16px;
//   margin-bottom: 16px;
// }

// div#app {
//   display: flex;
//   align-items: center;
//   justify-content: center;
//   flex-direction: column;

//   .search-wrapper {
//     position: relative;
//     label {
//       position: absolute;
//       font-size: 12px;
//       color: rgba(0, 0, 0, 0.5);
//       top: 8px;
//       left: 12px;
//       z-index: -1;
//       transition: 0.15s all ease-in-out;
//     }
//     input {
//       padding: 4px 12px;
//       color: rgba(0, 0, 0, 0.7);
//       border: 1px solid rgba(0, 0, 0, 0.12);
//       transition: 0.15s all ease-in-out;
//       background: white;
//       &:focus {
//         outline: none;
//         transform: scale(1.05);
//         & + label {
//           font-size: 10px;
//           transform: translateY(-24px) translateX(-12px);
//         }
//       }
//       &::-webkit-input-placeholder {
//         font-size: 12px;
//         color: rgba(0, 0, 0, 0.5);
//         font-weight: 100;
//       }
//     }
//   }

//   .wrapper {
//     display: flex;
//     max-width: 444px;
//     flex-wrap: wrap;
//     padding-top: 12px;
//   }

//   .card {
//     box-shadow: rgba(0, 0, 0, 0.117647) 0px 1px 6px,
//       rgba(0, 0, 0, 0.117647) 0px 1px 4px;
//     max-width: 124px;
//     margin: 12px;
//     transition: 0.15s all ease-in-out;
//     &:hover {
//       transform: scale(1.1);
//     }
//     a {
//       text-decoration: none;
//       padding: 12px;
//       color: #03a9f4;
//       font-size: 24px;
//       display: flex;
//       flex-direction: column;
//       align-items: center;
//       img {
//         height: 100px;
//       }
//       small {
//         font-size: 10px;
//         padding: 4px;
//       }
//     }
//   }

//   .hotpink {
//     background: hotpink;
//   }

//   .green {
//     background: green;
//   }

//   .box {
//     width: 100px;
//     height: 100px;
//     border: 1px solid rgba(0, 0, 0, 0.12);
//   }
// }
// .search-wrapper {
//   display: flex;
//   position: relative;
//   label {
//     position: absolute;
//     font-size: 12px;
//     color: rgba(0, 0, 0, 0.5);
//     top: 8px;
//     left: 12px;
//     z-index: -1;
//     transition: 0.15s all ease-in-out;
//   }
//   input {
//     padding: 4px 12px;
//     color: rgba(0, 0, 0, 0.7);
//     border: 1px solid rgba(0, 0, 0, 0.12);
//     transition: 0.15s all ease-in-out;
//     background: white;
//     &:focus {
//       outline: none;
//       transform: scale(1.05);
//       & + label {
//         font-size: 10px;
//         transform: translateY(-24px) translateX(-12px);
//       }
//     }
//     &::-webkit-input-placeholder {
//       font-size: 12px;
//       color: rgba(0, 0, 0, 0.5);
//       font-weight: 100;
//     }
//   }
// }
// .recipes {
//   display: flex;
//   flex-flow: column;
//   justify-content: center;
//   align-items: center;
// }
</style>
