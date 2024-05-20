<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Google Dorks for Bug Bounty</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            background-color: #212121;
            color: #f0f0f0;
            padding: 20px;
            box-sizing: border-box;
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 20px;
        }
        label {
            font-size: 1.2em;
        }
        input {
            font-size: 1em;
            padding: 5px;
            margin-left: 5px;
        }
        button {
            font-size: 1em;
            background-color: #4CAF50;
            color: white;
            border: none;
            padding: 6px 12px;
            cursor: pointer;
            margin-left: 5px;
        }
        button:hover {
            background-color: #45a049;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            margin-bottom: 10px;
        }
        a {
            text-decoration: none;
            color: #69f0ae;
        }
        a:hover {
            text-decoration: underline;
        }
        p {
            margin: 0;
        }
        p.description {
            margin-bottom: 5px;
            font-weight: bold;
        }
        section {
            margin-top: 20px;
            border-top: 1px solid #ccc;
            padding-top: 20px;
        }
        h2 {
            margin-bottom: 10px;
        }
        ul.link-list {
            margin: 0;
            padding: 0;
            list-style-type: none;
        }
        ul.link-list li {
            margin-bottom: 10px;
        }
        .hidden { display: none; }
        #tooltip {
        position: absolute;
        background-color: black;
        color: white;
        padding: 5px;
        border-radius: 5px;
    }
    </style>
</head>
<body>
    <h1>Google Dorks for Bug Bounty</h1>
    <p>
        <a href="https://twitter.com/reewardius" target="_blank">
            <img src="https://img.shields.io/twitter/url/https/twitter.com/TakSec.svg?style=social&label=Follow%20%40reewardius" alt="Twitter Follow Badge">
        <a href="https://github.com/reewardius/bugbounty-dorks/" target="_blank">GitHub Repo</a>
        </a><br><br>
    </p>
    <label for="domainInput">Enter a domain:</label>
    <input type="text" id="domainInput" placeholder="example.com" oninput="updateDomain()">
    <div id="tooltip" class="hidden">For multiple domains, separate by comma. e.g., example1.com, example2.com</div>

    <ul id="dorkList"></ul>
    <section>
        <h2>Additional Resources</h2>
        <ul class="link-list">
            <li><a href="https://github.com/reewardius/bugbounty-dorks/" target="_blank">Google Dorks For Bug Bounty</a></li>
            <li><a href="https://freedium.cfd/https://thegrayarea.tech/5-google-dorks-every-hacker-needs-to-know-fed21022a906" target="_blank">5 Google Dorks Every Hacker Needs to Know</a></li>
            <li><a href="https://freedium.cfd/https://infosecwriteups.com/uncover-hidden-gems-in-the-cloud-with-google-dorks-8621e56a329d" target="_blank">Uncover Hidden Gems in the Cloud with Google Dorks</a></li>
            <li><a href="https://freedium.cfd/https://infosecwriteups.com/10-google-dorks-for-sensitive-data-9454b09edc12" target="_blank">10 Google Dorks for Sensitive Data</a></li>
        </ul>
    </section>
    <script>
    const domainInput = document.getElementById('domainInput');
    const tooltip = document.getElementById('tooltip');

    domainInput.addEventListener('mouseover', function() {
        tooltip.style.display = 'block';
        tooltip.style.left = domainInput.offsetLeft + 'px';
        tooltip.style.top = (domainInput.offsetTop + domainInput.offsetHeight + 5) + 'px';
    });

    domainInput.addEventListener('mouseout', function() {
        tooltip.style.display = 'none';
    });
    
    let originalDorks = [];
    let stopAppending = false;  // Flag to stop appending new dorks

    async function fetchDorks() {
        const url = "https://raw.githubusercontent.com/reewardius/bugbounty-dorks/main/README.md";
        const response = await fetch(url);
        const text = await response.text();

        const dorkList = document.getElementById("dorkList");
        const regex = /(?:^### (.+)|^> (.+))/gm;
        let match;
        let title = '';
        let firstDork = true;

        while ((match = regex.exec(text)) !== null) {
            if (match[1]) {
                // Title match
                title = match[1];
                if (title === "Dorks that work better w/o domain") {
                    stopAppending = true;  // Set the flag to stop appending when this title is encountered
                }
            } else if (match[2] && !stopAppending) {
                // Dork match
                if (firstDork) {
                    firstDork = false;
                    continue;
                }
                const dork = match[2];
                originalDorks.push(dork);
                const listItem = createDorkListItem(dork, title);
                dorkList.appendChild(listItem);
            }
        }
    }
        let prevTitle = '';

        function createDorkListItem(dork, description) {
            const googleLink = `https://www.google.com/search?q=${encodeURIComponent(dork)}`;

            const listItem = document.createElement("li");

            if (description && description !== prevTitle) {
                const desc = document.createElement("p");
                desc.textContent = description;
                desc.classList.add("description");
                listItem.appendChild(desc);
                prevTitle = description;
            }

            const link = document.createElement("a");
            link.href = googleLink;
            link.textContent = dork;
            link.classList.add("dorkLink");
            link.target = "_blank";

            listItem.appendChild(link);

            return listItem;
        }

        function updateDomain() {
            const domainInput = document.getElementById("domainInput");
            const domains = domainInput.value.split(",").map(domain => domain.trim());
        
            if (domains.length === 0) return;
        
            const dorkLinks = document.querySelectorAll(".dorkLink");
            dorkLinks.forEach((link, index) => {
                let originalDork = originalDorks[index];
                
                // Check if the dork is related to Drupal and skip modification
                if (originalDork.includes("Drupal")) {
                    return; // Skip any modification if it's a Drupal related dork
                }

                // For site:example.com
                if (/site:"?example\[?\.\]?com"?/i.test(originalDork)) {
                    const joinedDomains = domains.map(d => `site:${d}`).join(" | ");
                    originalDork = originalDork.replace(/site:"?example\[?\.\]?com"?/gi, joinedDomains);
                }
                
                // For "example.com"
                else if (/["']example\[?\.\]?com["']/i.test(originalDork)) {
                    const joinedDomains = domains.map(d => `"${d}"`).join(" | ");
                    originalDork = originalDork.replace(/["']example\[?\.\]?com["']/gi, joinedDomains);
                }
                
                // For intext:"example.com" and similar patterns
                const intextPattern = /intext:"example\.com"/gi;
                if (intextPattern.test(originalDork)) {
                    const joinedDomains = domains.map(d => `intext:"${d}"`).join(" | ");
                    originalDork = originalDork.replace(intextPattern, joinedDomains);
                }

                // Update intext:"" for all domains after the first
                if (originalDork.includes('intext:"')) {
                    const updatedIntexts = domains.map((d) => `intext:"${d}"`).join(" | ");
                    originalDork = originalDork.replace(/intext:"[^"]+"/gi, updatedIntexts);
                }

                const updatedLink = `https://www.google.com/search?q=${encodeURIComponent(originalDork)}`;
            
                link.textContent = originalDork;
                link.href = updatedLink;
            });
        }
        fetchDorks();
    </script>
</body>
</html>
