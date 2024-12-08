<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" href="https://31.media.tumblr.com/bfdac94fa90650797a1fdc26de002184/tumblr_inline_mzhj5hUMgn1r11hh6.jpg">
    <link href='https://fonts.googleapis.com/css?family=Times+New+Roman:600' rel='stylesheet' type='text/css'>
    <style>
        body {
            width: 100%;
            max-width: 500px;
            margin: 0 auto;
            font-family: 'Times New Roman', serif;
            background-color: #f0f8ff;
            color: #000;
            text-align: center;
        }
        #mainTable {
            font-size: 19px;
            vertical-align: middle;
            width: 100%;
            max-width: 700px;
            margin: 0 auto;
            border-collapse: separate;
            border-spacing: 5px 5px;
        }
        #leftField, #rightField {
            width: 150px;
            height: 150px;
            min-width: 150px;
            max-width: 150px;
            min-height: 200px;
            max-height: 200px;
            cursor: pointer;
            text-align: center;
        }
        .middleField {
            width: 150px;
            height: 70px;
            border: 1px solid #000;
            cursor: pointer;
            background-color: #d3d3d3;
            text-align: center;
        }
        a {
            color: #5b17ba;
            text-decoration: none;
        }
        a:hover {
            color: #945ce3;
        }
        .instructions {
            margin: 20px 0;
        }
        #resultField {
            text-align: center;
        }
    </style>
    <script>
        var namMember = ["Is It Over Now x Out Of The Woods", "Getaway Car x The Other Side Of The Door x August", "Come Back... Be Here x Daylight", "White Horse x coney island (+ Sabrina Carpenter)", "Should've Said No x You're Not Sorry", "New Year's Day x peace", "Is It Over Now x I Wish You Would", "Haunted x exile", "Would've, Could've, Should've x ivy", "Forverer & Always x Maroon", "Mine x Starlight", "I Don't Wanna Live Forever x Dress", "long story short x The Story Of Us", "Clean x evermore", "Foolish One x Tell Me Why", "This Love x Call It What You Want", "Death By A Thousand Cuts x Babe", "Fifteen x You're On Your Own, Kid", "Sparks Fly x gold rush", "False God x Slut!", "Tim McGraw x cowboy like me", "mirrorball x epiphany", "The Alchemy x Treacherous", "Begin Again x Paris", "I Think He Knows x Gorgeous", "Say Don't Go x Welcome To New York x Clean", "Message In A Bottle x How You Get The Girl x New Romantics", "Come Back... Be Here x The Way I Loved You x The Other Side Of The Door","Fresh Out The Slammer x High Infidelity", "The Tortured Poets Department x Now That We Don't Talk", "You're On Your Own, Kid x Long Live", "Sparks Fly x I Can Fix Him (No Really I Can)", "I Look In People's Windows x Snow On The Beach", "Our Song x Jump Then Fall", "The Prophecy x long story short", "Glitch x Everything Has Changed", "Would've, Could've, Should've x I Know Places", "tis the damn season x Daylight", "The Bolter x Getaway Car", "All Of The Girls You Loved Before x Crazier", "It's Nice To Have A Friend x dorothea", "I Can See You x Mine", "Cornelia Street x Maroon", "This Is What You Came For x gold rush", "The Great War x You're Losing Me", "Carolina x no body, no crime", "The Manuscript x Red", "I Forgot That You Existed x This Is Why We Can't Have Nice Things", "I Hate It Here x the lakes", "Hits Different x Death By A Thousand Cuts", "The Black Dog x Come Back... Be Here x Maroon", "thanK you aIMee x Mean", "Out Of The Woods x Is It Over Now x Clean", "State Of Grace x You're On Your Own, Kid", "Sweet Nothing x hoax", "The Albatross x Dancing With Our Hands Tied", "This Love x Ours", "Clara Bow x The Lucky One", "Guilty As Sin? x Untouchable", "The Archer x Question...?", "imgonnagetyouback x Dress", "You Are In Love x cowboy like me", "Sweeter Than Fiction x Holy Ground", "Mary's Song (Oh My My My) x So High School x Everything Has Changed", "right where you left me x All You Had To Do Was Stay", "Last Kiss x Sad Beautiful Tragic", "closure x A Perfectly Good Heart", "Robin x Never Grow Up", "the 1 x Wonderland", "I Almost Do x The Moment I Knew", "Mr. Perfectly Fine x Red", "Getaway Car x Out Of The Woods", "Superstar x invisible string", "Speak Now x Hey Stephen", "this is me trying x Labyrinth", "Paper Rings x Stay Stay Stay", "it's time to go x Better Man", "Teardrops On My Guitar x The Last Time", "We Were Happy x happiness", "the last great american dynasty x Run", "Nothing New x Dear Reader", "Fresh Out The Slammer x You Are In Love", "ivy x Call It What You Want", "I Don't Wanna Live Forever x imgonnagetyouback", "loml x Don't You", "mirrorball x Clara Bow","Surburban Legends x New Year's Day", "I Can Fix Him (No Really I Can) x I Can See You", "Red x Maroon", "Today Was A Fairytale x I Think He Knows", "The Black Dog x exile", "Everything Has Changed x End Game x Thinking Out Loud (+ Ed Sheeran)", "King Of My Heart x The Alchemy", "Dear John x Sad Beautiful Tragic", "My Boy Only Break His Favorite Toys x coney island", "Long Live x Change", "The Archer x You're On Your Own, Kid", "Death By A Thousand Cuts x Getaway Car (+ Jack Antonoff)", "Tim McGraw x Timeless", "this is me trying x Daylight", "Should've Said No x I Did Something Bad", "loml x White Horse", "Out Of The Woods x All You Had To Do Was Stay", "mirrorball x Guilty As Sin?", "Our Song x Call It What You Want", "The Black Dog x Haunted", "Espresso x Please Please Please x Is It Over Now (+ Sabrina Carpenter)", "Hits Different x Welcome To New York", "Afterglow x Dress", "How You Get The Girl x Clean", "The Albatross x Holy Ground", "Cold As You x exile", "The Prophecy x This Love", "Maroon x cowboy like me", "Cornelia Street x The Bolter", "Death By A Thousand Cuts x The Great War", "My Boy Only Breaks His Favorite Toys x This Is Why We Can't Have Nice Things", "False God x tis the damn season", "I Don't Wanna Live Forever x Mine", "evermore x Peter", "us. x Out Of The Woods", "You're On Your Own, Kid x long story short", "Mr. Perfectly Fine x Better Than Revenge", "State Of Grace x Labyrinth", "Ours x the last great american dynasty", "Cassandra x mad woman x I Did Something Bad", "Sparks Fly x Message In A Bottle", "You're Losing Me x How Did It End?", "Haunted x Wonderland", "Never Grow Up x The Best Day"];

        var colorGroups = {
            "group1": { options: ["Tim McGraw", "Picture to Burn", "Teardrops on My Guitar", "A Place in This World", "Cold as You", "The Outside", "Tied Together with a Smile", "Stay Beautiful", "Should’ve Said No", "Mary’s Song (Oh My My My)", "Our Song", "I’m Only Me When I’m with You", "Invisible", "A Perfectly Good Heart"], color: "#00a3ad" },
            "group2": { options: ["Fearless", "Fifteen", "Love Story", "Hey Stephen", "White Horse ", "You Belong With Me", "Breathe", "Tell Me Why", "You’re Not Sorry", "The Way I Loved You", "Forever & Always", "The Best Day ", "Change", "Jump Then Fall", "Untouchable", "Come In With The Rain", "Superstar", "The Other Side Of The Door", "Today Was A Fairytale", "You All Over Me", "Mr. Perfectly Fine", "We Were Happy", "That’s When", "Don’t You", "Bye Bye Baby"], color: "#865829" },
            "group3": { options: ["Mine", "Sparks Fly", "Back to December", "Speak Now", "Dear John", "Mean", "The Story of Us", "Never Grow Up", "Enchanted", "Better than Revenge", "Innocent", "Haunted", "Last Kiss", "Long Live", "Ours", "Superman", "Electric Touch", "When Emma Falls in Love", "I Can See You", "Castles Crumbling", "Foolish One", "Timeless"], color: "#513163" }, 
            "group4": { options: ["State of Grace", "Red", "Treacherous", "I Knew You Were Trouble", "All Too Well", "22", "I Almost Do", "We Are Never Ever Getting Back Together", "Stay Stay Stay", "The Last Time", "Holy Ground", "Sad Beautiful Tragic", "The Lucky One", "Everything Has Changed", "Starlight", "Begin Again", "The Moment I Knew", "Come Back... Be Here", "Girl at Home", "Ronan", "Better Man", "Nothing New", "Babe", "Message in a Bottle", "I Bet You Think About Me", "Forever Winter", "Run", "The Very First Night", "All Too Well (10 Minute Version)"], color: "#951e1a" },
            "group5": { options: ["Welcome to New York", "Blank Space", "Style", "Out of the Woods", "All You Had to Do Was Stay", "Shake It Off", "I Wish You Would", "Bad Blood", "Wildest Dreams", "How You Get the Girl", "This Love", "I Know Places", "Clean", "Wonderland", "You Are in Love", "New Romantics", "Slut!", "Say Don't Go", "Now That We Don't Talk", "Suburban Legends", "Is It Over Now?", "Sweeter than Fiction"], color: "#94a9bb" },
            "group6": { options: ["...Ready For It?", "End Game", "I Did Something Bad", "Don't Blame Me", "Delicate", "Look What You Made Me Do", "So It Goes...", "Gorgeous", "Getaway Car", "King Of My Heart", "Dancing With Our Hands Tied", "Dress", "This Is Why We Can't Have Nice Things", "Call It What You Want", "New Year's Day"], color: "#404040" }, 
            "group7": { options: ["I Forgot That You Existed", "Cruel Summer", "Lover", "The Man", "The Archer", "I Think He Knows", "Miss Americana and the Heartbreak Prince", "Paper Rings", "Cornelia Street", "Death By A Thousand Cuts", "London Boy", "Soon You'll Get Better", "False God", "You Need to Calm Down", "Afterglow", "ME!", "It's Nice to Have a Friend", "Daylight", "All Of The Girls You Loved Before"], color: "#fdc0cc" },     
            "group8": { options: ["the 1", "cardigan", "the last great american dynasty", "exile", "my tears ricochet", "mirrorball", "seven", "august", "this is me trying", "illicit affairs", "invisible string", "mad woman", "epiphany", "betty", "peace", "hoax", "the lakes"], color: "#929292" },
            "group9": { options: ["willow", "champagne problems", "gold rush", "tis the damn season", "tolerate it", "no body, no crime", "happiness", "dorothea", "coney island", "ivy", "cowboy like me", "long story short", "marjorie", "closure", "evermore", "right where you left me", "it's time to go"], color: "#994 914" }, 
            "group10": { options: ["Lavender Haze", "Maroon", "Anti-Hero", "Snow On The Beach", "You're On Your Own, Kid ", "Midnight Rain", "...Question? ", "Vigilante Shit", "Bejeweled", "Labyrinth", "Karma", "Sweet Nothing", "Mastermind", "The Great War", "Bigger Than The Whole Sky", "Paris", "High Infidelity", "Glitch", "Would've, Could've, Should've", "Dear Reader"], color: "#526d85" },
            "group11": { options: ["Fortnight", "The Tortured Poets Department", "My Boy Only Breaks His Favorite Toys", "Down Bad", "So Long, London", "But Daddy I Love Him", "Fresh Out The Slammer", "Florida!!!", "Guilty as Sin?", "Who's Afraid of Little Old Me?", "I Can Fix Him (No Really I Can)", "loml", "I Can Do It With a Broken Heart", "The Smallest Man Who Ever Lived", "The Alchemy", "Clara Bow", "The Black Dog", "imgonnagetyouback", "The Albatross", "Chloe or Sam or Sophia or Marcus", "How Did It End?", "So High School", "I Hate It Here", "thanK you aIMee", "I Look in People's Windows", "The Prophecy", "Cassandra", "Peter", "The Bolter", "Robin", "The Manuscript"], color: "#2f2a24" },
        };

        var lstMember = [];
        var parent = [];
        var equal = [];
        var rec = [];
        var cmp1, cmp2;
        var head1, head2;
        var nrec;
        var numQuestion;
        var totalSize;
        var finishSize;
        var finishFlag;

        function initList() {
            var n = 0;
            var mid;
            var i;

            lstMember[n] = [];
            for (i = 0; i < namMember.length; i++) {
                lstMember[n][i] = i;
            }
            parent[n] = -1;
            totalSize = 0;
            n++;

            for (i = 0; i < lstMember.length; i++) {
                if (lstMember[i].length >= 2) {
                    mid = Math.ceil(lstMember[i].length / 2);
                    lstMember[n] = lstMember[i].slice(0, mid);
                    totalSize += lstMember[n].length;
                    parent[n] = i;
                    n++;
                    lstMember[n] = lstMember[i].slice(mid);
                    totalSize += lstMember[n].length;
                    parent[n] = i;
                    n++;
                }
            }

            for (i = 0; i < namMember.length; i++) {
                rec[i] = 0;
            }
            nrec = 0;
            for (i = 0; i <= namMember.length; i++) {
                equal[i] = -1;
            }

            cmp1 = lstMember.length - 2;
            cmp2 = lstMember.length - 1;
            head1 = 0;
            head2 = 0;
            numQuestion = 1;
            finishSize = 0;
            finishFlag = 0;
        }

        function sortList(flag) {
            var i;
            var str;

            if (flag < 0) {
                rec[nrec] = lstMember[cmp1][head1];
                head1++;
                nrec++;
                finishSize++;
                while (equal[rec[nrec - 1]] != -1) {
                    rec[nrec] = lstMember[cmp1][head1];
                    head1++;
                    nrec++;
                    finishSize++;
                }
            } else if (flag > 0) {
                rec[nrec] = lstMember[cmp2][head2];
                head2++;
                nrec++;
                finishSize++;
                while (equal[rec[nrec - 1]] != -1) {
                    rec[nrec] = lstMember[cmp2][head2];
                    head2++;
                    nrec++;
                    finishSize++;
                }
            } else {
                rec[nrec] = lstMember[cmp1][head1];
                head1++;
                nrec++;
                finishSize++;
                while (equal[rec[nrec - 1]] != -1) {
                    rec[nrec] = lstMember[cmp1][head1];
                    head1++;
                    nrec++;
                    finishSize++;
                }
                equal[rec[nrec - 1]] = lstMember[cmp2][head2];
                rec[nrec] = lstMember[cmp2][head2];
                head2++;
                nrec++;
                finishSize++;
                while (equal[rec[nrec - 1]] != -1) {
                    rec[nrec] = lstMember[cmp2][head2];
                    head2++;
                    nrec++;
                    finishSize++;
                }
            }

            if (head1 < lstMember[cmp1].length && head2 == lstMember[cmp2].length) {
                while (head1 < lstMember[cmp1].length) {
                    rec[nrec] = lstMember[cmp1][head1];
                    head1++;
                    nrec++;
                    finishSize++;
                }
            } else if (head1 == lstMember[cmp1].length && head2 < lstMember[cmp2].length) {
                while (head2 < lstMember[cmp2].length) {
                    rec[nrec] = lstMember[cmp2][head2];
                    head2++;
                    nrec++;
                    finishSize++;
                }
            }

            if (head1 == lstMember[cmp1].length && head2 == lstMember[cmp2].length) {
                for (i = 0; i < lstMember[cmp1].length + lstMember[cmp2].length; i++) {
                    lstMember[parent[cmp1]][i] = rec[i];
                }
                lstMember.pop();
                lstMember.pop();
                cmp1 -= 2;
                cmp2 -= 2;
                head1 = 0;
                head2 = 0;

                if (head1 == 0 && head2 == 0) {
                    for (i = 0; i < namMember.length; i++) {
                        rec[i] = 0;
                    }
                    nrec = 0;
                }
            }

            if (cmp1 < 0) {
                str = "battle #" + (numQuestion - 1) + "<br>" + Math.floor(finishSize * 100 / totalSize) + "% sorted";
                document.getElementById("battleNumber").innerHTML = str;
                showResult();
                finishFlag = 1;
            } else {
                showImage();
            }
        }

        function showResult() {
            var ranking = 1;
            var sameRank = 1;
            var str = "";

            str += "<table style=\"width:495px; font-size:18px; line-height:120%; margin-left:auto; margin-right:auto; border:1px solid #000; border-collapse:collapse\" align=\"center\">";
            str += "<tr><td style=\"color:#fff1f4; background-color:#000; text-align:center;\">rank</td><td style=\"color:#fff1f4; background-color:#000; text-align:center;\">song</td></tr>";

            for (var i = 0; i < namMember.length; i++) {
                var songName = namMember[lstMember[0][i]];
                var coloredSongName = applyColorToSong(songName);
                str += "<tr><td style=\"border:1px solid #000; text-align:center; padding-right:0px;\">" + ranking + "</td><td style=\"border:1px solid #000; padding-left:0px;\">" + coloredSongName + "</td></tr>";
                if (i < namMember.length - 1) {
                    if (equal[lstMember[0][i]] == lstMember[0][i + 1]) {
                        sameRank++;
                    } else {
                        ranking += sameRank;
                        sameRank = 1;
                    }
                }
            }
            str += "</table>";
            document.getElementById("resultField").innerHTML = str;
        }

        function applyColorToSong(song) {
            for (var group in colorGroups) {
                if (colorGroups[group].options.includes(song)) {
                    return `<span style="color:${colorGroups[group].color};">${song}</span>`;
                }
            }
            return song;
        }

        function showImage() {
            var str0 = "battle #" + numQuestion + "<br>" + Math.floor(finishSize * 100 / totalSize) + "% sorted";
            var str1 = toNameFace(lstMember[cmp1][head1]);
            var str2 = toNameFace(lstMember[cmp2][head2]);

            document.getElementById("battleNumber").innerHTML = str0;
            document.getElementById("leftField").innerHTML = applyColorToSong(str1);
            document.getElementById("rightField").innerHTML = applyColorToSong(str2);

            numQuestion++;
        }

        function toNameFace(n) {
            return namMember[n];
        }

        window.onload = function() {
            initList();
            showImage();
        };
    </script>
</head>
<body>
    <p class="instructions">
        <b>welcome to the eras' tour surprise song sorter.</b><br />
        please pick the song you like more. please note that choosing "i like both" or "skip for now" frequently will negatively affect your results. <br />
        even if you make a mistake, do NOT click back page. all progress will be discarded.<br />
        made by cln (dec 2024) as consulted the work of <a href="https://biasorter.tumblr.com/">biasorter</a> and <a href="https://jobazzle.tumblr.com/">jobazzle</a>.<br />
    </p>
    <table id="mainTable" align="center">
        <tbody>
            <tr>
                <td id="battleNumber" colspan="3" style="padding-bottom: 10px; text-align:center;">
                    <b>battle #1<br>0% sorted</b>
                </td>
            </tr>
            <tr>
                <td id="leftField" onclick="if(finishFlag==0) sortList(-1);" rowspan="2" style="text-align:center;"></td>
                <td class="middleField" onclick="if(finishFlag==0) sortList(0);" style="text-align:center;">i like both</td>
                <td id="rightField" onclick="if(finishFlag==0) sortList(1);" rowspan="2" style="text-align:center;"></td>
            </tr>
            <tr>
                <td class="middleField" onclick="if(finishFlag==0) sortList(0);" style="text-align:center;">skip for now</td>
            </tr>
        </tbody>
    </table>
    <br><br>
    <div id="resultField" style="text-align: center;"><br></div>
</body>
</html>
