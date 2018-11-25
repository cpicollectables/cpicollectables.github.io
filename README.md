# CPI Collectables

for (i = 0; i < collectibleskeys.length; i++) {
  // For every collectible in the object...

  var collectible = collectibleskeys[i];
  // Get the collectibles' name key

  var factslength = collectibles[collectible].facts.length;
  // Get the length of the collectibles' facts array

  var randomindex = Math.floor(Math.random() * collectibles[collectible].facts.length);
  // Generate a random index for a fact in the array

  collectibles[collectible].currentfact = randomindex;
  // Set the value of the current fact displayed to the random index

  $("#" + collectible + " .displayed-fact").text(collectibles[collectible].facts[collectibles[collectible].currentfact]);
  // Display the fact stored in the random-generated index of the array

}
