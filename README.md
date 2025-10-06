import React,{useState} from 'react';
import Pic1 from './duran.png' 
import Pic2 from './boston.png'
import Pic3 from './abba.png'

function Test(){

  //set states to 0 
const [countD, setDCount] = useState(0);
const [countB, setBCount] = useState(0);
const [countA, setACount] = useState(0);

//amount of items 
const dStock = 10;
const bStock = 4;
const aStock = 6;

//total
const total = (countD * 1170) + (countB * 350) + (countA * 800); 

//if no items in cart 
const errorHandle = () =>{
  if (total === 0){
    window.alert("Please Fill Your Cart");
    return;
  }
//items in the cart
  let cartTotal = "This is your cart and the Items";
  if (countD > 0) cartTotal += `Duran Duran = ${countD}`;
  if (countB > 0) cartTotal += `Boston = ${countB}`;
  if (countA > 0) cartTotal += `ABBA = ${countA}`;
  cartTotal += `Your total is : R${total}` ;
  alert(cartTotal);
};

  return(
    <div style={{padding : 20, 
    background:'linear-gradient(90deg, #5e0f0fff, #072744ff )'
    }}>
      <header> {/*This is the useless nav */}
        <div>
          <h1 style={{color : 'white', 
            padding : 20, 
            display : 'flex', 
            justifyContent : 
            'center', 
            alignItems : 'center'}} >🎵Keshav's Music Shop🎵</h1>
        </div>
          {/*this is the nav bar */}
          <div>
            <nav style={{ margin: -30,
              background:'linear-gradient(90deg, #5e0f0fff, #072744ff  )',
               display : 'flex', justifyContent : 'center', alignItems : 'center'}}>
              <ul style={{listStyleType :'none', 
                display : 'flex', justifyContent : 'center', alignItems : 'center'}}>
                <li style={{cursor: 'pointer', 
                  display: 'inline-block', 
                  margin: 20, padding : 
                  50, background: 
                  'linear-gradient(-90deg, #e01919ff, #0b3962ff)', 
                  borderRadius: 20, borderWidth : 20, display : 'block'}}><a style={{textDecoration: 'none',color: 'white'}} href='#home'>Home</a></li>
                <li style={{cursor: 'pointer',
                   display: 'inline-block', 
                   margin :20, 
                   padding : 50, 
                   background: 'linear-gradient(-90deg, #e01919ff, #0b3962ff )', 
                   borderRadius: 20, borderWidth : 20, display : 'block'}}><a style={{textDecoration: 'none',color: 'white'}} href='#products'>Products</a></li>
                <li style={{cursor: 'pointer', 
                  display: 'inline-block', 
                  margin :20, 
                  padding : 50, 
                  background: 'linear-gradient(-90deg, #e01919ff, #0b3962ff )',
                   borderRadius: 20, 
                   borderWidth : 20, 
                   display : 'block',}}><a style={{textDecoration: 'none',color: 'white'}} href='#about'>About Us</a></li>
                <li style={{cursor: 'pointer', 
                  display: 'inline-block', 
                  margin :20, 
                  padding : 50, 
                  background: 'linear-gradient(-90deg, #e01919ff, #0b3962ff)', 
                  borderRadius: 20, borderWidth : 20, display : 'block'}}><a style={{textDecoration: 'none',color: 'white'}} href='#contact'>Contact</a></li>
              </ul>
            </nav>
          </div>
      </header>

      <hr></hr>
        <section className='products'>
          <h2 style={{color : 'white', padding : 20, display : 'flex', justifyContent : 'center', alignItems : 'center'}} id='products'>Products For Sale.</h2>
        </section>

     {/* this is the product card*/} 
        <div style={{width : 700,background : "linear-gradient(65deg, red, green)",border : 'solid black 5px', padding : 20}}>
          <div>
            <h2 style={{color : 'white'}}>Duran Duran : Back to future Album : R1170</h2>
            <h3 style={{color : 'white'}}>There is : {dStock} Avaliable</h3> {/*find img and all  */}
            <img src={Pic1}></img> {/*insert the differnt imgs when doing CSS then kill the comment*/}
          </div>
          <div>
            <button onClick={() => countD < dStock && setDCount(countD + 1)} 
            style={{border : 'black solid 4px', position : 'absolute', right : 1050, top : 600, 
            background : 'linear-gradient(135deg, red, green)', color : 'white', height : 50, fontSize : 30, width : 100}}>Add</button>{/*add button*/}

            <button onClick={() => countD > 0 && setDCount(countD - 1)} 
            style={{border : 'black solid 4px', position : 'absolute', right : 900, top : 600, 
            background : 'linear-gradient(135deg, red, green)', color : 'white', height : 50, fontSize : 30, width : 120}}>Deduct</button>{/*delete button*/}

            <h3 style={{color : 'white'}}>This is how many you have in your cart : {countD}</h3>
          </div> 
        </div>
        <br></br>
      {/* this is the product card come*/}
      <div>
        <div style={{width : 700,background : "linear-gradient(65deg, #ff7700ff, black, blue)",border : 'solid black 5px', padding : 20}}> 
          <div>
             <h2 style={{color : 'white'}}>Boston : Boston Album : R350</h2>
             <h3 style={{color : 'white'}}>There is : {bStock} Avaliable</h3>
            <img src={Pic2}></img> {/*insert the differnt imgs when doing CSS then kill the comment*/}
          </div>
          <div>
            <button onClick={() => countB < bStock && setBCount(countB + 1)} 
            style={{border : 'black solid 4px', position : 'absolute', right : 1050, top : 1060, 
            background : 'linear-gradient(75deg, #ff7700ff, black, blue)', color : 'white', height : 50, fontSize : 30, width : 100}}>Add</button>{/*add button*/}

            <button onClick={() => countB > 0 && setBCount(countB - 1)} 
            style={{border : 'black solid 4px', position : 'absolute', right : 900, top : 1060,
             background : 'linear-gradient(135deg, #ff7700ff, black, blue)', color : 'white', height : 50, fontSize : 30, width : 120}}>Deduct</button>{/*delete button*/}

            <h3 style={{color : 'white'}}>This is how many you have in your cart : {countB}</h3>
          </div>
        </div>
      </div>

        <br></br>
       {/* this is the product card*/}
        <div style={{width : 700,background : "linear-gradient(65deg, #C24B33, #FFE48C, #E7D60A)",border : 'solid black 5px', padding : 20}}>
          <div>
             <h2>ABBA 2 for 1 special : Lay all Your Love on Me and Abba Albums : R800</h2>
             <h3>There is : {aStock} Avaliable</h3>
            <img src={Pic3}></img> 
          </div>
          <div>
            <button onClick={() => countA < aStock && setACount(countA + 1)} 
            style={{border : 'black solid 4px', position : 'absolute', right : 1050, top : 1550, 
            background : 'linear-gradient(75deg, #C24B33, #FFE48C, #E7D60A)', color : 'black', height : 50, fontSize : 30, width : 100}}>Add</button>{/*add button*/}

            <button onClick={() => countA > 0 && setACount(countA - 1)} 
            style={{border : 'black solid 4px', position : 'absolute', right : 900, top : 1550, 
            background : 'linear-gradient(135deg,  #C24B33, #FFE48C, #E7D60A)', color : 'black', height : 50, fontSize : 30, width : 120}}>Deduct</button> {/*delete button*/}

            <h3>This is how many you have in your cart : {countA}</h3>
          </div>
        </div>

<br></br>

{/*the cart model*/}
      <div style={{padding : 20, border : 'black solid 3px' , width : 350, background : 'linear-gradient(90deg , green, blue )'}}>
        <h3 style={{color : 'white'}}>Price Counter.</h3>
        <h4 style={{color : 'white'}}>Total : R{total}</h4> {/*set to change over time */}
       {/*and also alert in time */}
        <button style={{border : 'black solid 4px', position : 'absolute', right : 1150, top : 1900, 
          background : 'linear-gradient(90deg, blue, green)', color : 'white', height : 50, fontSize : 20, width : 120}}
          onClick={errorHandle}>Order Now</button>
      </div> 
    </div>    
    
  )
}

export default Test; 
