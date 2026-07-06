// INITIALIZE BACKGROUND STARS
const starsContainer = document.getElementById('starsContainer');
for (let i = 0; i < 100; i++) {
    let star = document.createElement('div');
    star.className = 'star';
    star.style.width = star.style.height = Math.random() * 3 + 'px';
    star.style.left = Math.random() * 100 + 'vw';
    star.style.top = Math.random() * 100 + 'vh';
    star.style.animationDelay = Math.random() * 2 + 's';
    starsContainer.appendChild(star);
}

// SECTION NAVIGATION FUNCTION
function nextSection(current, next) {
    document.getElementById(`section${current}`).classList.remove('active');
    document.getElementById(`section${next}`).classList.add('active');

    if (next === 2) startTypewriter();
    if (next === 4) generateCandles();
}

// SECTION 2: TYPEWRITER EFFECT
const message = "Hey Geet, you are turning 14 today! 🎉 Time flies so incredibly fast. I've built this little world just for you to celebrate your special day. Click below to explore your birthday surprises! 💖";
let index = 0;
function startTypewriter() {
    const textEl = document.getElementById('typewriter');
    function type() {
        if (index < message.length) {
            textEl.innerHTML += message.charAt(index);
            index++;
            setTimeout(type, 40);
        } else {
            document.getElementById('storyBtn').classList.remove('hidden');
        }
    }
    type();
}

// SECTION 3: CAKE DECORATION
let toppingsAdded = new Set();
function addTopping(type) {
    document.getElementById(`cake-${type}s`).classList.remove('hidden');
    toppingsAdded.add(type);
    if (toppingsAdded.size === 4) {
        document.getElementById('cakeNextBtn').classList.remove('hidden');
    }
}

// SECTION 4: CANDLES INTERACTIVITY
function generateCandles() {
    const grid = document.getElementById('candlesGrid');
    grid.innerHTML = '';
    for (let i = 1; i <= 14; i++) {
        setTimeout(() => {
            let wrapper = document.createElement('div');
            wrapper.className = 'candle-wrapper';
            wrapper.innerHTML = `<div class="flame" id="flame-${i}"></div><div class="candle-stick"></div>`;
            grid.appendChild(wrapper);
            
            // Auto light up
            setTimeout(() => {
                document.getElementById(`flame-${i}`).classList.add('lit');
                if (i === 14) document.getElementById('blowBtn').classList.remove('hidden');
            }, 300);
        }, i * 300);
    }
}

function blowCandles() {
    for (let i = 1; i <= 14; i++) {
        let flame = document.getElementById(`flame-${i}`);
        flame.classList.remove('lit');
        flame.classList.add('blown');
    }
    setTimeout(() => nextSection(4, 5), 1500);
    setTimeout(triggerFireworks, 1600);
}

// SECTION 5: PREMIUM FIREWORKS ENGINE
function triggerFireworks() {
    const container = document.getElementById('fireworksDisplay');
    let duration = 4000; // 4 second celebration
    let interval = setInterval(() => {
        createExplosion(container);
    }, 400);

    setTimeout(() => {
        clearInterval(interval);
        nextSection(5, 6);
    }, duration);
}

function createExplosion(container) {
    const x = Math.random() * window.innerWidth;
    const y = Math.random() * (window.innerHeight * 0.6);
    const colors = ['#ff416c', '#ff4b2b', '#00f2fe', '#4facfe', '#fecfef', '#ffea9f'];
    const color = colors[Math.floor(Math.random() * colors.length)];

    for (let i = 0; i < 40; i++) {
        let p = document.createElement('div');
        p.className = 'fw-particle';
        p.style.backgroundColor = color;
        p.style.left = x + 'px';
        p.style.top = y + 'px';
        
        let angle = Math.random() * Math.PI * 2;
        let velocity = Math.random() * 120 + 40;
        p.style.setProperty('--x', Math.cos(angle) * velocity + 'px');
        p.style.setProperty('--y', Math.sin(angle) * velocity + 'px');
        
        container.appendChild(p);
        setTimeout(() => p.remove(), 1000);
    }
}

// SECTION 6: GIFT BOX OPENING
function openGift() {
    document.getElementById('giftLid').classList.add('open');
    setTimeout(() => nextSection(6, 7), 1200);
}

// SECTION 8: FLOATING HEARTS
setInterval(() => {
    const container = document.getElementById('heartsContainer');
    if(!container) return;
    let heart = document.createElement('div');
    heart.className = 'heart';
    heart.innerHTML = '❤️';
    heart.style.left = Math.random() * 100 + 'vw';
    heart.style.fontSize = Math.random() * 20 + 10 + 'px';
    heart.style.animationDuration = Math.random() * 2 + 3 + 's';
    container.appendChild(heart);
    setTimeout(() => heart.remove(), 4000);
}, 300);
