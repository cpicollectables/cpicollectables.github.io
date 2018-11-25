# CPI Collectables

.calculator {
  padding: 10px;
  /* Content inside is not right up to the edges */
  background-image: url("imageassets/purplefriends-pattern.png");
  /* Setting a purple pattern background to make the calculator element stand out */
}

.calculator span {
  /* For the plus and minus buttons */
  background-color: #6852e2;
  padding: 5px 11px;
  /* Setting a background colour and padding to provide a larger surface area for the user to touch */
  color: white;
  /* White symbols on a dark purple background colour for easy legibility */
  border-radius: 6px;
  box-shadow: 3px 3px rgba(0, 0, 0, 0.1);
  /* Club Penguin Island style, but scaled down smaller */
  margin: auto 5px;
  /* Space on both sides of the button */
}

.calculator input {
  font-family: 'proxima_nova_bold';
  font-size: 15pt;
  text-align: center;
  /* For the <input> where the value is displayed - some styling code has to be repeated */
  width: 100px;
  /* Setting a fixed width */
  border-radius: 6px;
  /* Club Penguin Island style */
}
// Storing information and values for each collectible in an object
var collectibles = {
  "seashells": {
    "facts": ["1 coin per 4 shells exchanged", "Refreshes every 15 minutes", "Found in Beacon Boardwalk and Coconut Cove"],
    "currentfact": 0,
    "amountcollected": 0,
    "exchangerate": 4
  },
  "crystals": {
    "facts": ["1 coin per 4 crystals exchanged", "Refreshes every 15 minutes", "Found in The Sea Caves"],
    "currentfact": 0,
    "amountcollected": 0,
    "exchangerate": 4
  },
  "icecrystals": {
    "facts": ["1 coin per 4 crystals exchanged", "Refreshes every 15 minutes", "Found in Mt. Blizzard"],
    "currentfact": 0,
    "amountcollected": 0,
    "exchangerate": 4
  },
  "windchimes": {
    "facts": ["1 coin per 4 chimes exchanged", "Refreshes every 15 minutes", "Found in Island Central"],
    "currentfact": 0,
    "amountcollected": 0,
    "exchangerate": 4
  }
};
// An array containing all of the keys of the objects (collectible names)
var collectibleskeys = Object.keys(collectibles);
for (i = 0; i < collectibleskeys.length; i++) {
  // For every collectible in the object...

  var collectible = collectibleskeys[i];
  // Get the collectibles' name key

  $(".collectible-" + collectible + " .calculator").html('<span class="calculator-minus" id="' + collectible + '">&#8211;</span><input type="number" min="0" value="0" class="calculator-input" id="' + collectible + '-input"><span class="calculator-plus" id="' + collectible + '">+</span>');
  // Add calculator controls, with IDs of elements containing the collectibles' name key
}
  
$(".coinsearned").html('<i class="custom-emoji coinicon"></i>' + " You will earn <strong>0</strong> coins.");
// And for users with JavaScript enabled, this adds a default value where they'll find out how many coins they've earned
$("input").change(function(event) {
  // Listener for when a user changes the value of an input tag

  var collectible = event.target.id.slice(0, event.target.id.length - 6);
  // Get part of the ID which will be the collectible key of the collectible

  if (document.getElementById(collectible + "-input").value == "") {
    // If the entered value is nothing...

    document.getElementById(collectible + "-input").value = 0;
    // Set the value back to 0 to prevent errors in calculations of earnings

  }

  collectibles[collectible].amountcollected = parseInt(document.getElementById(collectible + "-input").value);
  // Set the amountcollected in the object to the value of the element currently

  calculateCoins();
  // Function to call calculating earnings

});
/* The "intentional bug" I created... and then forgot about... */
/* I did not comment my JavaScript as I was going along yesterday */

  for (i = 0; i < 1; i++) {
    // For the first collectible in the object...

/* What it was supposed to be once I was ready */

  for (i = 0; i < collectibleskeys.length; i++) {
    // For every collectible in the object...
