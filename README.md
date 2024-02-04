# Amendment-Flashcards
Flashcards of the US constitutional amendments
<!DOCTYPE html>
<html>
<head>
    <title>US Constitutional Amendments Flashcards</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            height: 100vh; /* Full viewport height */
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center; /* Centering flashcard vertically */
            background-color: #f0f0f0;
        }
        #flashcard {
            width: 60%;
            max-width: 800px;
            border: 2px solid #000;
            padding: 40px;
            background-color: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        #amendment, #summary {
            font-size: 28px;
            font-weight: bold;
        }
        #summary {
            display: none;
            font-weight: normal;
            margin-top: 20px;
        }
        .button {
            margin: 10px;
            padding: 15px 30px;
            font-size: 20px;
            cursor: pointer;
        }
        .button-container {
            display: flex;
            flex-direction: column; /* Stack buttons vertically */
            align-items: center; /* Center buttons vertically */
        }
    </style>
</head>
<body>

<div id="flashcard">
    <p id="amendment"></p>
    <p id="summary"></p>
</div>

<div class="button-container">
    <button id="back" class="button">Back</button>
    <button id="next" class="button">Show Summary</button>
    <button id="startOver" class="button">Start Over</button>
</div>

<script>
      var amendments = [
    ["First Amendment", "Guarantees freedoms concerning religion, expression, assembly, and the right to petition."],
    ["Second Amendment", "Guarantees the right to bear arms."],
    ["Third Amendment", "Prohibits the quartering of soldiers in private homes without the owner's consent during peacetime."],
    ["Fourth Amendment", "Protects against unreasonable searches and seizures."],
    ["Fifth Amendment", "Provides for the right to due process of law, including protection against self-incrimination and double jeopardy."],
    ["Sixth Amendment", "Guarantees rights related to criminal prosecutions, such as the right to a speedy and public trial, an impartial jury, and counsel."],
    ["Seventh Amendment", "Provides for the right to trial by jury in certain civil cases, according to common law."],
    ["Eighth Amendment", "Prohibits excessive fines and excessive bail, as well as cruel and unusual punishment."],
    ["Ninth Amendment", "Asserts that the enumeration of certain rights in the Constitution does not deny or disparage others retained by the people."],
    ["Tenth Amendment", "States that powers not delegated to the United States by the Constitution, nor prohibited by it to the states, are reserved to the states or to the people."],
    ["Eleventh Amendment", "Provides immunity of states from suits from out-of-state citizens and foreigners not living within the state borders."],
    ["Twelfth Amendment", "Revises presidential election procedures."],
    ["Thirteenth Amendment", "Abolishes slavery and involuntary servitude, except as punishment for a crime."],
    ["Fourteenth Amendment", "Defines citizenship, contains the Privileges or Immunities Clause, the Due Process Clause, the Equal Protection Clause, and deals with post-Civil War issues."],
    ["Fifteenth Amendment", "Prohibits the denial of the right to vote based on race, color, or previous condition of servitude."],
    ["Sixteenth Amendment", "Allows the federal government to collect income tax."],
    ["Seventeenth Amendment", "Establishes the direct election of United States Senators by popular vote."],
    ["Eighteenth Amendment", "Prohibits the manufacture, sale, or transportation of intoxicating liquors."],
    ["Nineteenth Amendment", "Grants women the right to vote."],
    ["Twentieth Amendment", "Changes the dates of congressional and presidential terms, known as the 'Lame Duck Amendment.'"],
    ["Twenty-First Amendment", "Repeals the Eighteenth Amendment, ending prohibition."],
    ["Twenty-Second Amendment", "Limits the president to two terms in office."],
    ["Twenty-Third Amendment", "Grants the District of Columbia electors in the Electoral College."],
    ["Twenty-Fourth Amendment", "Prohibits the revocation of voting rights due to the non-payment of poll taxes."],
    ["Twenty-Fifth Amendment", "Addresses succession to the Presidency and establishes procedures for filling a vacancy in the office of the Vice President and responding to Presidential disabilities."],
    ["Twenty-Sixth Amendment", "Lowers the voting age to 18 years."],
    ["Twenty-Seventh Amendment", "Delays laws affecting Congressional salary from taking effect until after the next election of representatives."]
];

    var current = 0;
    var showSummary = false;

    function updateFlashcard() {
        if (showSummary) {
            document.getElementById("summary").style.display = "block";
            document.getElementById("next").textContent = "Next Amendment";
        } else {
            if (current < 0) current = amendments.length - 1; // Wrap around to last amendment if current is less than 0
            document.getElementById("amendment").textContent = amendments[current][0];
            document.getElementById("summary").textContent = amendments[current][1];
            document.getElementById("summary").style.display = "none";
            document.getElementById("next").textContent = "Show Summary";
        }
        showSummary = !showSummary;
    }

    function startOver() {
        current = 0;
        showSummary = false;
        updateFlashcard();
    }

    document.getElementById("next").onclick = function() {
        if (!showSummary) current++;
        updateFlashcard();
    };

    document.getElementById("back").onclick = function() {
        if (showSummary) {
            showSummary = false;
        } else {
            current--;
        }
        updateFlashcard();
    };

    document.getElementById("startOver").onclick = startOver;

    // Initialize the first flashcard
    startOver();
</script>

</body>
</html>
