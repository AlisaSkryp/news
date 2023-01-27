<script></script>
<template>
  <nav class="nav">
    <div class="nav__burger">
      <span></span>
      <span></span>
      <span></span>
    </div>

    <p>Menu</p>
    <button type="button" class="left-arrow"></button>
    <ul>
      <li class="item1"><a href="#">Life</a></li>
      <li><a href="#">Culture</a></li>
      <li><a href="#">Sport</a></li>
      <li><a href="#">Culture</a></li>
      <li><a href="#">Sport</a></li>
      <li><a href="#">Culture</a></li>
      <li><a href="#">Sport</a></li>
      <li><a href="#">Culture</a></li>
      <li><a href="#">Sport</a></li>
    </ul>
    <button type="button" class="right-arrow"><p>></p></button>

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
  padding-left: 30px;
  padding-right: 30px;
  align-items: center;
  background: rgba(31, 30, 28, 1);
}
.nav p {
  padding-right: 23px;
}
.left-arrow:before {
  content: "\003C";
  color: #ffff;
}
.left-arrow {
  border-left: 1px dotted #fff;
  height: 40px;
  --tw-bg-opacity: 1;
  background: rgba(31, 30, 28, var(--tw-bg-opacity));
  float: left;

  text-align: center;
  width: 60px;
}

.left-arrow p {
  color: #fff;
  font-size: 18px;
}

.right-arrow {
  background: rgba(31, 30, 28, 1);
  border-left: 1px solid rgb(76, 78, 80);
  float: left;
  height: 60px;
  text-align: center;
  width: 60px;
}

.right-arrow p {
  color: #fff;
  font-size: 18px;
}

ul {
  padding: unset;
  display: flex;
  align-items: center;
  font-size: 0;
  overflow: hidden;
  width: 100%;
  white-space: nowrap;
}

li {
  display: flex;
  color: #fff;
  font-size: 15px;
  padding-left: 10px;
  padding-right: 10px;
  list-style: none;
  text-align: center;
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
