//Tutorial 4

function createCharacter(charName, catName = null, initialSkills) {


    //checks to see if the inputted skill is a number and less than 10, if so it increments the skill by 1
    function levelUp(skill) {
        if(typeof this[skill] === 'number' && this[skill] < 10) {
            this[skill]++;
        }
    }


    //add the inputted items onto the end of the inventory
   function grabItems(...items) {
        this.inventory.push(...items);
    }

   
   //removes the selected item from inventory if it was previously part of inventory
   function dropItem(item) {
        const itemIndex = this.inventory.indexOf(item);
        if (itemIndex !== -1) {
            this.inventory.splice(itemIndex, 1);
        }

    }

   
    //takes the raw skill inputs and ensures their values are numbers and not greater than 10
    const refinedFishing = Math.min(10, Number(initialSkills?.[0] ?? 0));
    const refinedMining = Math.min(10, Number(initialSkills?.[1] ?? 0));
    const refinedFarming = Math.min(10, Number(initialSkills?.[2] ?? 0));

    let character = {                 
        characterName: charName,
        fishingSkill: refinedFishing, 
        miningSkill: refinedMining, 
        farmingSkill: refinedFarming, 
        inventory: [],
        levelUp, 
        grabItems,
        dropItem
    };
 
    //adds catName when a values was given
    if(catName !== null) {
        character.catName = catName;
    }
    
    return character;                   
}

function describeCharacter(character) {


    let total = character.fishingSkill + character.miningSkill + character.farmingSkill;

    let description = character.characterName;

    
    if (total < 10) {
        description += " is just starting out";
    } else {
        description += " is a skilled adventurer";
    }

    //when catName is a property, add it to the description
    if("catName" in character){
        description += ` and has a cat ${character.catName}`;
    }

    description += ".";

    console.log(description);

    return description;                 
}

// A few examples are shown below of the calling the function k
let player = createCharacter("New Player", null)
player.levelUp("farmingSkill")
console.log(player.farmingSkill) //should print 1
player.grabItems("Apple", "Peach") 
player.dropItem("Peach")
console.log(...player.inventory) //should print Apple
describeCharacter(player) //should print "New Player is just starting out."
