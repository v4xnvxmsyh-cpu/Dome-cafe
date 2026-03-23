<!DOCTYPE html>  
<html lang="ar" dir="rtl">  
<head>  
<meta charset="UTF-8" />  
<meta name="viewport" content="width=device-width, initial-scale=1.0" />  
<title>**منيو** **كافيه** **دوم** - Mansoura</title>  
<style>  
  :root {  
    --background-color: #3e2f2f;  
    --card-background: #5a283a;  
    --text-color: #f2d4cd;  
    --accent-color: #bd6377;  
    --overlay-bg: rgba(0, 0, 0, 0.95);  
  }  
  
  body {  
    margin: 0;  
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;  
    background-color: var(--background-color);  
    color: var(--text-color);  
    display: flex;  
    flex-direction: column;  
    min-height: 100vh;  
  }  
  
  header {  
    padding: 1.5rem;  
    text-align: center;  
    font-size: 2.2rem;  
    font-weight: bold;  
    background-color: var(--card-background);  
    border-bottom: 3px solid var(--accent-color);  
  }  
  
  main {  
    flex-grow: 1;  
    padding: 2rem 1rem;  
    display: grid;  
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));  
    gap: 1.5rem;  
    max-width: 1000px;  
    margin: 0 auto 100px;  
  }  
  
  .menu-image {  
    background-color: #fff;  
    border-radius: 15px;  
    overflow: hidden;  
    cursor: pointer;  
    box-shadow: 0 8px 25px rgba(0,0,0,0.5);  
    transition: 0.3s;  
    aspect-ratio: 3 / 4;  
  }  
  
  .menu-image img {  
    width: 100%;  
    height: 100%;  
    object-fit: contain;  
    display: block;  
  }  
  
  #overlay {  
    position: fixed;  
    top: 0; left: 0; right: 0; bottom: 0;  
    background: var(--overlay-bg);  
    display: none;  
    justify-content: center;  
    align-items: center;  
    z-index: 3000;  
  }  
  
  #overlay img { max-width: 95%; max-height: 90%; border-radius: 5px; }  
  #overlay.show { display: flex; }  
  
  .close-btn {  
    position: fixed;  
    top: 20px; right: 20px;  
    font-size: 3rem; color: white;  
    cursor: pointer; background: rgba(0,0,0,0.5);  
    width: 60px; height: 60px; border-radius: 50%;  
    display: flex; justify-content: center; align-items: center;  
  }  
  
  footer { text-align: center; padding: 2rem; background: var(--card-background); }  
  
  .contact-buttons {  
    position: fixed;  
    bottom: 25px;  
    left: 20px;  
    display: flex;  
    flex-direction: column;  
    gap: 15px;  
    z-index: 2000;  
  }  
  
  .contact-btn {  
    width: 60px; height: 60px;  
    border-radius: 50%;  
    display: flex; justify-content: center; align-items: center;  
    box-shadow: 0 4px 15px rgba(0,0,0,0.6);  
    transition: 0.3s;  
  }  
  
  .contact-btn img { width: 35px; height: 35px; }  
  
  @media (max-width: 600px) { main { grid-template-columns: 1fr; } }  
</style>  
</head>  
<body>  
  
<header>**قائمة** **مقهى** **دوم**</header>  
  
<main>  
  <div class="menu-image" data-full="https://i.ibb.co/S7X7YvS/menu1.png">  
    <img src="https://i.ibb.co/S7X7YvS/menu1.png" alt="**القهوة** **والمشروبات** **الساخنة**">  
  </div>  
  <div class="menu-image" data-full="https://i.ibb.co/pWf4L4z/menu3.png">  
    <img src="https://i.ibb.co/pWf4L4z/menu3.png" alt="**العصائر** **والمثلجات**">  
  </div>  
  <div class="menu-image" data-full="https://i.ibb.co/r7YyXvX/menu2.png">  
    <img src="https://i.ibb.co/r7YyXvX/menu2.png" alt="**السوفت** **والشيشة**">  
  </div>  
</main>  
  
<footer>  
    <p style="font-size: 1.4rem; margin: 0; color: #f2d4cd;">**تضاف** 12% **ضريبة**</p>  
    <p style="font-size: 0.9rem; opacity: 0.6;">Dome Cafe - Mansoura</p>  
</footer>  
  
<div id="overlay"><span class="close-btn">×</span><img src=""></div>  
  
<div class="contact-buttons">  
  <a href="https://www.tiktok.com/@dome._.cafe?_r=1&_t=ZS-94usYwlf1fx" target="_blank" class="contact-btn" style="background: #000;">  
    <img src="https://upload.wikimedia.org/wikipedia/commons/3/34/TikTok_logo.svg" alt="TikTok" style="filter: invert(1);">  
  </a>  
  <a href="https://wa.me/201097343627" target="_blank" class="contact-btn" style="background: #25D366;">  
    <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp">  
  </a>  
</div>  
  
<script>  
  const cards = document.querySelectorAll('.menu-image');  
  const overlay = document.getElementById('overlay');  
  const overlayImg = overlay.querySelector('img');  
  const close = document.querySelector('.close-btn');  
  
  cards.forEach(card => {  
    card.onclick = () => {  
      overlayImg.src = card.getAttribute('data-full');  
      overlay.classList.add('show');  
      document.body.style.overflow = 'hidden';  
    };  
  });  
  
  close.onclick = () => {  
    overlay.classList.remove('show');  
    document.body.style.overflow = '';  
  };  
  overlay.onclick = (e) => { if(e.target === overlay) close.onclick(); };  
</script>  
  
</body>  
</html>  
