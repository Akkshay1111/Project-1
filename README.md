# Project-1
Responsive Website


<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

 <style>
   body {
    font-size: 15px;
  }
  
  button {
    background: #ffc600;
    border: 0;
    padding: 10px 20px;
  }
  
  img {
    max-width: 100%;
  }
  
  /* .wrapper */
  
  .wrapper {
    display: grid;
    grid-gap: 20px;
  }
  
  .top {
    display: grid;
    grid-gap: 20px;
    grid-template-areas:
      "hero hero cta1"
      "hero hero cta2"
  }
  
  .hero {
    grid-area: hero;
    min-height: 400px;
    background: white url(images/taco.jpg);
    background-size: cover;
    background-position: bottom right;
    padding: 50px;
    display: flex;
    flex-direction: column;
    align-items: start;
    justify-content: center;
  }
  
  .hero > * {
    background: var(--yellow);
    padding: 5px;
  }
  
  .cta {
    background: var(--yellow);
    display: grid;
    align-items: center;
    justify-items: center;
    align-content: center;
  }
  
  .cta p {
    margin: 0;
  }
  
  .cta1 {
    grid-area: cta1;
  }
  
  .cta2 {
    grid-area: cta2;
  }
  
  .price {
    font-size: 60px;
    font-weight: 300;
  }
  
  /* Navigation */
  
  .menu ul {
    display: grid;
    grid-gap: 10px;
    padding: 0;
    list-style: none;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  }
  
  .menu a {
    background: var(--yellow);
    display: block;
    text-decoration: none;
    padding: 10px;
    text-align: center;
    color: var(--black);
    text-transform: uppercase;
    font-size: 20px;
  }
  
  [aria-controls="menu-list"] {
    display: none;
  }
  
  /* Features! */
  
  .features {
    display: grid;
    grid-gap: 20px;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }
  
  .feature {
    background: white;
    padding: 10px;
    border: 1px solid white;
    text-align: center;
    box-shadow: 0 0 4px  rgba(0,0,0,0.1);
  }
  
  .feature .icon {
    font-size: 50px;
  }
  .feature p {
    color: rgba(0,0,0,0.5);
  }
  
  /* About Section */
  
  .about {
    background: white;
    padding:50px;
    display: grid;
    grid-template-columns: 400px 1fr;
    align-items: center;
  }
  
  /* Gallery! */
  
  .gallery {
    display: grid;
    grid-gap: 20px;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  }
  
  .gallery img {
    width: 100%;
  }
  
  .gallery h2 {
    grid-column: 1 / -1;
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    grid-gap: 20px;
    align-items: center;
  }
  
  .gallery h2:before, .gallery h2:after {
    display: block;
    content: '';
    height: 10px;
    background: linear-gradient(to var(--direction, left), var(--yellow), transparent);
  }
  
  .gallery h2:after {
    --direction: right;
  }
  
  @media (max-width: 1000px) {
    .menu {
      perspective: 800px;
    }
    [aria-controls="menu-list"] {
      display: block;
      margin-bottom: 10px;
    }
  
    .menu ul {
      max-height: 0;
      overflow: hidden;
      transform: rotateX(90deg);
      transition: all 0.5s;
    }
  
    [aria-expanded="true"] ~ ul {
      display: grid;
      max-height: 500px;s
      transform: rotateX(0);
    }
  
    [aria-expanded="false"] .close {
      display: none;
    }
  
    [aria-expanded="true"] .close {
      display: inline-block;
    }
  
    [aria-expanded="true"] .open {
      display: none;
    }
  
  }
  
  @media (max-width: 700px) {
    .top {
      grid-template-areas:
        "hero hero"
        "cta1 cta2"
    }
    /* About */
    .about {
      grid-template-columns: 1fr;
    }
  }
  
  @media (max-width: 500px) {
    .top {
      grid-template-areas:
        "hero"
        "cta1"
        "cta2"
    }
  }
  </style>
 
  <style>
    /*
  Oh Hello!
  These are some base styles so that our tutorial looks good.
  Let's go through the important bits real quick
*/
:root {
    --yellow: #ffc600;
    --black: #272727;
  }
  
  html {
    /* border-box box model allows us to add padding and border to our elements without increasing their size */
    box-sizing: border-box;
    /* A system font stack so things load nice and quick! */
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica,
      Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
    font-weight: 900;
    font-size: 10px;
    color: var(--black);
    text-shadow: 0 2px 0 rgba(0, 0, 0, 0.07);
  }
  
  /*
    WAT IS THIS?!
    We inherit box-sizing: border-box; from our <html> selector
    Apparently this is a bit better than applying box-sizing: border-box; directly to the * selector
  */
  *,
  *:before,
  *:after {
    box-sizing: inherit;
  }
  
  body {
    background-image: url("./images/topography.svg"),
      linear-gradient(110deg, #f93d66, #6d47d9);
    background-size: 340px, auto;
    min-height: calc(100vh - 100px);
    margin: 50px;
    /* background: white; */
    background-attachment: fixed;
    letter-spacing: -1px;
  }
  
  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    margin: 0 0 5px 0;
  }
  /* Each item in our grid will contain numbers */
  .item {
    /* We center the contents of these items. You can also do this with flexbox too! */
    display: grid;
    justify-content: center;
    align-items: center;
    border: 5px solid rgba(0, 0, 0, 0.03);
    border-radius: 3px;
    font-size: 35px;
    background-color: var(--yellow); /* best colour */
  }
  
  .item p {
    margin: 0 0 5px 0;
  }
  </style>
  <title>Responsive Website! - By Akshay</title>
</head>

<body>

  <h1 style="border:dashed yellow 1px"><marquee>Ak food hub of all type of Foods.We have spacial discount on online booking upto <b><u>15-45% OFF</u></b> and spacial discounts on sunday. </marquee></h1>
    <hr style="color:whitesmoke">
    <h1 style="color:rgb(32, 162, 167); font-family:  sans- serif, Arial, Helvetica;">Sign In</h1>
    <hr style="color:whitesmoke"><br>
 

  <div class="wrapper">
      <nav class="menu">
          <button aria-expanded="false" aria-controls="menu-list">
            <span class="open">☰</span>
            <span class="close">×</span>
            Menu
          </button>
          <ul id="menu-list">
            <li>
              <a href="">Cold entrées</a>
            </li>
            <li>
              <a href="">Hot entrées</a>
            </li>
            <li>
              <a href="">Fruit</a>
            </li>
            <li>
              <a href="">Desserts</a>
            </li>
            <li>
              <a href="">Reservations</a>
            </li>
          </ul>
        </nav>
    <div class="top">
      <header class="hero">
        <h1>Akshay's Foods Joint</h1>
        <p>Pretty Good Test!</p>
      </header>
      <div class="cta cta1">
        <p class="price">180 /-  Only</p>
        <p>McDonald's McFlurry</p>
        <p>In Special Offer </p>
      </div>
      <div class="cta cta2">
        <p class="price">199 /-  Only</p>
        <p>Panda Express Orange Chicken</p>
        <p>In Special Offer </p>
      </div>

    </div>

    <section class="features">
      <div class="feature">
        <span class="icon">🌮</span>
        <h3>Burger</h3>
        <p>A dish consisting of a flat round cake of minced beef, or sometimes another savoury ingredient, that is fried or grilled and served in a split bun or roll with various condiments and toppings..</p>
      </div>
      <div class="feature">
        <span class="icon">🍺</span>
        <h3>Beer</h3>
        <p>Beer is one of the oldest and most widely consumed alcoholic drinks in the world, and the third most popular drink overall after water and tea.</p>
      </div>
      <div class="feature">
        <span class="icon">🎵</span>
        <h3>Music</h3>
        <p>Music is the art of arranging sounds in time to produce a composition through the elements of melody, harmony, rhythm, and timbre.</p>
      </div>
      <div class="feature">
        <span class="icon">🍷</span>
        <h3>Wine</h3>
        <p>Wine is an alcoholic drink typically made from fermented grape juice..</p>
      </div>
    </section>

    <section class="about">
      <img src="images/burger.jpg" alt="Yummy Taco" class="about__mockup">
      
      
      <div class="about__details">
        <h2>Featured Taco</h2>
        <p>Slim Profile, easy to hold and loaded with cheese.</p>
        <p>This is the one you have been waiting for</p>
        <button>Learn More →</button>
      </div>
    </section>


    <section class="gallery">
      <h2>Inside Akshay's foods</h2>
      <img src="https://th.bing.com/th/id/R4794d79b559940fa142f96f4f7fff3c2?rik=nRxiMC1AMnNycA&riu=http%3a%2f%2fs3-media3.fl.yelpcdn.com%2fbphoto%2fcJG_yf5fA2UF8TTnlJezEQ%2f348s.jpg&ehk=qz9eZYoXA%2bJ%2fRiL9GJkaIuYgsBjN7BzUNlhU37prW%2f8%3d&risl=&pid=ImgRaw" alt="">
      <img src="https://cdn.downtoearth.org.in/library/large/2019-05-31/0.68487000_1559290735_70-20190615-dte-english.jpg" alt="">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQpno89s53p-_xqDfX5Hajjm2OftOAGVrZCRw&usqp=CAU" alt="">
      <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAAQABAAD/2wCEAAkGBxMSEhUTExMVFhUXGR0aGRgYFxgdGBgYHxgYGBcbGB4fHSghGCAlHR8XITEhJSkrLi4uGB8zODMtNygtLisBCgoKDg0OGxAQGy8lICYtLTI1LS0vLy0wLS0rLS4tNS8uLS8tLS0vLS0rLS8tLTAvLS0vLS0tLS8tLS0tLS0tLf/AABEIAKcBLQMBIgACEQEDEQH/xAAcAAABBQEBAQAAAAAAAAAAAAAFAgMEBgcAAQj/xABFEAACAQIEAwUFBgQEBQMFAQABAhEAAwQSITEFQVEGEyJhcQcygZGhI0JSscHwFGJy0TNDkuFTgqKy8SRz0hc0Y4OjFv/EABoBAAMBAQEBAAAAAAAAAAAAAAIDBAUBAAb/xAAzEQABBAEDAQUHBAIDAQAAAAABAAIDESEEEjFBBSJRYXETgZGhsdHwMsHh8RVCFDNSI//aAAwDAQACEQMRAD8AxypnCsUbN23dG6MG+RqTwjgV3EaoAqTBdzCz0GhLHyUGrThuzOHsAlw+IuD7sQgMSJUSSSNlMnnlG9IklYAWnPkmMY45C088MwfFsJZu3bQIdZVtrqnoGGo5yNvKs84h7NVS64S8XUahIC3I5Sx8J+EHy1q49nL9y1bUMe7skhlIgAsQNAOSxpz84mivFbuHtgAkq+UsAuhYCNM3IjpPXpWMNRJGCGdPz+1b7NpNuWbvwVsIAf4dbQP+YRnf4SdPnFRcZi1e2+VnIUiS6gHMegBIAP8Aer5xh1xVtgyQv82vxHlzms+wVhS92w0eND3Zn7ymV66gZj8K7Bqfak3khHJCGNHmr1wfj1rG4RbXeAYhUylWJ3GgMAazvIof2Cx4a7cshlV1OZc05SQYdfPlt+lUfgGLGFxaXGEqpYGOUgifqKt2FSwTax2oYXmzWjER4wsTA18J3iTvvXpoWsJB4NV65Xo3F4x5rUhjWTMSFmJhQZPWQarQ7QrfcBlZHV/eOXYxtp+4qfaxod1uDVSo000kAkN560tuBrcurcVdAdRyOs/v1qSUl42ZI/fxRsawC3YPj+yO4u6CmUrKnlI1oTcwoa2MqK6gkhSdiCfdImRyjaibWEtJlyyo/EZB8iTMVXeIvc/iEaykW7UkqDqwZdIHSek13UEbrec1Xn9MpMV8NRfDAqCqrEagSoMHUjfQiSBPSh3BrFy0v2s5iWJmNZJPp8qnWMekrOYM+mXmNPvfvnRC53bpkcxPunnPKPOhjaJODkcJjrZgjlIsEuNCBO/XT/aqt2mxdu/cVQ2YgagFSV1/KDyM0bwysnhJJE+9yM8qqWP7MGzft3cwKZiQMokEgxJ3IEk0LpN0ebHj1yjiYA6/ghuMsNh7ikQLbEZmC7aaFhz9fy5iO1XC1e22KtgKyFe+QbEMYS4vkTofPzBJujQXkiQPCZEiDqZjy6+VD7fBgC1hCe4v57ancoCmYQZmA2oB6DpJq0OowPH9kGoYssmvCxolxnH3Gy2LiWk7gskW7YXWYaSNW1HOhRatwLPXpcim72LZTIJzTIM6gjn616TUK8ZJogFwlbL2d7cYfiNhMNjWW1iUINu62iMw2MzoTsVO80a4twG5km6veL1UZl9dNvWKwJV012ovwbtZjMLAsYi4q/hJzJ/paQPhWfquz2TndZBHUKzT6x8IocK88fxpQ4cW7kG2xMEsdgFACmQedHOC4JLYZnKm40MzDkD156md6p6e1XFMIv4bC3/6rcH8zUq17T9dOF4aT0PmCPudQPlUEvZMjmBgdj65Vo7RjP8ArR/PJWTHYlkdYRoBOoB2I8hS8VwDEY/Dm0Q9oEoxdwNhuAvPQnXSq83tK4g7Lbs2MNYLaCUJPwJMfSoXac47MLeMxjXSy5jbttCBf5goAPyooOy2xEFxyM4/Cgm1zpW7Q0AVSt1/jWD4Ra7jDsL99RAUEFLZ5tcI0mdSo19KyXi11r1x7txizuSWY7kmiptqgWFA01HpQjFjQitOKmnCkey255UF8ORtrTVOW7xWnHYNrzqxRJyzxJ10JzDzqdYxavtoeh/SgrLXgrhaF0OKP3kkabimFao2Dx5Gjajrz/3qTdAmRqDQ1SK0oGuakg14TXF5aFxBThlA7vu7ajIhXUIu0kjYnflr1OtQzdQbPlWCVGygaEsY1Yk7zvVh4fjcPjMNdFu4WmcysfEs8tdY6Has/wCKcMvYV88F0Bjxagg7r8qyAHOwTRV+BlS+PLibJS5nZ0URuRknca6hT+4q3djL1rG4dTdGZ1YqzES6gTlE8lK/maqeEsW7uGu5DdJYaW5ZlBkHQfd1oT2U4y2BxMtORvBcXXQTqSI1jXTzodhmY4f7NPhVrslMIHQq0durV+ziRDsLYAyKjHKF9OZoBhMYM5ZzBCydNdCQ0AjnP1rZr2Fs4pUfKrqRKtJ2I0y8oP6VnXb3hb28VbvqALYCr5RqGDR1BNdiod0geq855cP2VEvP3l5imgbWDp6kCTFXP7Q8KS6wBGqTuZW5z000HXnULtTgAhR1AHhI03kDr+9qF8Nx9w2cTaBPdEC5ED35Vfqv/bVM1SRtcOhH2SYCWOLT1tapwnji2rNprttjbK5VuAKSTIGU6yCenlRs8XNtQUQsCAesDfTXeNAKyrsPea4XTVpCsQToMpgR51acRh3uZgl0pKwJ+7Gnh5AisqdzoTtaa81VDE2Uku4V04ncL2ibRzkuI/l8WsjoKVjsNcAtmzlJWFYHZreux5EGhXZTC3rCoLstmJB11B0AbU7RMjfbpRrH4xreeUIWBDyAuvMmfDFE0NIL3emPjaTIdtMCp/FONv8AxSWRaKwVOaCX3OYAdNvzovhLpuE3GLAkyV1jQFcoB25bb0dNhHUMVGYbGJI8p9agXuDgEMSWkiSz+7r92BS5YH7bbxgomTC6KIWQHGWBGnIT5R0ig/aMQqg/inWdCFI0+tGyEt8oPKqf2t4gDcS2DqBJ5x15idNYGtMnZ/8AOjyuQm32OFDQZojXmduZgaj8jqJNTzjlsWxdYHIguXSfJcttF9WYkD0pPZ2wbstyOp/JfWBr6mqx7U+MrK4O0dFg3I8h9mnnElj5kUzQacl25d1ElYWeYzEF3Z2952LH1Ykn6mvMPbBYBmyDmYzR8OdNkwa9vWwwLppp4k6DqOqz8R8jW+s9P8XwS2ipt3RetsJFxVZfFpmRlbVWXT1BB50LUSam4K5Ia0zQrxB5K49xvT7p8jPIVqXZT2NBlW7jb24BFqydIOviuc+XugeproNYK4fFZRcUAa09heDYi5rbw99x1S1cYfMKa+neF9msHhQO5w9pCPvZQX+LtLH509jeN2LXv3kXyLCfgN6WXhv6iAiALzTRa+aR2Wxo1ODxUf8AsXf/AI0y+Bu2SC6XLR5Z1ZDPlIFfSjcfs/jH1rxuK220LCDyOxmkHVw/+x8Uz2Ug5afgvnfAz3iu0kg/WtU4/g0u8Pw2ICqHAZGOkkajU/AfOjXFuyOBxIM2hbY/5lmEaesAZW+INZ52y7PY7BWf8Z7+DUyCNO7JOneLy/qkj02owdxsIbBFHCrPE3hd9SYj4a0MUzSHuM510FPWxGgo2spG6S0zdw4NMYPAXLri3aR7jnZUUlvkOXnVl7NcCfGX0sppOrNyVB7zHr0jqRW8cE4Hh+H28llAuniYxnc/iduf5DlROlDBZSdtrH+DeyLHXRN5reHB5Mc7/FV8P/VVis+xawB9pjLpP8iIo/6s1WjjXbFbci3DHkTIX6Ak0Bw3ae9fvLbt5mMSSoAQLp4tRsDzO+0a1nO7SBPcBKoOkc0W/CZuexrCAf8A3WJ//l/8KhYn2RKulrHR/LctT9VcR8q0S1etuTCgsIzA9NpA23008qG4ngyjvGTNaPvMAwKsBrIzTl5bR6ULtZMRbAD8fsvMhZdOJH56rMuI+zfH2hK21vAc7TSY/pbKx9ADVSv2mRirqysN1YEMPUHUVu1rtFlvC0ykAgZXn3qI4qzYvEG9ZtXSNAbiKxHUDMDFOi1zXYPK5JpnsokYK+eeE8QNq4GUlGWcyfiABOWOYJERWk8OvWuJ2CzFl0gqrQVYctdv1oFwvA28cr2bwKuBmDL7vkVHLbU1TMU1zCXnRbhO6kiQGERrXnsE3GHBda7Zzwrnh54deBnNZuEZ1aM6+emkjnG9TO0HA8PftZ7LgmTc0MllaZPmQw+tV/s1gFxDZjcZrWneDZ7fInpE8+lH8Pww8Nv/AGqi7g7mi3YlVYnw5h907idiYqVwIfg94e6/5CoNUK4SuxPadsNkw19vszojx7h5Bv5Z58qJe0O8zWyiEMdJg6xOxEbdDTvG+yS4mXtPlHIQMp0BpjstjHRHt3m1syCxEkpuB+k76UtzuHj3heLQcBVp8Q2IwthhlBtsRczaHSJjTpJPqKEcbwptsDm8LDUr0Osem1WrjmGtkjunNu5ezSvuhXA1kRpmWBPlQIqbth7bKe8tmIjXX9POqo5Lo9Pv9khwKl+zvELbu3A+mm/XXQVo+ExKrmYmCxJkAaT0rIOHXM7IplbqsBPQyAdOc9K1Dg9tbp+0glCJI0WdoqXWAh9+PiqYaLRasKhmQZWmI8TDf1HKDFK4bxO7lAdGzAEFgAUPmD+lSMPfRQZICD9N6dbEoEDKJXUnQeZmpWjZkO/Pshd3sFqk4C6zDxhRPIfHf6UzjkdQoFvOJ3mI105V2FCqFZAFzQfLU66eleY/iEKQgLnUQIHzJ0A8zV4IdEA45/PL9lMQd+AhnaPjCWLcsAzEwq9TzPkB1qpcC4NcxLtdvE92TM/8QkyQB0HX4T0Ivw4XLveYhu8YHS2s92vkW+95gRVmw9sRrHkOQHkPKga3cbdynk7BTVX+2PGRw/C/ZQLj+G2N/wCpj1Cj4SR1isVu3CxLMSSSSSTJJOpJ6mrT7SuK9/jGUe7Z+zH9W7ny10/5RVUitSBga1SPNlNXKVgLNx7qJaBNxmCoBuWJgD0115RM169urx7GMEH4hmMfZ22ZZ5MSqyPgW+dOc6ggrKHds+wOIwUOQGQgeJAcuaPEAN11nw9NROoW1+z32im3hDh7il7tofZknQ251nmcunwPka0rtNiAmFuLcAcMMozR4p0k8hG/wr584xwh8Pd7xSQQ2jdG6N66+TfQyvnaXeyDqdWPLyVMULi32pbbQcrTOK8bvkF7hz22XwxICtoY/OgeGxqXGazdCk6ZDlXKznrzgbUzwnii4hVLsVIIDLplBUaCOYIBgmdJB505wVCMfhgVUDNJ1EwJPTy+h0rAbCTIWyfq8Vtyysjh3RjBqq/OUXxGDuJauswXLbc28qzLldsoI+g6nXTUbw/HpeDWywVgu+XI6tGs8ump+m9XDtBdAJzWb7W1Zj9nblZJJLEjXcmhV3B8OYqxw5Y3QDmFy5MddG5Dp0oXRRBxBx4H0S4dU8ji/RSuG33YK9s5kVcrHkzCANDt8daNcOx4uAhl6q6Nr5EEcxyoHwNrCyq271gT4VZhcUxPiXmZ8id/OieCwAF97ltlZWHiA3DAwZU6gn+9M0odE8BjrF8fuptQWSA7hWMfYrKvaJ2ZGCxA7v8AwboL2x+HWHTzymI8mHnVXWtc9sij+FwxPvd60emTX6hayG7cCiTX04yFkLVPYiF73EHQtktx6Znn8lqz+0bjRtBLY+9LN1KggADrJJ/0isa9n/ag4LGLdb/DbwXB/KTv8Dr862Xt9w4YiymJtQ4RTtrKNBzD+kj5MelS6tp9k4flKjSke2aT+FZmly5cJFtwZVyqhEZgU8UEHb1AOgJ5GiHCOFWzaGKw5LlLQNyySM6XI94662jGYemtDMDira27k2rhYkd3dV2BQkEMZEj3oMRrO4ihvD793DMt61cKXFUCfKFBU7ggkbc9KiDGez2jCtcZC82Pspn/APpLuGcXhq7qwliTIYmfLcE89RVn9nHbPFYrFGzfYNbyMRCCQxKqNd41IignGMnExZuW7Yt3YZWRfdJDgyscsveaHUeHcRUjBcHxGBS5ftIQ+dGSNRkBaFOus5lkTyFPa6NkdVn+VHJbnFys/EMElu6ttyxYMJbkwOZg3PoB6zSsbj8p+zZWBnl8fgfL6Cq/xbjjrfAcySMyHorMTBPSQ0dJrzAvbZdQ0AmCDEzr1+tYkjS2yBQK1tI90uHi6+f9LO+A9obmHYFfEo0ynkOYB5elWHh9rBYyczMLpJOSQpG+iSCG/egrPlaKeW8Dv/cV9VJA12Rg+IWA2QjBytHwPZNUuZrWIv2W/EAI3GjQQGExI2rQb1t7Kpbuuji54SMsJdJEkBSTkYidJIMHbasU4VjsTbU3LV5wo3h59JU8vhFHOKdp72MtrbuXElTMAMskTB2MH41mz6eVzhmx49QrYnsrwWuYLh62rc4YeH/hFjHmFnVSNo25aVTOOcUw9jFK6o4eIvKyMBlJ3II+vPWo/ZLtQ63FXF5jlBi6s6iP8yNSR+Lnz6m19ocRZxeHuKjo0feJUAHzJIipXMLXU4H3cFNYUI49wZLytes5A4ysCTEkajyMjTzoRwm4GeQCGjKSVzeqPsZB2IPOo3DL72Aoc2by2z4FVySB+E+HKR0MyNag4fE3kvXbpRctwksgbbeIPUTTmMNFqE0Mp3tN2axC3DdS3n1mVEGN9pmjHA7TXlIsYkKqLORli4bkTsTrzGaTyolwbtkqoQ6k9PFJHloPzNB7/Dbd9jfKvlH4WW0vpMyx9CKCXvtDXdPejiJYSUHxvG8WAAdUE66gHYtudTtVp7M9sb7oEfCuVme8MIgG41b3h6SdagJiEtLNvDpbjZ2gt6gkkz5zQDH8fu3SQJjQSWMmTGkQFB8q8IGPFBvvTHSudg8eC1S7x0XFgE6a6bbgRyJ+leW3Zhmd8iD5n+3yrP8AsteutMuBClMhPiJIIkDnDR150Ru4h7o8Dm6FGyEZnIldAQBJ0Ma7jfWAra4gnwXHxU2wibdoQz5bY0mB6U72s7ZfwWW0ih7zJm1Phtg7FhuSeQ02+eaNxt7TlVRldSQe83UgwQUHMefyobicUzszuxZ2MszGSTz/AH0itCLS0bcopJQRQTmIxBdmZjLMSzE8yTJPzpANMZq9z1cApiU/NWf2a8ZGFxyOfcYFHPIAxDHyBA+dVBrtSbF8Ih6tv6DYfrQvGETclfTXanBd/hmABaIaF3IG4Eb6TpzrPbPDwZFwTZuEqBH3iT73Ubn4UK9n3tS7gDD4wk2xolzcqOjdR51eO03FMJasDFrdBU6Kqwc7Ez4ByIgnoNazNdpHSOEjeeo9OoVuk1XsmmMiwevqs+7P8IIxBGhKkZkbmFYGdd4aPp50bOBtW8cl2Svdo75SCSRlIJn8ABPnJ6zT/Br1jFE3MLcAxCy3duQHcxJCyObTME+9rvRi/bF60WyBbvdugBEMMwhl11EkDQ9B50h2++/g18QjkDSe5x9Cqd2sxt1caVR2UlgYznKysluCANQNGHMaDzpvszxAXMtu6jEKxZXTVrROpDA+8pmdNak8Zdc+Ge5Ye+VstbK6qS6NlBbnMEkrH3qRw/hfEcT4LWEFizBGo7tQI06O3wHwpZYZW00X+H3pmnqJx3FHcdiMLZVjduNcU65FUCI15SRt1FW3s6HdA5t90G2X70ci/n5cqCcP7L4bAot/G3rcpqC0LbVv5QdXbod/Kaq/a32htiQcPgwyWjo1w6PcHMAfcTrzPlrNGl0Ri70h9wStRMJTtjz5lBvaz2nXE4lbdozZsgqrDZnJGdh1GgA/pnnWe4piTU/iKeKPL50MuVsRmws+Ru00vBV47C+0W9gYtPNyx+E7r/T/AGqjAV7REAoAVuWHsYPGgvgbypmMtYbRZ38I+4Z10kabCoWK7OFCS9llEakHT5jQj+9Y7YuMrBkYqw2IJBHxFWzg/tH4hh4HeC6o5XBOnqIP51mT9nBx3MNFaEPaD2t2uyPP7qzdnsEuFxaFXV1ZiJggg5WMHSCYH7irJje2NlMVfwl0DJlGQ8nJQZkPQ68v/NXse0/D3NcTgJaQc1thMjY65fPnU3hnbDgiMXGGv23IgkgsYBkf5jUr/izZ3Z+/zXnzxuIxXw/hQuGcNC3GuNLKw8OYqWQeREgty+dWrBYIkZjZNwkAkxAB1nlBPp5VD/8AqFwlNUsXXJMwLS7/APMwr257VZ/wcAxXrcuhT8gp/Ok/4+R5uRw9yedcA3bE1YBXUsCkk19CsZeU+mJPPUUxXCvUvWiOHxqr1PkQpFEU48AICx6Ej6bCgljDM5hRNFMT2fu21DNGvQ6/Kp5PZAgOOVVE2ZzSWDAU63xtTEu69REj55q58daVpJLdOf6xQtOHXIkLPprHr05U3cwxUwwIIoBHGTQKJzpWi3D5Ije48Z8CD/mP6DSpXDuJ4i4wBIRCdWy6T6nQaxQizhLupW2zZYJ8MjUFhpzkA1YuFWmNtlRXGb3kElddR5KYj1ilzBjG4CASPJyU1ewV64CVZrmVWd8zRlC7wOfM+gp5mtvC5XtZQAwkwTlgiWJKnQROhg8yKLdnsNfF5MOto5wWDjZiGAgfIkztAmil3s2yq1tybly3IZdGcrEDKDGuizz0qGScx/q46H18en9q7Tsa+iT6hALVjE3MpXNKDwjLBBABygRqdFOvxqwXuHXsCGvrGS9pkB+0tPJcd3qAwBBE8xEioHZfHMw7hLzWj3gAkA+8wBDnLIJEQdp3HMaDY4tav2LotNbFxQwi5Jtd5JUBwRtoNpGpApbg8P75AH1sqyZwABYLvkZx/fv81lDcMtG2w8IjUXJJZ/FMkknWNDp8+cE8GLN4FZbeaO8fUDoDGnIyf2bXx/gJL/ZKFTWVtkvlbKGZUOgyxMFssbRtIrggDm5YAuBHEmWkZl2crsNOf+0VN1NAkG6U8kMZAJFIFi+FEMRbYMokg6zGYqswOZA8taFkEb71e+I4axaBS2HVlVM7MRLHJM7wviIPlFU/iWGKGTGpI96TI3O5MHkefKqtPPvUmp0wa3exQmam+9mkO1NzVdKAFPM9EuB4hZKMdDtJ0B5x60JrhQvYHNpMjkLHblccgtXAUJ0OhBIII2IPrzrQOy/b13R7d22t6+BKA5Va7G6zEZ42HP1rI8BxGCA502nePXrUy5cKGQwPMMp+IIIqQsc0q3cyRq0K/wC2lv8ALwQB/muRHqAn0oFxH2pcSvSFe3YH/wCNBPzfN8xFC8Sn8YrXkH/qVE3UA/xlA1uoB98ffUb+8OYqvI+tNaQQpizaUXQviLneYi8znmzszN6Df5bVPW2si1azMzmBpJY9AKi9nOF3cXfSzZWXbrsq82boB/YbmvoHsr2TsYFBlAa6R4rpHiPUL+FfIfGaHYXFM9qGBZLwn2VY2+c13JYU/j8T/wChf1IqzWfY3g11u3r9w9AURfkFJ/6q03E30QZnYAfvbrVU4r2xtgE20Z1mM0gL+p+lckmjhw52UtjJZv0hBD7LuGD/ACrp/wD3XP0NQMd7LuHnRTiLfmtwMB651NOXe291jKIhXyzSNSOcDofjUJu2F9xOSBMGJEGec6ddjyNRS640dl37vuqmdnyGi6qQ3iHshaCcNilb+W6pU/61n/tFUvjXZfF4OTfsMq/8RfFb/wBSyF9Gg1q1ntkh1YFfrHroCKXw/jOIYki5adCdANIEa6Rr86YzXu22W36IDo3A0TXr91iiNUgadPpWncb7DWsUGeyqYe9vCn7G4fNY+yPmumuoO9ZpjMHcs3DauIUdTBU7j+4O4I0I1FVxytkFj5pBYWmkW4ZcEgEDblUjF49VOXLEUMwV3JqSai3r2Zix50G2yncBVxhSMtOsa60mYxVygSEtEmBRJOHFQGImdjIj49PjUy3gMqyIIAmZ30k/KncDaLBlUyHGWeSkkRU8k4AsFWQ6QudtcD5J/A8JK6s0A8wNBt896NnFyjCRI8JOmo6+f/moPDUCHu7rwyiQRrJiQJ6R5VKxgULAB13OgnTX1rGmcXv72VvRMDI6ZhQ+E4hSpkgSYIPoSPXnp5USx3Cbb+IjMw0iY3Ej85jagNlFlginNlLCMxzRrly6+oOsRRjhfFJf7Qm28yDEAEAyCDsd67K1zXb2EooyHxmN4CnNiMxW57oCwVGmoBDR0iF+tMYTi9xsQS9wZAsuzbgeo1JGhEnrTnGMbcuOWQW2JGptDLcflmKyVYxzAG1BbOBztmziO8RXUjISr3AugnTrGkaUURYASSsyTRSh2BhWPFcYtYk5EdmYFSDJSRpJGm46EjlEnStKwdzPajvGBO6sQcpAgxm93QVktrH9291CoTxNbBSBlXXwehUST56cqLHtU1zJbULbVAFa5qxA2GYTtp5mhe7cK24+tqpmhMgBaR6+Hu+ytWP7PW2vrcdBnDKwuIcrQNfHyuCQIbfXlEmo9pbCYWwLNt2JvHxNcOZituCAdAIJPPeCNdqK8N4tcsq63kNy2mjBGy5VOk2yOWx08jVc4rg0V1v22uNbuSM1wKGkkmDk8JIaDoB6czLp4iXmz3W8N+fy8PkmywyQtvnzHHj8Uc7LsbCSRmnXU6FgCNuU+Lah1vib2b6uttEERqoOhnTNGh8/zqwYzCixiMPlIa06gajkdCfyoD2m8dzKo0EgegkTpz/uK40uEp39VkF5PKk9o2a4/eZCNRnH+WWhdBpm12P6cqD2gsZGaX8U6LlOUiTJDc4+O4q9vhh3qMr92CCbhJYhvD96TCjwzO+9ULtDilulGQtEGQ34pEnYbjL8ANBtWl2ebOEU8rTDtQY0g0s0hq2VmL1WpVNV016l208DT9i8V9OlRA9KF2hItdBpFsNiWRldGKspkEaEEbGi9+2uMU3bKhcQom7YUaXBzu2B15tb+Iqp98amYTGkMpkqymVZdCp5EUsx9QmCToV9A+xngIs4MYhh9piNZ6WwfAB66t8R0q4cZ4othersDlGvISSYBgVQ/Zr7QluhcLisqXYi24gJcH5A13bnHsb9xhr3QAynSRIBI66k/KpNXqDFF3f1E0qNLpxNNTuOVHxWPvMc7r3pYHLm5Ttl2gT0rihCIzFVI008Kk75iSNDpAkcjU/hWMscQt92j5XUSoaO9tnUaRo6cpHxFCbeLNrvMPiVcOhBnTI4BlfFpoTPI79a+eMMg7zvj1WrJqRW1goj4Uh+MsWrNs3Q+aSVdQCVIG7Kdp2PTc6Uxg+II2VGVDrvMMwaCobqRMUawWGwuKBw9yzdtspkqjBlzcyGiI8zGhFRu0PY+yoZzedLaS8xJUcwFE6VR7FpHePwU7dY8iiLUW9wdLr5bLhjB8MXB8iUgj8684hwD+Ctm7cxAS8R4LK+Kf6tfy0HXlUHg3bVLNlbVmyRdPv3WbMWE6ZemnwFEOKd3cRb5YHbMY2J1zfmPlXnF0Dg1w5VMbDMNwPd/PgneAdoC6gnQ+sg9YNFu0/Al4jYzIB/E2xNs/jG5tt1nl0PkTVf4KufOkKU5NzV9Auw0B6nTcb1YuA4kqy/WrdNqCXFpH9KHVQBmWn+1iz40DQj4c6jvjugqye1fhS4fiV3KIW8FvAdM85/+tXPxqmxWyGNWaZHJrcwKmdzlApPD7PM1JdcxC9aMmkDWkmgkYZWYSJPL9/CrPwa5bCAzqJLBhtruNPQ+tCruFVCLfMb+sCB8alW7AghpkMB89if3yrK1DhIF9Bo2mE3yU+cNN1yWICMSDyPPekcT4kWYAa6jQc42/8AFO452t4fICCxMEbFTmgkfiHLyqHdtKqkAqcv3pEsd9OunSlRsvvH0CKWZoO3j1+ivXBbiKjN3a2soM7AZTBJnzABPpXnG+HpesNCgto3nsDIMa6GhGCxF3FKlu14VRfHJ1I0gAjkf9tqtJQJbVVElUgEaDcafCNPhWHLcUgdfevjw9fVaVgjAws1e9etAJoYJytzAO8EGjOC4jobbW/EdJiCCBynmDPoTSxbu94QbWpnUgHSfuzsdT/ehvFly5vG0g6kmCWInaYGsfCtW2y00j4JQBiBPRd/FC8WzwHDA66ZtCvpMafAVK4dwZWu3JxASzbbxXCdWWYUpb1zE+XX4UDwWCuXWLhdNGJ20mJHx50fwBzutsoHb7qyQTqOYHODodN+tPkHsh3ePDwQ6aaKVpa80QbBxn44v1TVu8VWCxJgqCujd30dNiBy5jYSIANcPQLYUSHRr8hhqICgeeRiSBB10OlSrfZ27fOTu0w6ncTmdojTYAcz8OdHMZgLKABRk7sZSR+AaAEnQgsSfFMkzUrpgc9fJI1WpEcfsmO5N9Dx5j6WU1i8AyLbtF8y29iQJXcFZHL66VXeOcXsrcbPq+5RBzjmSNPjUPjXaNWzWrTnbS8qxJEkrE6Tp9oP9I3qqrb5n1Pn69TVMWj3ndIsN7vBTcbxO7eJJYqv4VOnx/FQnEW9D8x8P9pogV00qNlmfJWPyQmtKNrWCmhKOeUJIpLrTmWvMtUpKjlTXkVJy03cFdXkzXUrIa9Fs15eSacSkFaWgry8tZ4H2OTiXDbd/CEJirXguJMLcZdmH/DciDI0PPqDPBuHYi/YBxNs95ZJUzKues+ekHrVA9nfa9uG38xk2XgXVG8cmHmPyr6MtYpL1tb1qHDCQRzFQaiBsrdpVUU74nbmrDOG8BxL3s9sZFDEq85CqzK+f73rTrWIGITIboa8qn7RFBAMR4t11/SofGuC2MReV85ETns5iATvmyn3W66UpLKIVi7YUAyEDALP4iN3YdTpzrHkLt2TYHQcfXn6LQJa9vn9P4XqWEwtotlzMq+JlVQbjRyAA12/YrOb+FxfELzXEBIMQ5P2SgjUSfdjoBO+9aXieIYdrWaVuqDPhggka6zoY316eVVfhva+5iGuuLa2rFpTrJLux90A6BdNYA6a0bXFoLh0U2wucAqxx3gTYVUhldwPEFGo81nUieZAotwO+GwoVkJUtDZZzDo3wMa+k1WRxF1d87MXkzO5MnTXy60ewPECLaQGD21ls0KBMBT5jbffTrSp2PLReSDa2tOAG7b5S+zAVbt20CwDDRgsgw2jEchMfOrbgbBznrmPKOdU3sleOIxd027ZyiYkCLat/wBpmSAOnrWo8LwCr4mhUQSSdgBuSap08JMpcR0WfrZW7Q0G+qyv26EfxeHX7ww4n0Ny5H61mZFW7t/xb+Mxd2+PdnKn/tr4V+fvR/MaqhrcjNhY72lpypFnQCm7OIK3M3Sku9MJcI+O9dcLFLsbtrrCm47F52zagnf161Nw19g6HP4go57jX986CEzRTC2gYg8hrIn0FTSsa1tLQ00j3yWp3aS46hXJ1gqPTfnvz1qv2b5AA89Z6bA/nRDjN0sQn3U3OhJPPblQ2Old0zajAKVrnB0xrhW3hfGHuXMqMLebTozHlmfc6zvV34fgWWymd2zLGYFiFjWeYGmm+9Y/ZuwZGhqzYLtVcAC3YuKDJzbnpr5Vma7RPd/1rS0Wpi2hrsEdVe+LLbtnxAAN4Ug6htWLH4CPjVNxGF712YNAJWYglzyy6bjmTRXEYpb6JfN0lxMLAIE7+k7TT3B8IWzF2g5QJY89JAgbwByqCEmBhJOePn0WmYWubR4+q94fYs96mFYFf4hChuKYJZYZTOx1WDoAZ86hcJxIs8QN1Um2rZASYiCAzCdwDOnIGaNukAeQHu8jyn08qC3kKi5K/eDLpvoCrEen6U6HU7rvP59qU0mjaHkjjwWlYu+ttQ7e8TC6jxNrESY2J/01RO2PE7nd27d8KDdZrrR41QKSlhWCjxzDMQOZ8hUfHWnxCJcutcXIIGgjTQZQPdO09aXjsi4ZmuAO7iekE7N1nX869FK1jxQvNed+vCm/x9RlxORnyVZ4l3WebL5lIB/w2TKdohtTsDP83lUe2daULDlDcCOUG7BTlBmIJ2G4514tboWO7JtLO2tMHZz0Q/VlX9acb6UjE+GyTzuPlH9KasfQsVH/ACGuhAUMiuy1wNdVCSuIpk06RTRFeXEkmkkmvYriYry8kEUuzvTTUq01eK8E8zVb+wntAv8ADmy/4lgnxWydupQ8j5bVTXNJBodoKO19L4fiXDuLoGS7kvLsVOS6h3/5hPr8KEdo+w1+e8stnJEMFCiRzKgkZSeYBOvyrBbN5kIZWKsOYMGrhwb2ncQw8DvRcUcrgn671NLpWvNkff7J0eoczAPuVmw+GvW7b4Z7d62Gky1lgM0ggyTt6E7DrQPGcSt217i2Syg7BXBLTuQQCDPw0HSrRw723bC9hj6owP0MUZX2u8PPvC4p/ob9KkOiAPJVY1x52i1lGH4Vib9xlSxfK3DOY22POZnQfWrxw72c37gUXrzIg5aFyOUDZee5PpRjE+13BD3bd5z5KB/3MKGYj2su4Pc2Ft9GuEsf9Kx/3U0xZs8DySxqHkU0fNXzh/CMPgrJ921aXVmYxPmxO5rO+2vbn+K/9Nhcy2Jhm2a7003VBvG55xtVQ45xrE4pi1+81wA6D3UH9KDQeu/nQ+00bbkR6UYaAKCBrc27JXl5ZX1mhLrR9UhIO5P7+lCMRbg0+EpeoGQodyoxuVNMVFv2xuKepuEldTVi4ZgvsjcMAD7vM8tKr9toImrDwfFqujiU2GvWpdXuDe6tHs8NLzuKRiOGMVkMDIJJPhEAT6E+VRk4Y5Gm7NAA15TPWIq5W8MLbgpclFExod9Muuh15HpXmO4aMwIAYMPdUAQD0iANdfn1rPZ2hWCqNT2a/duZlUW5hGVsu5PSnLmGkKACDHvNoD6eVXnFcGtgBWcMqfeIIJ5yRPvSSP1pri3ClWy7wTC6MT8NKL/INJARRaB5ZudjyVJwHeZlmQsyfMfrWpcNVDaS5kPiI8XMyY+B0GgqicPvKCjES0QykaaH96Vaez+K7xhDlbafrsB9f3tN2lbxdVSu0DNja3Xat92xmIIBAAk7b6x/f5UJUBC3e6XANyBlIEmR+UcooxZdoI0yxp6n40C47issARM5S2kKI5k1gw2XbVW0E4KryY66bndEySW2IGmpgEfAU5xF27tBcXNl1yliARlX3o3Go2M+lP4a7ZDlrSl2gj1kFRA5azuahtiLdoQTnuZpA+6NAIPUaD6VsM/WC1vH1/ZDJXsiHnB6obxO9dLxceSoyALooWPdUCAF8gBUQL8ql3CWYs251nX4VHcxW2y9ovlfNSAbjXCQlsuwRYzMYE7DqT0AGpPQGoXE8Qr3PB/hoAieaifEfNmLMf6qnYy53SEf5lwa9UtHl5F/+3+qg4Wnxjqp3nova9Bror0Cmpa6mb1PgUQ4PwxbxOYxBED8U7jyjQ/Sge8MG4o44zI4NagdNuatuK7NZrjsGVC4LJbEkAkkDUDwrOu2g086EWuDAiCxznbaJjbz1igGojPVO/4ct1SDmkzRvGcANt1UvIJXMVAJWZzTruAJjnNDcbgWtBSxXxTAB1gRqRymdPT0pgkacApToXtFkJoNXtMg0sNRpdpYNe0kUqa4vJ6yKlprvUG3cinFumhIRtKn4hdBpT2GfQUPN8nczT1m7SnNwmtdlT3uZgRpy3/Sl2sPzJqIbsDSnLd1m3MD86Db4Jm7xUoEt8Nqj4mzJ0qQtcwom4SnHcUBsaik4tBAgUxg70GDtU2+nhqhToY1ELyBQpB3E+VQWWnsPjIADKGA67j0oHgnhOhcATaP8N422aGAaVy68/8Afzq2cLd8xUEHTqDA6Ty3is9cnKjQANdaI4TjxU6EBiIzDoOR+nyrK1Ok3juBbem1YGJHfyrvjsRbYfaBg4G0+XM6AiqPxXi8IbaEwZ0J5TpT2L4sWBYNLeW8xzPSq5dtNM0Wi0W3L17tDtCm7IjypWExxkSdFEAafGrDhuInCZXQhlcTB6+fpVQyHpSzdaINWzaZsmDx1Cy4NY6MHx8VpNrtDduWi+QZmMJEiBznr6edReM4rvbKFZXPBbXQmTr86qOFxbBQFZh5Rp+dSMzvAk5eQkx51nt7PDX2MZWoe02mOqsqVgeJ3LLeEkxOx0/3rrAI1YmfOkW7YX1pN3EaVc2JoNgZWZJqHvFOOB0UtsRSrl5bIzPBufctbxzD3eg6JuecDcN/FsT4AZ69PTp61yYdiZJ1O8nX400R+KQZCeF1y4WYsxJYmSTuSdya6Kk28H5/Skd2NYMx6Uywl0UyFpQWvSwH6a16p+FetcpWng/Zy0y27jXLbhwDkLhY8Izq2sg5s68vdnnorinc2shwylIGpk6uANRqY9ee9B+HX+5Y5kViNs06HkRBE/Guu45m0ELOhCiAZjesyVrzJk2FWyQNFAUVOxRXN4Wy6CGBjOQSZbXQEx5DSmMfb0zaeEbgnSYLT++dDbl7K0cqJG+t5rdpSxkwRlUEKNW1HvaAwTXQxzSPBVibukFQuHEOyIzMMzgB+hJAM9BB+tHOLWcOLdzCgeMOc17xQCAQfBG+o1FA8RdBJYIoQtpbOwB2E8tANjRLDcVFq4T3bgLoPEGI06kQRvy9daNwN2EyOi0hxVJvW8rEGRB570irPx/Dm4jXQoZiwzZV1AyyWjeBEExyk1WIq6N+9trJ1EJiftXoNKD0iKUENMSUvPU6zgmyhm8KnYnn6DnRPsxwlD9tdBZQ2VE/G2haeoEjQbkgVoFzsZ3t3vcRopAy21jwryDxoDH3RttUk+qZFymtYSLWWhVGwJrjcA+79TWyJwO1bhVsqo6wDUHiXArTqZQR1iCDUI7VjvLcLpjPisstX0nxBvzFFMPh2dDcTxIvvFdcoPNhuo8yIqbxrskbeo907MP16fKq3F2w4dWKsNmU6xsRpuDsRsa0I5GSi2FBuIOUYBpQqLhMWLk6AONwNj5r09OX5SU+FERSMG1UKm4XGQMraivK6npKk9yGGlMNgOldXUFoqUixgzlyk6EzHnTq8PUV7XUBJRgWpCYURpXj4Kva6g3G0yhSaOFFefwgrq6jsoCEtbYFL7+Nq6urlWvcBMd6XJCj16f70tcBr4vF5bD4CurqI44Q88qQto7KPgIFKuYMqCxPuESPIwPzrq6pJ5nNcGjrX1WlodMyRrnu6KZYtW3IKscsQ4ZdvQzqPhTjWMJcGTNdt3Ng0AoW21jxfSva6kN3OLu8cfmfFVaiKNmymjvHP8eCrmIt5SVI1UkfHY0Z4b2PxmJw5xNlFZPEB41BlTB0MfnXV1XvkIYHBYm0byE9xPg95e8uwO7GQHxTqU5TqRod/KhdgeMTXV1TtNg2rHRNa+wnccyxmHlp+/P86O+y7xY6CAVFp2Og0gAfka6uoq7hXpP1e5VDiFwlsvIGiODxDMhtsxy7g75T/b+wrq6jeO4ELHH2hRbDcPdBJWLbEBWzaFWPMDUyvWNvhVW4mgDaR8AR8+vr5V1dQac99U6toMN+CiClA11dVqx1snYjggWxYusAQLQKj+ZizE+v+3SrNibhNdXV8priTKVYuS2WpzE2gVJiQNCOfzrq6pQMLqGYvCd4hAjLtFUTjnAFSQsmdRJGw0Irq6qNHI5rsFA9oIyqTikNtwymNZHkaPG3Nu3dAhbqkjyKsVcfAjTyIr2ur6cm2gpEa//Z" alt="">
      <img src="https://www.investopedia.com/thmb/ZxELD8YzG2qU7WiYVal8QjJ3Xcc=/1500x844/smart/filters:no_upscale()/GettyImages-1034323548-0e7ece8590ab48dc97e9016fdfa3a6dd.jpg" alt="">
      <img src="https://cdn.touchbistro.com/wp-content/uploads/2020/01/food-presentation-tips-inset-3.jpg" alt="">
      <img src="https://www.qsrmagazine.com/sites/default/files/styles/story_page/public/story/why-lawsuits-are-taking-aim-quick-service-meal-pricing.jpg?itok=TIEv5om2" alt="">
      <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTETl9ZchpnexBqEZmb-N8z3WMaGrPU6hQftg&usqp=CAU" alt="">
      <img src="https://th.bing.com/th/id/Rb6d0993e6b85bd0ed9fbeea8c00628ba?rik=F4GbNayOHzjmYA&riu=http%3a%2f%2fnopalitosrestaurants.com%2fwp-content%2fuploads%2f2017%2f12%2frestaurant2-inside1.jpg&ehk=D7ERv%2bhe7FQAaGm6NFnVCFd0PLLff3hWB9p8oB0wqoc%3d&risl=&pid=ImgRaw" alt="">
      <img src="https://media-cdn.tripadvisor.com/media/photo-s/06/b7/23/17/restaurant.jpg" alt="">
    </section>
  </div>

  <script>
    const navButton = document.querySelector('button[aria-expanded]');

    function toggleNav({ target }) {
      const expanded = target.getAttribute('aria-expanded') === 'true' || false;
      navButton.setAttribute('aria-expanded', !expanded);
    }

    navButton.addEventListener('click', toggleNav);
  </script>

</body>

</html>
