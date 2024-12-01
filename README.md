<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <!-- <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous"> -->
</head>
<style>
    body {
        background-color: #3C3D37;
    }

    .container {
        /* border: 1px solid black; */
        display: flex;
        align-items: center;
        justify-content: center;
        margin-top: auto;
        height: auto;
        overflow-y: auto;
        padding: 2.5%;
    }

    .code-holder-container-scrollable {
        /* border: 1px solid red; */
        display: flex;
        flex-direction: column;
        align-items: center;
        /* justify-content: center; */
        width: 30%;
        height: 500px;

        padding: 2.5%;

    }

    .code-holder-container {
        display: flex;
        flex-direction: column;
        align-items: center;
        /* justify-content: center; */
        width: 100%;
        overflow-y: auto;
        overflow-x: hidden;
        background-color: #181C14;
        padding: 5%;
        padding-top: 10%;
        border-radius: 20px;
    }

    .code-holder {
        /* border: 1px solid red; */
        padding: 2.5%;
        font-size: 20px;
        font-weight: bold;
        display: flex;
        align-items: center;
        justify-content: start;
        padding-left: 5%;
        width: 70%;
        border-radius: 20px;
        background-color: lightgray;
        text-align: center;
        margin-bottom: 5%;
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
        transition: transform 0.3s ease;
        cursor: pointer;

    }

    .code-holder:hover {
        /* This will move the div 10px to the right and 10px down on hover */
        transform: translateY(-10px);
    }

    .icon {
        /* border: 1px solid red; */
        display: flex;
        align-items: center;
        justify-content: center;
        width: 8%;
    }

    h1 {
        margin: 0 !important;
    }

    /* Custom Scrollbar for Webkit Browsers (Chrome, Safari, Edge) */

    /* Webkit Browsers (Chrome, Safari, Edge) */
    ::-webkit-scrollbar {
        width: 12px;
    }

    ::-webkit-scrollbar-track {
        background-color: transparent;
    }

    ::-webkit-scrollbar-thumb {
        background-color: #888;
        border-radius: 10px;
    }

    ::-webkit-scrollbar-thumb:hover {
        background-color: #555;
    }

    /* Overlay that covers the entire screen */
    .overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: rgba(0, 0, 0, 0.7);
        /* Black background with opacity */
        display: none;
        /* Hidden by default */
        justify-content: center;
        align-items: center;
    }

    /* The modal container */
    .modal {
        background: transparent;
        padding: 20px;
        border-radius: 8px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        width: 20%;
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        border-radius: 20px;
    }

    .customize-input {
        border: 2px solid wheat !important;
        padding: 4%;
        border-radius: 20px;
        outline: none !important;
        color: wheat;
        width: 100%;
        background-color: transparent;
    }

    .customize-input::placeholder {
        color: #facc75;
    }



    /* Close button styling */
    .close-btn {
        margin-top: 20px;
        padding: 10px 20px;
        background-color: #007bff;
        color: white;
        border: none;
        border-radius: 4px;
        cursor: pointer;
        width: 20%;
    }

    .close-btn:hover {
        background-color: #0056b3;
    }


    #countdown {
    width: 100%;
    height: 100%;
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 200px;
    font-weight: bold;
    color: white;
    background-color: rgba(0, 0, 0, 0.7);
    text-align: center; /* Horizontally center the text */
    line-height: 1.2; /* Adjust line height if needed */
    padding: 20px;
    border-radius: 5px;
    display: none !important;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    display: flex;              /* Enable flexbox */
    justify-content: center;    /* Center horizontally */
    align-items: center;        /* Center vertically */
}
</style>

<body>

    <div id="countdown"></div>
    <div id="container" class="container" style="visibility: hidden;">
        <div class="code-holder-container-scrollable">
            <div id="codeContainer" class="code-holder-container">

                <!-- <div class="code-holder">
                    <h1>ASDJK3</h1>
                    <span class="icon" style="margin-left: auto; padding-right: 5%;">
                        <img src="copy.png" alt="copy" style="width: 100%;">
                    </span>
                </div> -->

            </div>
        </div>  
    </div>

    <div id="modalOverlay" class="overlay">
        <div class="modal">
            <input type="password" class="customize-input" placeholder="Enter Password" id="passwordInput" required>
            <button type="submit" style="visibility: hidden !important;"></button>
        </div>
    </div>



    <!-- <div class="container">
        <input type="file" id="fileInput" accept=".txt">
        <button onclick="readFile()">Read File</button>
    </div>



    <div class="container" style="flex-direction: column;">
        <textarea id="plainText" rows="4" cols="50" placeholder="Enter text to encrypt"></textarea><br><br>
        <button onclick="encrypt()">Encrypt</button><br><br>

        <textarea id="encryptedText" rows="4" cols="50"
            placeholder="Encrypted text will appear here"></textarea><br><br>
        <button onclick="decrypt()">Decrypt</button><br><br>

        <textarea id="decryptedText" rows="4" cols="50" placeholder="Decrypted text will appear here"></textarea>

    </div>

    <div class="container" style="flex-direction: column;">
        <label for="secretInput">Edit the secret:</label><br>
        <textarea id="secretInput" rows="10" cols="50"></textarea><br>

        <button onclick="updateSecret()">Update Secret</button>
    </div>


    <div class="container" style="flex-direction: column;">
        <h1>Update Gist</h1>
        <textarea id="gistContent" rows="10" cols="50">Your secret content here...</textarea>
        <br>
        <button onclick="updateGist()">Update Gist</button>
    </div> -->
</body>
<script>
    //window.onload = fetchSecret;
    var deleted = "";
    var targetId = 1;

    window.onload = function () {
        openModal();
        // fetchSecret();
    };

    function validate() {
        let password = document.getElementById('passwordInput');
        if (password.value !== "0929487569411") {
            alert("Wrong password");
            window.location.reload();
        }
        else {
            alert("Welcome stupid");
            closeModal();
            createCode();
        }

    }


    document.getElementById('passwordInput').addEventListener('keydown', function (event) {
        // Check if the key pressed is Enter (keyCode 13)
        if (event.key === 'Enter') {
            validate();
        }
    });



    async function createCode() {
        const container = document.getElementById('container');
        container.style.visibility = "visible";
        const lines = await fetchSecret();
        //   console.log("triying pass array from function fetch: " +lines[0]);
        for (let i = 0; i < lines.length; i++) {
            createDiv(lines[i], i);
        }



        const divs = document.querySelectorAll('.code-holder');
        divs.forEach(div => {
            div.addEventListener('click', async function () {
                // Get the ID of the clicked div
                console.log(divs);
                const clickedDivId = this.id;
                var code = document.getElementById(`${clickedDivId}`);
                var textToCopy = code.innerText;
                navigator.clipboard.writeText(textToCopy)
                .then(() => {
                    alert("Text copied to clipboard!");
                })
                .catch(err => {
                    console.error('Error copying text: ', err);
                    alert('Failed to copy text');
                });
                const lineToRemove = parseInt(clickedDivId.replace('code-holder-', ''), 10);
                const updatedText = await fetchSecret(lineToRemove);
                updateGist(updatedText);

            });
        });
    }

    function openModal() {
        document.getElementById('modalOverlay').style.display = 'flex';
    }

    // Function to close the modal and hide the overlay
    function closeModal() {
        document.getElementById('modalOverlay').style.display = 'none';
    }




    function createDiv(textCode, id) {
        // Check if codeContainer is found
        if (!codeContainer) {
            console.error("codeContainer element not found!");
            return;
        }

        const codeHolder = document.createElement('div');
        const h1 = document.createElement('h1');
        const span = document.createElement('span');
        const image = document.createElement('img');

        image.src = "copy.png";
        image.style.width = "100%"; // Ensure image width is properly set

        span.classList.add('icon');
        span.style.marginLeft = "auto";
        span.style.paddingRight = "5%";
        h1.textContent = textCode;
        codeHolder.id = id;
        // codeHolder.onclick = function () {
        //     updateSecret();
        // };

        codeHolder.classList.add('code-holder');

        codeHolder.appendChild(h1);
        codeHolder.appendChild(span);
        span.appendChild(image);  // Make sure the image is inside the span

        codeContainer.appendChild(codeHolder);  // Append the codeHolder to the container
    }

    function readFile() {
        const fileInput = document.getElementById('fileInput');
        const file = fileInput.files[0]; // Get the first selected file
        console.log(fileInput.value);

        if (file) {
            const reader = new FileReader();

            // Define what happens when the file is successfully read
            reader.onload = function (event) {
                const content = event.target.result;

                // Split the file content into lines
                const lines = content.split('\n');  // \n is the newline character
                const firstLine = lines[0].trim(); // Get the first line and trim any extra spaces
                console.log(lines)

                // Display the first line
                document.getElementById('fileContent').textContent = firstLine;
            };

            // Define what happens if there's an error reading the file
            reader.onerror = function (error) {
                console.error("Error reading file:", error);
                alert("Error reading the file.");
            };

            // Read the file as text
            reader.readAsText(file);
        } else {
            alert("No file selected.");
        }
    }



    let encryptionKey;

    // Derive key from secret password (user-provided)
    async function deriveKeyFromPassword(password) {
        const encoder = new TextEncoder();
        const passwordBuffer = encoder.encode(password);

        // Using PBKDF2 to derive a key from the password
        encryptionKey = await crypto.subtle.importKey(
            "raw",
            passwordBuffer,
            {
                name: "PBKDF2"
            },
            false, // Non-extractable
            ["deriveKey"]
        );

        // Derive the AES key for AES-GCM
        encryptionKey = await crypto.subtle.deriveKey(
            {
                name: "PBKDF2",
                salt: new TextEncoder().encode("salt_value"), // Use a fixed salt (or random salt, but needs to be saved for decryption)
                iterations: 100000,
                hash: "SHA-256",
            },
            encryptionKey, // Import key from password
            {
                name: "AES-GCM",
                length: 256,
            },
            false, // Key is non-extractable
            ["encrypt", "decrypt"]
        );
    }

    // Encrypt the input text using the derived secret key
    async function encrypt() {
        const text = document.getElementById("plainText").value;
        const password = "099411";

        if (!text || !password) {
            alert("Please enter both text to encrypt and a secret key");
            return;
        }

        if (!encryptionKey) await deriveKeyFromPassword(password); // Derive the key from the password

        const encoder = new TextEncoder();
        const data = encoder.encode(text);

        // Generate a random Initialization Vector (IV)
        const iv = crypto.getRandomValues(new Uint8Array(12)); // 12-byte IV

        try {
            const encrypted = await crypto.subtle.encrypt(
                {
                    name: "AES-GCM",
                    iv: iv, // IV used for AES-GCM
                },
                encryptionKey, // The encryption key
                data // The data to encrypt
            );

            // Convert encrypted data to Base64 for easy display
            const encryptedBase64 = arrayBufferToBase64(encrypted);
            document.getElementById("encryptedText").value = encryptedBase64;
            document.getElementById("encryptedText").dataset.iv = arrayBufferToBase64(iv); // Store IV for later decryption
        } catch (error) {
            console.error("Encryption failed:", error);
        }
    }

    // Decrypt the encrypted text using the secret key
    async function decrypt() {
        const encryptedBase64 = document.getElementById("encryptedText").value;
        const ivBase64 = document.getElementById("encryptedText").dataset.iv;
        const password = "0929487569411";

        if (!encryptedBase64 || !ivBase64 || !password) {
            alert("Please enter both a secret key and encrypted text to decrypt");
            return;
        }

        if (!encryptionKey) await deriveKeyFromPassword(password); // Derive the key from the password

        const encryptedData = base64ToArrayBuffer(encryptedBase64);
        const iv = base64ToArrayBuffer(ivBase64);

        try {
            const decrypted = await crypto.subtle.decrypt(
                {
                    name: "AES-GCM",
                    iv: iv, // IV used for AES-GCM
                },
                encryptionKey, // The encryption key
                encryptedData // The encrypted data
            );

            // Convert decrypted data back to text
            const decoder = new TextDecoder();
            const decryptedText = decoder.decode(decrypted);
            document.getElementById("decryptedText").value = decryptedText;
        } catch (error) {
            console.error("Decryption failed:", error);
        }
    }

    // Convert ArrayBuffer to Base64
    function arrayBufferToBase64(buffer) {
        const binary = String.fromCharCode.apply(null, new Uint8Array(buffer));
        return window.btoa(binary);
    }

    // Convert Base64 to ArrayBuffer
    function base64ToArrayBuffer(base64) {
        const binary_string = window.atob(base64);
        const len = binary_string.length;
        const bytes = new Uint8Array(len);
        for (let i = 0; i < len; i++) {
            bytes[i] = binary_string.charCodeAt(i);
        }
        return bytes.buffer;
    }




    var newUpdatedText = "";
    const token = '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';  // Replace with your token
    const gistId = '5285eed81474c8bde8641e74854fb2ca';  // Replace with your Gist ID
    const url = `https://api.github.com/gists/${gistId}`;

    // Function to update the Gist file
    function updateGist(newText) {
        // const updatedContent = document.getElementById('secretInput').value;  // Get the updated secret from textarea

        var userResponse = confirm("Do you want to proceed?");

        if (userResponse) {
            const data = {
                files: {
                    'code.txt': {
                        content: newText // Update the file content with the new secret
                    }
                }
            };
            fetch(url, {
                method: 'PATCH',
                headers: {
                    'Authorization': `token ${token}`,
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify(data)
            })
                .then(response => response.json())
                .then(result => {
                    console.log('Gist updated:', result);
                    alert('The Gist has been updated!');

                    var countdownElement = document.getElementById('countdown');
                    countdownElement.style.cssText = 'display: block !important; display: flex !important;';
                    var container = document.getElementById('container');
                    container.style.display = 'none';



                    // Start the countdown from 10 to 0
                    var countdownValue = 10;
                    countdownElement.innerHTML = countdownValue;

                    // Update countdown every second
                    var countdownInterval = setInterval(() => {
                        countdownValue--;
                        countdownElement.innerHTML = countdownValue;

                        if (countdownValue <= 0) {
                            clearInterval(countdownInterval); // Stop the countdown
                            location.reload(); // Reload the page
                        }
                    }, 1000); // Update every seconds
                })
                .catch(error => {
                    console.error('Error updating the Gist:', error);
                });
        } else {
            alert("You chose No!");
            location.reload();
        }



    }




    async function getRawUrl() {
        try {
            const response = await fetch(`https://api.github.com/gists/${gistId}`, {
                cache: 'no-cache', // Disables caching
                headers: {
                    'Content-Type': 'application/json' // Optional header depending on API needs
                }
            });

            const data = await response.json();
            const rawUrl = data.files?.['code.txt']?.raw_url; // Use optional chaining

            if (rawUrl) {
                console.log(rawUrl);
                return rawUrl;
            } else {
                console.error("Couldn't find 'code.txt' file in the Gist or error in response data.");
                return null; // Or handle it differently if the file is not found
            }
        } catch (error) {
            console.error('Error fetching the raw URL:', error);
            return null; // Or handle the error differently
        }
    }



    let fetchedSecret = '';  // This will hold the fetched secret text

    // Function to fetch the secret text from the GitHub Gist
    async function fetchSecret(lineToRemove) {
        const rawUrl = await getRawUrl();

        if (!rawUrl) {
            console.error("Couldn't retrieve the raw URL for the Gist file.");
            return null; // Or handle the error differently
        }

        try {
            var array = [];
            const response = await fetch(rawUrl);
            const data = await response.text(); // Parse the response as text

            fetchedSecret = data; // Store the fetched secret text

            // Count the number of lines in the fetched text
            const lineCount = data.split('\n').length;

            console.log(`Number of lines: ${lineCount}`);

            // Convert text to an array of lines
            const lines = data.split('\n');
            array = lines;

            // Remove the specific line using filter
            const updatedLines = lines.filter((line, index) => index !== lineToRemove);

            const updatedText = updatedLines.join('\n');

            if (lineToRemove === undefined) {
                return array;
            }
            else {

                return updatedText;

            }

        } catch (error) {
            console.error('Error fetching the secret:', error);
        }
    }


    // Function to update the secret text after editing
    async function updateSecret() {
        console.log(targetId);
        const updatedText = await fetchSecret(targetId);
        console.log(updatedText);
        // updateGist(updatedText);
        // console.log(deleted);
        // location.reload();
    }

</script>

</html>
