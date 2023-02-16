<script>
export default {
  data: function () {
    // let items = [];
    // for (let text = 0; text < 20; text++) {
    //   items.push({ id: `Test msg ${text}` });
    // }
    return {
      currentItem: 1,
      items: [
        { id: 1, text: "Politics" },
        { id: 2, text: "Sport" },
        { id: 3, text: "Climate changes" },
        { id: 4, text: "Coronavirus" },
        { id: 5, text: "Climate changes" },
        { id: 6, text: "Climate changes" },
        { id: 7, text: "Climate changes" },
        { id: 8, text: "Climate changes" },
        { id: 9, text: "Climate changes" },
        { id: 10, text: "Climate changes" },
        { id: 11, text: "Climate changes" },
        { id: 12, text: "Climate changes" },
        { id: 13, text: "Climate changes" },
        { id: 14, text: "Climate changes" },
        { id: 15, text: "Climate changes" },
        { id: 16, text: "Climate changes" },
        { id: 17, text: "Climate changes" },
      ],
    };
  },
  mounted() {
    document.addEventListener("click", this.nextItem);
  },
  methods: {
    nextItem(event) {
      if (event.click && this.currentItem > 1) {
        this.currentItem--;
      } else if (event.click && this.currentItem < 3) {
        this.currentItem++;
      }
    },
  },
};
</script>

<template>
  <nav class="nav">
    <div class="nav__burger">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <p class="nav__navigation">Menu</p>
    <button type="button" class="left-arrow" @click="topFunction"></button>
    <ul class="scrollmenu">
      <li
        v-for="item in items"
        :key="item.id"
        :class="{ 'active-item': currentItem === item.id }"
      >
        {{ item.text }}
      </li>
    </ul>
    <button type="button" class="right-arrow"></button>

    <font-awesome-icon icon="search" />
  </nav>
</template>

<style>
.search-box {
  width: fit-content;
  height: fit-content;
  position: relative;
}

button {
  border: none;
  cursor: pointer;
}
.nav__burger {
  padding-right: 20px;
}
.nav__navigation {
  margin-right: 23px;
}
span {
  display: block;
  flex-direction: column;
  width: 20px;
  height: 1px;
  margin-bottom: 5px;
  position: relative;

  background: #cdcdcd;
  border-radius: 3px;

  z-index: 1;

  transform-origin: 4px 0px;

  transition: transform 0.5s cubic-bezier(0.77, 0.2, 0.05, 1),
    background 0.5s cubic-bezier(0.77, 0.2, 0.05, 1), opacity 0.55s ease;
}

span:first-child {
  transform-origin: 0% 0%;
}

span:last-child {
  margin-bottom: 0px;
}
.nav {
  display: flex;
  padding: 20px 30px;
  align-items: center;
  background: rgba(31, 30, 28, 1);
}

.left-arrow:before {
  content: "\003C";
  color: #ffff;
}
.right-arrow:before {
  content: ">";
  color: #ffff;
}
.left-arrow {
  border-left: 1px dotted #fff;
  box-shadow: 0 0 30px rgba(0, 0, 0, 0.75);
  clip-path: inset(0px -30px 0px 0px);
  height: 30px;
  --tw-bg-opacity: 1;
  background: rgba(31, 30, 28, var(--tw-bg-opacity));
  float: left;
  z-index: 3;
  text-align: center;
  width: 60px;
}

.left-arrow p {
  color: #fff;
  font-size: 18px;
}

.right-arrow {
  background: rgba(31, 30, 28, 1);
  border-right: 1px dotted #fff;
  float: left;
  height: 30px;
  text-align: center;
  width: 60px;
  box-shadow: 0 0 30px rgba(0, 0, 0, 0.75);
  clip-path: inset(0px 0px 0px -30px);
  margin-right: 23px;
}

.right-arrow p {
  color: #fff;
  font-size: 18px;
}
.scrollmenu {
  padding: unset;
  display: flex;
  align-items: center;
  font-size: 0;
  overflow: hidden;
  width: 100%;
  white-space: nowrap;
  -webkit-overflow-scrolling: touch;
  -ms-overflow-style: -ms-autohiding-scrollbar;
}
li {
  display: flex;
  color: #fff;
  font-size: 15px;
  padding-left: 10px;
  padding-right: 10px;
  list-style: none;
  text-align: center;
  z-index: 1;
}
li a {
  background: rgba(31, 30, 28, 1);
  color: #fff;
  display: block;
  height: 100%;
  text-decoration: none;
  width: 100%;
}

li a:hover {
  background: rgb(76, 78, 80);
}
</style>
