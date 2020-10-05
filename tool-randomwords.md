---
title: Random Word Generator
players: 3+
equipment: standard deck, no jokers
---


<button  onclick='generateWord()'>Generate Word</button>



<script>
    function rD(i){return i[Math.floor(Math.random()*i.length)];} //draw a random item from a list.

    wordList = ['River', 'Train', 'Beautiful', 'Chip', 'Ant', 'Table', 'Firefighter', 'Hammer', 'Banana', 'Wedding', 'Shakespeare', 'Rodeo', 'Antarctica', 'Melt', 'Fireworks', 'Muscle', 'Heart', 'Ski', 'Cloud', 'Canoe', 'Cough', 'Waffle', 'Horse', 'Lamp', 'Soldier', 'Brush', 'Angel', 'Halloween', 'Voyage', 'Rollercoaster', 'England', 'Ring', 'Chalk', 'Nose', 'Ribbon', 'Tropical', 'Ocean', 'Space', 'Boil', 'Wild', 'Turtle', 'Kitchen', 'Actor', 'Cup', 'Ketchup', 'Playground', 'Hero', 'Strike', 'Mexico', 'Oatmeal', 'Camping', 'Slippers', 'North', 'Peel', 'Tree', 'Bicycle', 'Sticky', 'Short', 'Dolphin', 'Bathtub', 'Chef', 'Bat', 'Doughnut', 'Vacation', 'Mug', 'Fence', 'Canada', 'Crawl', 'Machine', 'Tower', 'Maze', 'Pop', 'Flower', 'Cart', 'Tiny', 'Castle', 'Bear', 'Couch', 'Doctor', 'Glove', 'Coffee', 'July Fourth', 'Ghost', 'Thumb', 'Pyramid', 'Fly', 'Cookie', 'Cabin', 'Hawaii', 'Horn', 'Rock', 'Whisky', 'Eagle', 'Blue', 'owl', 'Refrigerator', 'Teacher', 'Ball', 'Pretzel', 'Airport', 'Brother', 'Sky', 'China', 'Trip', 'Danger', 'Eye', 'Equipment', 'Burger', ]


    //test a more complicated version which includes english and chinese translations.


    critterWords = [
        {english:"Horse", chinese:"马",  symbol:"🐎\uFE0F"},
        {english:"Chicken", chinese:"鸡",  symbol:"🐓\uFE0F"},
        {english:"Dog", chinese:"狗",  symbol:"🐩\uFE0F"},
        {english:"Pig", chinese:"猪",  symbol:"🐖\uFE0F"},
        {english:"Monkey", chinese:"猴",  symbol:"\uFE0F"},
        {english:"Penguin", chinese:"企鹅",  symbol:"\uFE0F"},
        {english:"Duck", chinese:"鸭",  symbol:"\uFE0F"},
        {english:"Peacock", chinese:"",  symbol:"\uFE0F"},
        {english:"Owl", chinese:"",  symbol:"\uFE0F"},
        {english:"Bat", chinese:"",  symbol:"\uFE0F"},
        {english:"Unicorn", chinese:"",  symbol:"\uFE0F"},
        {english:"Bee", chinese:"",  symbol:"\uFE0F"},
        {english:"Caterpillar", chinese:"",  symbol:"\uFE0F"},
        {english:"Butterfly", chinese:"",  symbol:"\uFE0F"},
        {english:"Snail", chinese:"",  symbol:"\uFE0F"},
        {english:"Shell", chinese:"",  symbol:"\uFE0F"},
        {english:"Beetle", chinese:"",  symbol:"\uFE0F"},
        {english:"Ant", chinese:"",  symbol:"\uFE0F"},
        {english:"Spider", chinese:"",  symbol:"\uFE0F"},
        {english:"Web", chinese:"",  symbol:"\uFE0F"},
        {english:"Scorpion", chinese:"蝎",  symbol:"\uFE0F"},
        {english:"Mosquito", chinese:"蚊子",  symbol:"\uFE0F"},
        {english:"Bacteria", chinese:"菌",  symbol:"🦠\uFE0F"},
        {english:"Turtle", chinese:"龟",  symbol:"🐢\uFE0F"},
        {english:"Snake", chinese:"蛇",  symbol:"🐍\uFE0F"},
        {english:"Lizard", chinese:"",  symbol:"🦎\uFE0F"},
        {english:"Dinosaur", chinese:"",  symbol:"🦖\uFE0F"},
        {english:"Octopus", chinese:"",  symbol:"🐙\uFE0F"},
        {english:"Shrimp", chinese:"虾",  symbol:"🦐\uFE0F"},
        {english:"Crab", chinese:"",  symbol:"🦀\uFE0F"},
        {english:"Pufferfish", chinese:"",  symbol:"🐡\uFE0F"},
        {english:"Fish", chinese:"鱼",  symbol:"🐠\uFE0F"},
        {english:"Dolphin", chinese:"",  symbol:"🐬\uFE0F"},
        {english:"Shark", chinese:"",  symbol:"🦈\uFE0F"},
        {english:"Alligator", chinese:"",  symbol:"🐊\uFE0F"},
        {english:"Tiger", chinese:"虎",  symbol:"🐅\uFE0F"},
        {english:"Gorilla", chinese:"",  symbol:"🦍\uFE0F"},
        {english:"Elephant", chinese:"象",  symbol:"🐘\uFE0F"},
        {english:"Rhinoceros", chinese:"",  symbol:"🦏\uFE0F"},
        {english:"Hippopotamus", chinese:"河马",  symbol:"🦛\uFE0F"},
        {english:"Camel", chinese:"",  symbol:"🐫\uFE0F"},
        {english:"Llama", chinese:"",  symbol:"🦙\uFE0F"},
        {english:"Giraffe", chinese:"",  symbol:"🦒\uFE0F"},
        {english:"Cattle", chinese:"",  symbol:"\uFE0F"},
        {english:"Sheep", chinese:"",  symbol:"\uFE0F"},
        {english:"Goat", chinese:"",  symbol:"\uFE0F"},
        {english:"Deer", chinese:"鹿",  symbol:"\uFE0F"},
        {english:"Housecat", chinese:"猫",  symbol:"\uFE0F"},
        {english:"Rabbit", chinese:"",  symbol:"🐇\uFE0F"},
        {english:"Rat", chinese:"鼠",  symbol:"🐀\uFE0F"},
        {english:"Squirrel", chinese:"松鼠",  symbol:"🐿\uFE0F"},
        {english:"Hedgehog", chinese:"刺猬",  symbol:"🦔\uFE0F"},
        {english:"Dragon", chinese:"龙",  symbol:"🐉\uFE0F"},
    ]

    natureWords = [
        {english:"Cactus", chinese:"",  symbol:"🌵\uFE0F"},
        {english:"Tree", chinese:"",  symbol:"🌲\uFE0F"},
        {english:"Seed", chinese:"",  symbol:"🌱\uFE0F"},
        {english:"Spring", chinese:"",  symbol:"💐\uFE0F"},
        {english:"Summer", chinese:"",  symbol:"☀️\uFE0F"},
        {english:"Winter", chinese:"",  symbol:"❄️\uFE0F"},
        {english:"Fall", chinese:"",  symbol:"🍂\uFE0F"},
        {english:"Flower", chinese:"",  symbol:"🌺\uFE0F"},
        {english:"Leaf", chinese:"",  symbol:"🍁\uFE0F"},
        {english:"Mushroom", chinese:"",  symbol:"🍄\uFE0F"},
        {english:"Sun", chinese:"",  symbol:"🌞\uFE0F"},
        {english:"Moon", chinese:"",  symbol:"🌜\uFE0F"},
        {english:"Earth", chinese:"",  symbol:"🌏\uFE0F"},
        {english:"Star", chinese:"",  symbol:"⭐️\uFE0F"},
        {english:"Lightning", chinese:"",  symbol:"🌩\uFE0F"},
        {english:"Electricity", chinese:"",  symbol:"⚡️\uFE0F"},
        {english:"Storm", chinese:"",  symbol:"⛈\uFE0F"},
        {english:"Comet", chinese:"",  symbol:"☄️\uFE0F"},
        {english:"Fire", chinese:"",  symbol:"🔥\uFE0F"},
        {english:"Tornado", chinese:"",  symbol:"🌪\uFE0F"},
        {english:"Rainbow", chinese:"",  symbol:"🌈\uFE0F"},
        {english:"Clouds", chinese:"",  symbol:"☁️\uFE0F"},
        {english:"Snow", chinese:"",  symbol:"🌨\uFE0F"},
        {english:"Snowman", chinese:"",  symbol:"☃️\uFE0F"},
        {english:"Wind", chinese:"",  symbol:"💨\uFE0F"},
        {english:"Water", chinese:"",  symbol:"💦\uFE0F"},
        {english:"Rain", chinese:"",  symbol:"🌧\uFE0F"},
        {english:"Ocean", chinese:"",  symbol:"🌊\uFE0F"},
        {english:"Desert", chinese:"",  symbol:"🏜\uFE0F"},
        {english:"Mountain", chinese:"",  symbol:"🏔\uFE0F"},
        {english:"Camping", chinese:"",  symbol:"🏔\uFE0F"},
        {english:"Volcano", chinese:"",  symbol:"🌋\uFE0F"},
        {english:"Galaxy", chinese:"",  symbol:"🌌\uFE0F"},
        {english:"River", chinese:"",  symbol:"🏞\uFE0F"},
        {english:"Beach", chinese:"",  symbol:"🏖\uFE0F"},
        {english:"Island", chinese:"",  symbol:"🏝\uFE0F"},
    ]

    foodWords = [];


    artifactWords = [];



    actionWords = [];




    wordObjectList = [...critterWords, ...natureWords,];

    currentWord = ""; //Stores entire word object
    previousWord = ""; //Stores entire word object
    wordLog = ""; //Stores only the english portions of the words

    function generateWord(){
        //Move the words around
        previousWord = currentWord;
        wordLog = previousWord.english + "<br>" + wordLog;
        //Choose a random word from the wordlist
        currentWord = rD(wordObjectList);
        //rewrite page content
        document.getElementById("newOutput").innerHTML = currentWord.english + "<br>" + currentWord.chinese  + "   " + currentWord.symbol ;
        document.getElementById("oldOutputs").innerHTML = wordLog;


    }

    function generateWordOld(){
        //Choose a random word from the wordlist
        word = rD(wordList);
        //Get the old words 
        previousWord = document.getElementById("newOutput").innerHTML;
        wordLog = document.getElementById("oldOutputs").innerHTML;
        //move the words around. Add previous word to log, set new word as the main one at the top
        wordLog = previousWord + "<br>" + wordLog;
        document.getElementById("newOutput").innerHTML = word;
        document.getElementById("oldOutputs").innerHTML = wordLog;


    }


</script>