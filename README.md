"# premier-projet-medianet-2024" 
<!DOCTYPE html>
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
<style>
body {
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  margin: 0;
  background-color: #f4f4f4;
}

.container {
  position: relative;
  max-width: 1000px;
  margin: auto;
}

.scroll-container {
  display: flex;
  overflow: hidden;
  scroll-snap-type: x mandatory; 
  white-space: nowrap;
}

.scroll-container img {
  padding: 10px;
  flex: 0 0 auto; 
  width: 200px;
  height: 200px;
  scroll-snap-align: start; 
}

.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  padding: 16px;
  margin-top: -22px;
  color: #07ff5e;
  font-weight: bold;
  font-size: 20px;
  border-radius: 3px;
  background-color: hsla(277, 100%, 51%, 0.8);
  user-select: none;
  z-index: 1000;
  transform: translateY(-50%);
}

.prev:hover, .next:hover {
  background-color: hsla(71, 79%, 47%, 0.8);
  color: rgb(232, 16, 16);
}

.prev {
  left: 0;
}

.next {
  right: 0;
}

.dot-container {
  text-align: center;
  padding: 10px;
}

.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 2px;
  background-color: hsl(0, 91%, 49%);
  border-radius: 50%;
  display:grid;
}

.dot:hover, .dot.active {
  background-color: hsl(193, 100%, 55%);
}
</style>
</head>
<body>

<div class="container">
  <div class="scroll-container">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRxhKfeA9-eoWM7tJA8B_9g7DZL06s9pkfCJw&s">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRwR1I3TQqoLPYCEIGaiSdbXZ4cQ2XalBcGJg&s">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRb20eJEKQdG4ULlHuHkttTWYObZrBBzEaqbw&s">
    <img src="https://upload.wikimedia.org/wikipedia/fr/d/d4/JSO_Logo.png">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQfueekWVvbSh6PeLad5OaiUnTjD0pI2P16_A&s">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSm_VRDD1o2Pg-5YqD19FEe3kp9bpuL1CEzRw&s">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcROqZa_UjnfeWuFJScv3GYQWO6IjP58Dbckcg&s">
    <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRKB2j60Ta1S5kvP1HJbtPfJmTeKajJeihNRA&s">
    <img src="https://tmssl.akamaized.net/images/wappen/head/86583.png?lm=1614946806">
    <img src="https://tmssl.akamaized.net/images/wappen/head/89037.png?lm=1677151873">
  </div>
  
  <a class="prev" onclick="plus(-1)">&#10094;</a>
  <a class="next" onclick="plus(1)">&#10095;</a>
</div>
<div class="dots">
  <span class="dot" onclick="currentSlide(1)"></span>
  <span class="dot" onclick="currentSlide(2)"></span>
  <span class="dot" onclick="currentSlide(3)"></span>
  <span class="dot" onclick="currentSlide(4)"></span>
  <span class="dot" onclick="currentSlide(5)"></span>
</div>

<script>
  
let slideIndex = 1;
showSlides(slideIndex);

function plus(n) {
  showSlides(slideIndex += n);
}



function showSlides(n) {

  let slides = document.getElementsByClassName("scroll-container")[0].getElementsByTagName("img");

  let nbPhoto = 3; // entrez le nb de photos !

  let total = Math.ceil(slides.length / nbPhoto);


  if (n > total) { 
    slideIndex = 1; 
  }


  if (n < 1) { 
    slideIndex = total; 
  }


  for (let i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";
  }


  let debut = (slideIndex - 1) * nbPhoto;

  let fin = debut + nbPhoto;
 
 
  for (let j = debut; j < fin; j++) {
    if (slides[j]) {
      slides[j].style.display = "block";
    }
  }
}
function currentSlide(total) {
  showSlides(slideIndex = total);
}
</script>

</body>
</html>
