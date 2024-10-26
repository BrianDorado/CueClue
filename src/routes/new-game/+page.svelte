<script>

    function startGame(event) {
        event.preventDefault();
        const teams = document.getElementById("teams").value;
        const difficulty = document.getElementById("difficulty").value;
        const ruleSet = document.getElementById("ruleSet").value;

        const gameID = Math.floor(Math.random() * 100000);
        window.location.href = `/play/${gameID}?teams=${teams}&difficulty=${difficulty}&ruleSet=${ruleSet}`;
    }
</script>

<section class="bg-gray-900 text-white py-20 min-h-screen">
    <div class="container mx-auto flex flex-col items-center">
        <h1 class="text-4xl font-bold text-yellow-400 mb-8">New Game Setup</h1>
        <form class="w-full max-w-md bg-gray-800 p-8 rounded-lg shadow-lg space-y-6" on:submit|preventDefault={startGame}>
            <!-- Number of Teams -->
            <div>
                <label for="teams" class="text-lg mb-2 block">Number of Teams</label>
                <input id="teams" name="teams" type="number" min="2" max="10" value="2"
                       class="form-input bg-gray-700 text-white rounded-md shadow-sm focus:ring-yellow-400 focus:border-yellow-400 block w-full p-2.5">
            </div>

            <!-- Difficulty Level -->
            <div>
                <label for="difficulty" class="text-lg mb-2 block">Difficulty Level</label>
                <select id="difficulty" name="difficulty"
                        class="form-select bg-gray-700 text-white rounded-md shadow-sm focus:ring-yellow-400 focus:border-yellow-400 block w-full p-2.5">
                    <option value="easy">Easy</option>
                    <option value="medium">Medium</option>
                    <option value="hard">Hard</option>
                </select>
            </div>

            <!-- Rule Set -->
            <div>
                <label for="ruleSet" class="text-lg mb-2 block">Game Mode</label>
                <select id="ruleSet" name="ruleSet"
                        class="form-select bg-gray-700 text-white rounded-md shadow-sm focus:ring-yellow-400 focus:border-yellow-400 block w-full p-2.5 select">
                    <option value="roundRobin">Round Robin</option>
                    <option value="fastestFinger">Fastest Finger</option>
                    <option value="duelMode">Duel Mode</option>
                </select>
            </div>

            <!-- Start Game Button -->
            <div class="flex justify-center mt-6">
                <button type="submit"
                        class="bg-yellow-400 hover:bg-yellow-300 text-black font-bold py-3 px-6 rounded-md shadow focus:outline-none focus:ring-2 focus:ring-yellow-500">
                    🎬 Start Game
                </button>
            </div>
        </form>
    </div>
</section>
