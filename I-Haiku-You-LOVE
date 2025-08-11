<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>I-Haiku-You | Daily Haiku Game</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Georgia', serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            padding: 20px;
            color: #fff;
        }

        .game-container {
            max-width: 1200px;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .header {
            text-align: center;
            margin-bottom: 30px;
        }

        .game-title {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .date-display {
            font-size: 1.2rem;
            opacity: 0.9;
            margin-bottom: 20px;
        }

        .brilliance-display {
            background: rgba(255, 255, 255, 0.15);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
            text-align: center;
            transition: all 0.5s ease;
            min-height: 80px;
        }

        .brilliance-level {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .section-title {
            font-size: 1.5rem;
            margin-bottom: 20px;
            text-align: center;
            color: #fff;
        }

        /* Image Selection */
        .images-section {
            margin-bottom: 40px;
        }

        .image-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .image-card {
            background: rgba(255, 255, 255, 0.1);
            border: 3px solid transparent;
            border-radius: 15px;
            padding: 20px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s ease;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }

        .image-card:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
        }

        .image-card.selected {
            border-color: #ff6b6b;
            background: rgba(255, 107, 107, 0.2);
            box-shadow: 0 0 20px rgba(255, 107, 107, 0.5);
        }

        .image-emoji {
            font-size: 4rem;
            margin-bottom: 15px;
        }

        .image-title {
            font-size: 1.2rem;
            font-weight: 600;
        }

        /* Word Bank */
        .word-bank {
            margin-bottom: 40px;
        }

        .word-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
            gap: 12px;
            margin-bottom: 20px;
        }

        .word-button {
            background: rgba(255, 255, 255, 0.15);
            border: 2px solid rgba(255, 255, 255, 0.3);
            color: #fff;
            padding: 12px 16px;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 1rem;
            font-weight: 500;
            text-align: center;
        }

        .word-button:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }

        .word-button.used {
            background: rgba(108, 117, 125, 0.3);
            border-color: rgba(108, 117, 125, 0.5);
            cursor: not-allowed;
            opacity: 0.6;
        }

        /* Haiku Builder */
        .haiku-builder {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            text-align: center;
        }

        .haiku-lines {
            font-size: 1.4rem;
            line-height: 2.5;
            margin-bottom: 40px;
            min-height: 250px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .haiku-line {
            margin: 15px 0;
            display: flex;
            align-items: center;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
        }

        .word-slot {
            background: rgba(255, 255, 255, 0.1);
            border: 2px dashed rgba(255, 255, 255, 0.4);
            border-radius: 20px;
            padding: 10px 20px;
            min-width: 100px;
            min-height: 45px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.3s ease;
            font-style: italic;
            opacity: 0.7;
            font-size: 1.2rem;
        }

        .word-slot.filled {
            background: rgba(255, 107, 107, 0.3);
            border-color: #ff6b6b;
            border-style: solid;
            font-style: normal;
            opacity: 1;
            font-weight: 600;
        }

        .word-slot.selected {
            background: rgba(255, 255, 255, 0.3);
            border-color: #fff;
            transform: scale(1.05);
        }

        .word-slot:hover {
            background: rgba(255, 255, 255, 0.2);
            border-color: rgba(255, 255, 255, 0.6);
        }

        .syllable-counter {
            font-size: 1rem;
            opacity: 0.7;
            margin-left: 15px;
            font-style: italic;
        }

        /* Action Buttons */
        .action-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .btn {
            padding: 15px 30px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            font-size: 1.1rem;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(135deg, #ff6b6b, #ee5a6f);
            color: white;
        }

        .btn-secondary {
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: 2px solid rgba(255, 255, 255, 0.3);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.2);
        }

        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none;
        }

        /* Completion Modal */
        .completion-modal {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.8);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 20px;
        }

        .modal-content {
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 20px;
            padding: 40px;
            max-width: 600px;
            width: 100%;
            text-align: center;
            border: 2px solid rgba(255, 255, 255, 0.3);
            animation: modalSlideUp 0.5s ease-out;
        }

        .modal-brilliance {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }

        .modal-haiku {
            font-size: 1.5rem;
            line-height: 2;
            margin: 30px 0;
            font-style: italic;
            background: rgba(255, 255, 255, 0.1);
            padding: 30px;
            border-radius: 15px;
        }

        .ranking-explanation {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin: 20px 0;
            text-align: left;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        @keyframes modalSlideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .instructions {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 30px;
            text-align: center;
            font-size: 1.1rem;
        }

        @media (max-width: 768px) {
            .game-container {
                padding: 20px;
                margin: 10px;
            }
            
            .game-title {
                font-size: 2.5rem;
            }
            
            .image-grid {
                grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            }
            
            .word-grid {
                grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="game-container">
        <div class="header">
            <h1 class="game-title">I-Haiku-You</h1>
            <div class="date-display" id="dateDisplay">Today's Puzzle</div>
            
            <div class="brilliance-display" id="brillianceDisplay">
                <div class="brilliance-level">🌟 Ready to Create</div>
                <div class="brilliance-description">Complete your haiku to discover your brilliance level!</div>
            </div>
        </div>

        <div class="instructions">
            <p><strong>How to Play:</strong> Choose an inspiring image, then click words from the bank below to fill your haiku (5-7-5 syllables). Click any word slot to place your selected word!</p>
        </div>

        <div class="images-section">
            <h2 class="section-title">🌸 Choose Your Inspiration</h2>
            <div class="image-grid" id="imageGrid">
                <div class="image-card" data-image-id="cherry" onclick="selectImage('cherry')">
                    <div class="image-emoji">🌸</div>
                    <div class="image-title">Cherry Blossoms</div>
                </div>
                <div class="image-card" data-image-id="ocean" onclick="selectImage('ocean')">
                    <div class="image-emoji">🌊</div>
                    <div class="image-title">Ocean Waves</div>
                </div>
                <div class="image-card" data-image-id="mountain" onclick="selectImage('mountain')">
                    <div class="image-emoji">🏔️</div>
                    <div class="image-title">Mountain Peak</div>
                </div>
                <div class="image-card" data-image-id="night" onclick="selectImage('night')">
                    <div class="image-emoji">🌙</div>
                    <div class="image-title">Starry Night</div>
                </div>
                <div class="image-card" data-image-id="sunflower" onclick="selectImage('sunflower')">
                    <div class="image-emoji">🌻</div>
                    <div class="image-title">Sunflower Field</div>
                </div>
            </div>
        </div>

        <div class="word-bank">
            <h2 class="section-title">📝 Word Bank (50 words available)</h2>
            <div class="word-grid" id="wordGrid">
                <!-- Words populated by JavaScript -->
            </div>
        </div>

        <div class="haiku-builder">
            <h2 class="section-title">✍️ Build Your Haiku</h2>
            <div class="haiku-lines">
                <div class="haiku-line">
                    <div class="word-slot" data-line="0" data-slot="0" onclick="selectSlot(this)">word</div>
                    <div class="word-slot" data-line="0" data-slot="1" onclick="selectSlot(this)">word</div>
                    <div class="word-slot" data-line="0" data-slot="2" onclick="selectSlot(this)">word</div>
                    <span class="syllable-counter">(5 syllables)</span>
                </div>
                <div class="haiku-line">
                    <div class="word-slot" data-line="1" data-slot="0" onclick="selectSlot(this)">word</div>
                    <div class="word-slot" data-line="1" data-slot="1" onclick="selectSlot(this)">word</div>
                    <div class="word-slot" data-line="1" data-slot="2" onclick="selectSlot(this)">word</div>
                    <div class="word-slot" data-line="1" data-slot="3" onclick="selectSlot(this)">word</div>
                    <span class="syllable-counter">(7 syllables)</span>
                </div>
                <div class="haiku-line">
                    <div class="word-slot" data-line="2" data-slot="0" onclick="selectSlot(this)">word</div>
                    <div class="word-slot" data-line="2" data-slot="1" onclick="selectSlot(this)">word</div>
                    <div class="word-slot" data-line="2" data-slot="2" onclick="selectSlot(this)">word</div>
                    <span class="syllable-counter">(5 syllables)</span>
                </div>
            </div>
            
            <div class="action-buttons">
                <button class="btn btn-secondary" onclick="clearHaiku()">🗑️ Clear All</button>
                <button class="btn btn-primary" onclick="checkCompletion()">✨ Complete Haiku</button>
            </div>
        </div>
    </div>

    <!-- Completion Modal -->
    <div class="completion-modal" id="completionModal">
        <div class="modal-content">
            <div class="modal-brilliance" id="modalBrilliance"></div>
            <div class="modal-haiku" id="modalHaiku"></div>
            
            <div class="ranking-explanation">
                <h3>🌟 Brilliance Ranking System:</h3>
                <p><strong>☀️ Beaming:</strong> Perfect thematic harmony + creative word choices</p>
                <p><strong>✨ Brightest:</strong> Strong theme connection + good flow</p>
                <p><strong>🌤️ Bright:</strong> Clear theme + solid construction</p>
                <p><strong>☁️ Slightly Cloudy:</strong> Some thematic elements present</p>
                <p><strong>🌧️ Under the Weather:</strong> Keep experimenting with different combinations!</p>
            </div>
            
            <div class="action-buttons">
                <button class="btn btn-primary" onclick="shareHaiku()">📱 Share Haiku</button>
                <button class="btn btn-secondary" onclick="closeModal()">🔄 Create Another</button>
            </div>
        </div>
    </div>

    <script>
        // Game State
        let selectedImage = null;
        let currentHaiku = [
            ['', '', ''],
            ['', '', '', ''],
            ['', '', '']
        ];
        let usedWords = new Set();
        let selectedSlot = null;

        // Complete Word Bank - 50 nature-inspired words
        const wordBank = [
            'gentle', 'whisper', 'blossom', 'petals', 'dance', 'spring', 'morning', 'dew',
            'breeze', 'soft', 'cherry', 'pink', 'waves', 'ocean', 'blue', 'foam',
            'crash', 'shore', 'salt', 'deep', 'mountain', 'peak', 'snow', 'high',
            'clouds', 'stone', 'ancient', 'tall', 'stars', 'night', 'moon', 'dark',
            'shimmer', 'glow', 'dream', 'quiet', 'sunflower', 'golden', 'bright', 'warm',
            'field', 'summer', 'honey', 'seeds', 'love', 'heart', 'soul', 'peace',
            'eternal', 'moment'
        ];

        // Brilliance Rankings with your custom system
        const brillianceRankings = [
            {
                level: 1,
                name: "☀️ Beaming",
                description: "Your haiku radiates pure brilliance!",
                color: "#FFD700",
                glow: "0 0 20px rgba(255, 215, 0, 0.6)"
            },
            {
                level: 2,
                name: "✨ Brightest",
                description: "Shining bright with creativity!",
                color: "#FF6B6B",
                glow: "0 0 15px rgba(255, 107, 107, 0.5)"
            },
            {
                level: 3,
                name: "🌤️ Bright",
                description: "A lovely glow of inspiration!",
                color: "#4ECDC4",
                glow: "0 0 10px rgba(78, 205, 196, 0.4)"
            },
            {
                level: 4,
                name: "☁️ Slightly Cloudy",
                description: "Good effort! Try mixing different themes.",
                color: "#95A5A6",
                glow: "0 0 5px rgba(149, 165, 166, 0.3)"
            },
            {
                level: 5,
                name: "🌧️ Under the Weather",
                description: "Every poet has cloudy days. Keep creating!",
                color: "#7F8C8D",
                glow: "0 0 3px rgba(127, 140, 141, 0.2)"
            }
        ];

        // Initialize the game
        function initializeGame() {
            // Set today's date
            const today = new Date().toLocaleDateString('en-US', {
                weekday: 'long',
                year: 'numeric',
                month: 'long',
                day: 'numeric'
            });
            document.getElementById('dateDisplay').textContent = `Today's Puzzle - ${today}`;

            // Populate word bank
            const wordGrid = document.getElementById('wordGrid');
            wordGrid.innerHTML = '';
            
            wordBank.forEach(word => {
                const button = document.createElement('button');
                button.className = 'word-button';
                button.textContent = word;
                button.setAttribute('data-word', word);
                button.onclick = () => selectWord(word);
                wordGrid.appendChild(button);
            });
        }

        function selectImage(imageId) {
            // Remove previous selection
            document.querySelectorAll('.image-card').forEach(card => {
                card.classList.remove('selected');
            });

            // Add selection to clicked image
            const selectedCard = document.querySelector(`[data-image-id="${imageId}"]`);
            selectedCard.classList.add('selected');
            selectedImage = imageId;
            
            console.log(`Selected image: ${imageId}`);
        }

        function selectWord(word) {
            if (usedWords.has(word)) {
                alert('This word is already used in your haiku!');
                return;
            }
            
            if (selectedSlot) {
                // Place word in selected slot
                const line = parseInt(selectedSlot.getAttribute('data-line'));
                const slot = parseInt(selectedSlot.getAttribute('data-slot'));
                
                // If slot was previously filled, free up that word
                if (currentHaiku[line][slot] !== '') {
                    usedWords.delete(currentHaiku[line][slot]);
                    const oldWordButton = document.querySelector(`[data-word="${currentHaiku[line][slot]}"]`);
                    if (oldWordButton) oldWordButton.classList.remove('used');
                }
                
                // Fill the slot
                currentHaiku[line][slot] = word;
                selectedSlot.textContent = word;
                selectedSlot.classList.add('filled');
                selectedSlot.classList.remove('selected');
                
                // Mark word as used
                usedWords.add(word);
                const wordButton = document.querySelector(`[data-word="${word}"]`);
                wordButton.classList.add('used');
                
                // Clear selection
                selectedSlot = null;
                
                console.log(`Placed "${word}" in haiku`);
            } else {
                alert('Please select a word slot first (click on any "word" placeholder in the haiku)');
            }
        }

        function selectSlot(slot) {
            // Clear previous slot selection
            document.querySelectorAll('.word-slot').forEach(s => {
                s.classList.remove('selected');
            });
            
            // Select new slot
            slot.classList.add('selected');
            selectedSlot = slot;
            
            console.log('Selected slot for word placement');
        }

        function clearHaiku() {
            // Reset haiku state
            currentHaiku = [
                ['', '', ''],
                ['', '', '', ''],
                ['', '', '']
            ];
            
            // Clear used words
            usedWords.clear();
            document.querySelectorAll('.word-button').forEach(button => {
                button.classList.remove('used');
            });
            
            // Reset slots
            document.querySelectorAll('.word-slot').forEach(slot => {
                slot.classList.remove('filled', 'selected');
                slot.textContent = 'word';
            });
            
            selectedSlot = null;
            console.log('Cleared haiku');
        }

        function checkCompletion() {
            // Check if haiku is complete
            let isComplete = true;
            for (let line of currentHaiku) {
                for (let word of line) {
                    if (word === '') {
                        isComplete = false;
                        break;
                    }
                }
                if (!isComplete) break;
            }
            
            if (!isComplete) {
                alert('Please complete your haiku by filling all word slots!');
                return;
            }
            
            if (!selectedImage) {
                alert('Please select an inspiring image first!');
                return;
            }
            
            // Calculate brilliance ranking
            const ranking = calculateBrilliance();
            showCompletionModal(ranking);
        }

        function calculateBrilliance() {
            // Simple scoring system - you can make this more sophisticated
            let score = 0;
            
            // Check for thematic words related to selected image
            const themes = {
                cherry: ['cherry', 'blossom', 'petals', 'pink', 'spring', 'gentle', 'soft'],
                ocean: ['ocean', 'waves', 'blue', 'deep', 'salt', 'foam', 'shore'],
                mountain: ['mountain', 'peak', 'high', 'stone', 'ancient', 'tall', 'snow'],
                night: ['night', 'stars', 'moon', 'dark', 'glow', 'shimmer', 'dream'],
                sunflower: ['sunflower', 'golden', 'bright', 'warm', 'summer', 'honey', 'field']
            };
            
            const themeWords = themes[selectedImage] || [];
            let themeMatches = 0;
            
            // Count theme matches
            for (let line of currentHaiku) {
                for (let word of line) {
                    if (themeWords.includes(word.toLowerCase())) {
                        themeMatches++;
                    }
                }
            }
            
            // Assign brilliance level based on theme matches
            if (themeMatches >= 4) return brillianceRankings[0]; // Beaming
            if (themeMatches >= 3) return brillianceRankings[1]; // Brightest
            if (themeMatches >= 2) return brillianceRankings[2]; // Bright
            if (themeMatches >= 1) return brillianceRankings[3]; // Slightly Cloudy
            return brillianceRankings[4]; // Under the Weather
        }

        function showCompletionModal(ranking) {
            const modal = document.getElementById('completionModal');
            const brillianceDisplay = document.getElementById('modalBrilliance');
            const haikuDisplay = document.getElementById('modalHaiku');
            
            brillianceDisplay.textContent = ranking.name;
            brillianceDisplay.style.color = ranking.color;
            brillianceDisplay.style.textShadow = ranking.glow;
            
            // Format haiku text
            const haikuText = currentHaiku.map(line => line.join(' ')).join('<br>');
            haikuDisplay.innerHTML = haikuText;
            
            // Update main brilliance display
            const mainDisplay = document.getElementById('brillianceDisplay');
            mainDisplay.querySelector('.brilliance-level').textContent = ranking.name;
            mainDisplay.querySelector('.brilliance-description').textContent = ranking.description;
            mainDisplay.style.borderColor = ranking.color;
            mainDisplay.style.boxShadow = ranking.glow;
            
            modal.style.display = 'flex';
        }

        function closeModal() {
            document.getElementById('completionModal').style.display = 'none';
        }

        function shareHaiku() {
            const imageEmojis = {
                cherry: '🌸',
                ocean: '🌊',
                mountain: '🏔️',
                night: '🌙',
                sunflower: '🌻'
            };
            
            const haikuText = currentHaiku.map(line => line.join(' ')).join('\n');
            const selectedEmoji = imageEmojis[selectedImage] || '🌟';
            
            const shareText = `I-Haiku-You ${selectedEmoji}\n\n${haikuText}\n\nCan you create a haiku from the same inspiration? Play at: [Your-Website-URL]`;
            
            if (navigator.share) {
                navigator.share({
                    title: 'My I-Haiku-You Creation',
                    text: shareText
                });
            } else {
                navigator.clipboard.writeText(shareText).then(() => {
                    alert('Haiku copied to clipboard! Share it with your friends!');
                });
            }
        }

        // Initialize game when page loads
        window.onload = initializeGame;
    </script>
</body>
</html>
