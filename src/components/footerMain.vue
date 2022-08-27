<template>

<div class="footer">
  <div class="inner-footer">

<!--  for company name and description -->
    <div class="footer-items">
      <h1>VUE JS</h1>
      <p>Cosillas.</p>
    </div>

<!--  for quick links  -->
    <div class="footer-items">
      <h3>Quick Links</h3>
      <div class="border1"></div> <!--for the underline -->
        <ul>
          <a href="#"><li>Home</li></a>
          <a href="#"><li>Search</li></a>
          <a href="#"><li>Contact</li></a>
          <a href="#"><li>About</li></a>
        </ul>
    </div>

<!--  for some other links -->
    <div class="footer-items">
      <h3>Recipes</h3>
      <div class="border1"></div>  <!--for the underline -->
        <ul>
          <a href="#"><li>Indian</li></a>
          <a href="#"><li>Chinese</li></a>
          <a href="#"><li>Mexican</li></a>
          <a href="#"><li>Italian</li></a>
        </ul>
    </div>

<!--  for contact us info -->
    <div class="footer-items">
      <h3>Contact us</h3>
      <div class="border1"></div>
        <ul>
          <li><i class="fa fa-map-marker" aria-hidden="true"></i>XYZ, abc</li>
          <li><i class="fa fa-phone" aria-hidden="true"></i>123456789</li>
          <li><i class="fa fa-envelope" aria-hidden="true"></i>xyz@gmail.com</li>
        </ul> 
      
<!--   for social links -->
        <div class="social-media">
          <a href="#"><i class="fab fa-instagram"></i></a>
          <a href="#"><i class="fab fa-facebook"></i></a>
          <a href="#"><i class="fab fa-google-plus-square"></i></a>
        </div> 
    </div>
  </div>
  
<!--   Footer Bottom start  -->
  <div class="footer-bottom">
    Copyright &copy; XXXXX 2022.
  </div>
</div>
  
<!--   Footer Bottom end -->
  
<!--   FOOTER END -->
  
  
</template>

<script>
export default {
  name: "footerMain",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
/* FOOTER */
.footer {
	width: 100%;
	background: #333;
	display: block;
  
 }

 .inner-footer {
	 width: 95%;
	 margin: auto;
	 padding: 30px 10px;
	 display: flex;
	 flex-wrap: wrap;
	 box-sizing: border-box;
	 justify-content: center;
 }

.footer-items {
	width: 25%;
	padding: 10px 20px;
	box-sizing: border-box;
	color: #fff;
}

.footer-items p {
	font-size: 16px;
	text-align: justify;
	line-height: 25px;
	color: #fff;
}

.footer-items h1 {
	color: #fff;
}

.border1 {
	height: 3px;
	width: 40px;
	background: #04AA6D;
	color: #04AA6D;
	background-color: #04AA6D;
	border: 0px;
}

ul {
	list-style: none;
	color: #fff;
	font-size: 15px;
	letter-spacing: 0.5px;	
 }

ul a {
	text-decoration: none;
	outline: none;
	color: #fff;
	transition: 0.3s;
}

ul a:hover {
	color: #04AA6D;
}

ul li {
	margin: 10px 0;
	height: 25px;
}

li i {
	margin-right: 20px;
}

.social-media {
	width: 100%;
	color: #fff;
	text-align: center;
	font-size: 20px;
}

.social-media a {
	text-decoration: none;
}

.social-media i {
	height: 25px;
	width: 25px;
	margin: 20px 10px;
	padding: 4px;
	color: #fff;
	transition: 0.5s;
}

.social-media i:hover {
	transform: scale(1.5);
}

.footer-bottom {
	padding: 10px;
	background: rgba(55, 44, 44, 0.466);
	color: #fff;
	font-size: 12px;
	text-align: center;
}

/* for tablet mode view */

@media screen and (max-width: 1275px) {
	.footer-items {
		width: 50%;
	}
}

/* for mobile screen view */

@media screen and (max-width: 660px) {
	.footer-items {
		width: 100%;
	}
}


</style>
