# assaignment-four
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Flight Booking</title>
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Roboto:wght@400;500;700&display=swap"
        rel="stylesheet">
    <!-- Stylesheet -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">
    <link rel="stylesheet" href="style.css">
    
</head>

<body>
    <!--Header and Menu Section-->
    <header class="container">
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About Us</a></li>
                <li><a href="#">Contact</a></li>
                <li><a class="active" href="#">Sign Up</a></li>
            </ul>
        </nav>
    </header>

    <!--Booking Section-->
    <main class="main-content container">
        <div class="booking-form">
            <h3>Booking Flights</h3>
            <div class="input-group">
                <label for="">Flying From</label>
                <input class="inp-style" type="text" name="" placeholder="Dhake, Bangladesh">
            </div>
            <div class="input-group">
                <label for="">Flying To</label>
                <input class="inp-style" type="text" name="" placeholder="New York, United States">
            </div>
            <div class="inputs">
                <div class="input-group">
                    <label" for="">Departure</label>
                    <input class="inp-style" type="date" name="">
                </div>
                <div class="input-group">
                    <label for="">Return</label>
                    <input class="inp-style" type="date" name="">
                </div>
            </div>
            <div class="input-group f-class">
                <!--working place-->
                <div>
                    <label for="">First Class ($150)</label>
                    <input class="inp-style inp-width" type="number" name="" id="first-quantity">
                </div>
                <div class="plus-minus-btn">
                    <div class="plus-minus-btn" >
                        <p> <span><button onclick="handlerproductchange(true)" >+</button></span>
                             <span><button onclick="handlerproductchange(false)">-</button></span> </p>
                    </div>
                  
                </div>
            </div>
            
            <div class="input-group f-class">
                <div>
                    <label for="">Economy ($100)</label>
                    <input class="inp-style inp-width" type="number" name="" id="sec-quantity" >
                </div>
                <div class="plus-minus-btn" >
                    <p> <span><button onclick="handlerticketchange(true)" >+</button></span>
                         <span><button onclick="handlerticketchange(false)" >-</button></span> </p>
                </div>
            </div>
            <div class="calculations">
                <div class="amount">
                    <div class="left">
                        <p>Subtotal</p>
                    </div>
                    <div class="right">
                        <p id="sub-total">$0</p>
                    </div>
                </div>

                <div class="amount">
                    <div class="left">
                        <p>Charge 10% VAT</p>
                    </div>
                    <div class="right">
                        <p id="tax-amount">$50</p>
                    </div>
                </div>
                <hr>
                <div class="amount">
                    <div class="left">
                        <h4>Total</h4>
                    </div>
                    <div class="right">
                        <p id="final-amount">$550</p>
                    </div>
                </div>
            </div>
            <button class="btn-style">Book Now</button>
        </div>

        <div class="booking-content">
            <h1>discover <br> around the world</h1>
            <p>Lorem ipsum dolor sit amet consectetur adipisicingelit. Provident voluptatibus quam fuga laborumalias veniam libero autem quasi maxime ullam vero nama imi dolor, architecto ab facilis eaque deserunt nobise voluptatibus quam</p>
        </div>
    </section>

    <!--Thank You-->
</body>
<script>

//firstclass ticket start//
function handlerproductchange(isIncrease){
        const firstQuantity =document.getElementById("first-quantity").value;
     const firstqUantity = parseInt(firstQuantity);
     
     let finalfirstQuantity = firstqUantity;
     if(isIncrease == true) {
        finalfirstQuantity = firstqUantity+1;
     }
     if (isIncrease == false && finalfirstQuantity > 0 ) {
        finalfirstQuantity = firstqUantity-1;
     }
     document.getElementById("first-quantity").value = finalfirstQuantity
     calculateSubtotal();
    
    };
   //done firstclass ticket// 
    
    
//economyclass ticket start//

function handlerticketchange(isIncrease){
    const secQuantity =document.getElementById("sec-quantity").value;
    const secqUantity = parseInt(secQuantity);
    
    let finalsecQuantity = secqUantity;
    if(isIncrease==true){
        finalsecQuantity = secqUantity + 1;
    }
    if(isIncrease==false && secqUantity > 0 ){
        finalsecQuantity = secqUantity - 1;
    }
    document.getElementById("sec-quantity").value = finalsecQuantity;
    calculateSubtotal();
    
}
//economy class ticket done//


/* subtotal + charge + total*/
    function calculateSubtotal(){
       const firstClass = document.getElementById("first-quantity").value;
     const firstClassInput = parseInt(firstClass);
    

     const ecoClass = document.getElementById("sec-quantity").value;
     const ecoClassInput = parseInt(ecoClass);
    
    const totalSubTotal = firstClassInput * 150 + ecoClassInput * 100;
    document.getElementById("sub-total").innerText =  totalSubTotal;


    const tax = document.getElementById("tax-amount").innerText;
     const Tax = parseInt(tax);
     const totalTax = totalSubTotal * 0.1;
     document.getElementById("tax-amount").innerText = totalTax;

     const finalAmount = document.getElementById("final-amount").innerText;
const finalPrice = parseInt(finalAmount);
const finalMoney =totalTax + totalSubTotal;
document.getElementById("final-amount").innerText = finalMoney;
    }
//everything done//

</script>

</html>
