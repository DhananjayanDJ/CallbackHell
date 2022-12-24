<!DOCTYPE html>
<html lang="en">
  
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" 
        content="IE=edge">
    <meta name="viewport" content=
        "width=device-width, initial-scale=1.0">
  
    <title>Callback Hell</title>
      
    <style>
        * {
            padding: none;
            margin: none;
            box-sizing: border-box;
        }
  
        .word {
            color: #308d46;
            font-size: 4rem;
            transition: all .5s ease-in;
            margin: 0 5px;
            transform: translateY(3.8rem);
            opacity: 0;
        }
  
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            width: 95vw;
            height: 95vh;
        }
  
        .container {
            overflow: hidden;
            display: flex;
            flex-direction: row;
        }
  
        .animate {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
  
<body>
    <div class="container">
        <h2 class="word">DJ</h2>
        <h2 class="word">Ice</h2>
        <h2 class="word">Saran</h2>
    </div>
</body>
<script>
    let words = document.querySelectorAll(".word");
  
    const animateAll = (animate) => {
        setTimeout(() => {
            animate(words[0]);
            setTimeout(() => {
                animate(words[1]);
                setTimeout(() => {
                    animate(words[2]);
                }, 1000)
            }, 1000)
        }, 1000)
    }
  
    const animate = (word) => {
        word.classList.add("animate");
    }
  
    animateAll(animate);
</script>
  
</html>
