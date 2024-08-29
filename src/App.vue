<script setup>
import { ref } from 'vue';

// Use ref to make dynamicDate reactive in the template
const dynamicDate = ref('');

let d = new Date();
const daysNames = ['Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
const monthsNames = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December'];

let dayName = daysNames[d.getDay()];
let dayNumber = d.getDate();
let monthName = monthsNames[d.getMonth()];
let year = d.getFullYear();

dynamicDate.value = `${dayName} ${dayNumber} ${monthName} ${year}`;
</script>

<template>
  <div class="sm-navBar">
    <div class="logo"></div>
    <div class="date">
      <h3 id="dynamicDate">{{ dynamicDate }}</h3>
    </div>
    <!-- toggle switch container -->
    <div class="right">
      <p id="switch">check the code</p>
      <a href="https://elkhechafi.github.io/img-to-webP-converter/" target="_blank" rel="noopener noreferrer">
      <div class="circle-bg">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="50" height="50" viewBox="0 0 24 24">
          <path d="M10.9,2.1c-4.6,0.5-8.3,4.2-8.8,8.7c-0.5,4.7,2.2,8.9,6.3,10.5C8.7,21.4,9,21.2,9,20.8v-1.6c0,0-0.4,0.1-0.9,0.1 
              c-1.4,0-2-1.2-2.1-1.9c-0.1-0.4-0.3-0.7-0.6-1C5.1,16.3,5,16.3,5,16.2C5,16,5.3,16,5.4,16c0.6,0,1.1,0.7,1.3,1 
              c0.5,0.8,1.1,1,1.4,1c0.4,0,0.7-0.1,0.9-0.2c0.1-0.7,0.4-1.4,1-1.8c-2.3-0.5-4-1.8-4-4c0-1.1,0.5-2.2,1.2-3
              C7.1,8.8,7,8.3,7,7.6c0-0.4,0-0.9,0.2-1.3C7.2,6.1,7.4,6,7.5,6c0,0,0.1,0,0.1,0C8.1,6.1,9.1,6.4,10,7.3C10.6,7.1,11.3,7,12,7
              s1.4,0.1,2,0.3c0.9-0.9,2-1.2,2.5-1.3c0,0,0.1,0,0.1,0c0.2,0,0.3,0.1,0.4,0.3C17,6.7,17,7.2,17,7.6c0,0.8-0.1,1.2-0.2,1.4
              c0.7,0.8,1.2,1.8,1.2,3c0,2.2-1.7,3.5-4,4c0.6,0.5,1,1.4,1,2.3v2.6c0,0.3,0.3,0.6,0.7,0.5c3.7-1.5,6.3-5.1,6.3-9.3
              C22,6.1,16.9,1.4,10.9,2.1z"></path>
        </svg>
      </div>
      </a>
      <a href="https://www.linkedin.com/in/elkhechafi" target="_blank" rel="noopener noreferrer">
      <div class="circle-bg">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="50" height="50" viewBox="0 0 30 30">
          <path d="M24,4H6C4.895,4,4,4.895,4,6v18c0,1.105,0.895,2,2,2h18c1.105,0,2-0.895,2-2V6C26,4.895,25.105,4,24,4z M10.954,22h-2.95
              v-9.492h2.95V22z M9.449,11.151c-0.951,0-1.72-0.771-1.72-1.72c0-0.949,0.77-1.719,1.72-1.719c0.948,0,1.719,0.771,1.719,1.719
              C11.168,10.38,10.397,11.151,9.449,11.151z M22.004,22h-2.948v-4.616c0-1.101-0.02-2.517-1.533-2.517c-1.535,0-1.771,1.199-1.771,2.437
              V22h-2.948v-9.492h2.83v1.297h0.04c0.394-0.746,1.356-1.533,2.791-1.533c2.987,0,3.539,1.966,3.539,4.522V22z"></path>
        </svg>
      </div>
      </a>
      <div class="circle">
        <img src="./../public/world-wide-web.png" alt="website-icon" class="website-icon" height="auto">
      </div>
    </div>
    <!-- close toggle switch container -->
  </div>

  <nav class="sideBar">
    <ul class="pageNames">
      <RouterLink to="/" class="pageName" activeClass="active">Img converter</RouterLink>
      <RouterLink to="/WebpAdvantages" class="pageName" activeClass="active">Advantages</RouterLink>
    </ul>
  </nav>

  <RouterView />
</template>

<style scoped lang="scss">
  .sm-navBar{
    position: fixed;
    display: inline-flex;
    justify-content: space-between;
    align-items: center;
    top: 0%;
    height: 10vh;
    width: 100%;
    background-color: var(--bg-color);
    box-shadow: 0px 7px 19px 3px rgba(0, 0, 0, 0.25);
    transition: 750ms ease-in-out;
    .logo{
        padding: 1em;
        height: 80%;
        width: 10%;
        path{
            fill: none;
            transition: 800ms ease-in-out;
        }
    }
    .date{
        padding-top: 2%;
        text-align: center;
        width: max-content;
        height: 100%;
        color: var(--text-color);
        font-size: 1.3rem;
        font-weight: bolder;
        border-bottom: 2px solid #E8986A;
        transition: 750ms ease-in-out;
    }
    .right{
        padding-right: 5%;
        width: 30%;
        height: 100%;
        right: 0vw;
        border-bottom: 3px solid #E8986A;
        color: var(--text-color);
        display: inline-flex;
        justify-content: space-evenly;
        align-items: center;
        transition: 750ms ease-in-out;
        #switch{
            width: max-content;
            margin-top: 10%;
            height: 80%;
            right: 0vw;
            color: var(--text-color);
            font-size: 1rem;
            padding-top: 2%;
            padding-right: 5%;
            z-index: 5;
            &::before{
                content: '';
            }
        }
        .circle-bg{            
            height: 5vh;
            width: 10%!important; 
            border-radius: 25%; 
        }
        .circle{
            height: 5vh;
            width: 10%; 
            border-radius: 50%; 
            box-shadow: var(--card-shadow);
            display: inline-flex;
            justify-content: center;
            align-items: center;
            svg{
              width: 90%;
              height: 90%;
            }
            .website-icon{
              width: 100%;
              height: 5vh;
              margin: auto;
            }
        }
        .account{
          padding: 3% 2%;
          svg{
            path{
              fill: var(--bg-color-reverse);
            }
          }
        }
    }
    
    
}

.sideBar{
    height: 90vh;
    width: 10vw;
    position: fixed;
    top: 10vh;
    left: 0%;
    background-color: var(--bg-color);
    box-shadow: 0px 7px 19px 3px rgba(0, 0, 0, 0.25);
    transition: 750ms ease-in-out;
    display: inline-flex;
    justify-content: space-between;
    align-items: flex-end;
    flex-direction: column;
    .pageNames{
        display: inline-flex;
        justify-content: space-evenly;
        align-items: flex-end;
        flex-direction: column;
        list-style: none;
        margin-top: 10vh;
        width: 100%;
        height: 50%;
        color: var(--text-color);
        text-align: right;
        .pageName{
            text-align: right;
            padding-right: 2vw;
            width: 100%;
        }
        .active{
            background-color: var(--bg-color);
            margin-right: -10%;
            width: 80%;
            padding: 5% 5% 5% 0%;
            color: #E8986A;
            box-shadow: -15px 0px 8px 3px rgba(0, 0, 0, 0.25);

        }
    }
    footer{
        width: 100%;
        height: 15%;
        box-shadow: 0px 7px 19px 3px rgba(0, 0, 0, 0.25);
        background-color: var(--bg-color-reverse);
        border-radius: 25% 0% 30% 0vw;
        display: inline-flex;
        justify-content: center;
        align-items: center;
        font-size: 1em;
        color: var(--text-color);
    }
}

@media only screen and (max-width: 600px) {
  .sm-navBar{
        position: fixed;
        display: inline-flex;
        justify-content: space-between;
        align-items: center;
        top: 0%;
        height: 10vh;
        width: 100%;
        background-color: var(--bg-color);
        box-shadow: 0px 7px 19px 3px rgba(0, 0, 0, 0.25);
        transition: 750ms ease-in-out;
        .logo{
            padding: 1em;
            height: 80%;
            width: 25%;
            path{
                fill: var(--logo-fill);
                transition: 800ms ease-in-out;
            }
        }
        .date{
            display: none;
        }
        .right{
            padding-right: 5%;
            width: 60%;
            height: 100%;
            right: 0vw;
            border-bottom: 3px solid #E8986A;
            color: var(--text-color);
            display: inline-flex;
            justify-content: space-between;
            align-items: center;
            transition: 750ms ease-in-out;
            #switch{
                display: none;
                width: max-content;
                margin-top: 10%;
                height: 80%;
                right: 0vw;
                color: var(--text-color);
                font-size: 1rem;
                padding-top: 2%;
                padding-right: 5%;
                z-index: 5;
                &::before{
                    content: '';
                }
            }
            .circle-bg{            
                height: 4vh;
                width: 15%!important; 
                border-radius: 50%; 
                background-color: var(--card-bg);
                background-color: var(--bg-color-reverse);
            }
            .circle{
                height: 4vh;
                width: 15%; 
                border-radius: 50%; 
                background-color: var(--card-bg);
                box-shadow: 1px 2px 4px 2px #0000004d;
                &.account{
                  svg{
                    path{
                      fill: var(--bg-color-reverse);
                    }
                  }
                }
            }
        }
        
    }

    .sideBar{
        top: 90vh;
        height: 10vh;
        width: 100vw;
        position: fixed;
        bottom: 0%;
        left: 0%;
        background-color: var(--bg-color);
        box-shadow: 0px 7px 19px 3px rgba(0, 0, 0, 0.25);
        transition: 750ms ease-in-out;
        display: inline-flex;
        justify-content: space-between;
        align-items: flex-end;
        z-index: 999;
        .pageNames{
            display: inline-flex;
            justify-content: space-evenly;
            align-items: center;
            flex-direction: row;
            list-style: none;
            margin-top: 0%;
            width: 100%;
            height: 100%;
            padding: 0%;
            .pageName{
                padding: 0%;
                text-align: center;
                width: max-content;
            }
            .active{
                box-shadow: none;
                color: #E8986A;
                background-color: none;
                margin-right: 0%;
                padding: 0%;
    
            }
        }
        footer{
            display: none;
        }
      }
}
</style>
