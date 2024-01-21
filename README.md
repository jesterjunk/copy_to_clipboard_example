<a href="https://ko-fi.com/jesterjunk"><img src="https://gist.githubusercontent.com/jesterjunk/0aca4f4868b988d37e8a08e5c3fbe341/raw/76d6a5f562ccb26b78a5c09a9ffbd650a8dafa28/01_ko-fi.com_favicon_898x32_v01.png"></a>

<div align="center">

<h4>

<br>Demo on GitHub Pages<br><br>
[https://jesterjunk.github.io/copy_to_clipboard_example/](https://jesterjunk.github.io/copy_to_clipboard_example/)<br><br>

</h4>

<img src="https://gist.github.com/jesterjunk/13c494e167cef952f0c7c42a750b4d11/raw/6821d5a3d91a4fba013f8f5c5e5af7252317c97b/01_copy_to_clipboard_example.gif" alt="https://gist.github.com/jesterjunk/13c494e167cef952f0c7c42a750b4d11/raw/6821d5a3d91a4fba013f8f5c5e5af7252317c97b/01_copy_to_clipboard_example.gif" title="https://gist.github.com/jesterjunk/13c494e167cef952f0c7c42a750b4d11/raw/6821d5a3d91a4fba013f8f5c5e5af7252317c97b/01_copy_to_clipboard_example.gif">

<h4>

<br><br>Source Code on Gist<br><br>[https://gist.github.com/jesterjunk/13c494e167cef952f0c7c42a750b4d11](https://gist.github.com/jesterjunk/13c494e167cef952f0c7c42a750b4d11)<br><br>

</h4>

Vanilla<br>
┌────────┴────────┐<br>
HTML, CSS, and JavaScript<br>
└────────┬────────┘<br>
index.html

</div>

```html
<!DOCTYPE HTML>
<html lang="en" style="background: hsl(70, 8%, 15%);">
<head>
    <meta charset="UTF-8">
    <title>Copy To Clipboard Example</title>
    <style>

    body {
        margin: 0;
        color: #FFFFFF;
        font-family: Arial, Helvetica, sans-serif;
        text-align: center;
    }

    #main_container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: hsl(70, 8%, 15%);
    }

    textarea {
        padding: 8px;
        width: calc((42 * 11 * 1px) - (8px * 2));
        background: #00000042;
        color: #FFFFFF;
        outline: none;
        border: none;
        resize: none;
        border-radius: 4px;
    }

    button {
        margin-top: 20px;
        padding-bottom: 8px;
        background: rebeccapurple;
        color: #FFFFFF;
        width: calc(42 * 11 * 1px);
        font-size: 16px;
        line-height: 16px;
        border: none;
        border-radius: 4px;
        cursor: pointer;
    }

    button svg {
        position: relative;
        bottom: -5px;
    }

    </style>
</head>
<body>


<div id="main_container">

    <h3>Copy To Clipboard Example</h3>

    <textarea id="textarea">su·per·ca·li·fra·gil·is·tic·ex·pi·a·li·do·cious</textarea>

    <button id="copy_button">

        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-sm">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M12 4C10.8954 4 10 4.89543 10 6H14C14 4.89543 13.1046 4 12 4ZM8.53513 4C9.22675 2.8044 10.5194 2 12 2C13.4806 2 14.7733 2.8044 15.4649 4H17C18.6569 4 20 5.34315 20 7V19C20 20.6569 18.6569 22 17 22H7C5.34315 22 4 20.6569 4 19V7C4 5.34315 5.34315 4 7 4H8.53513ZM8 6H7C6.44772 6 6 6.44772 6 7V19C6 19.5523 6.44772 20 7 20H17C17.5523 20 18 19.5523 18 19V7C18 6.44772 17.5523 6 17 6H16C16 7.10457 15.1046 8 14 8H10C8.89543 8 8 7.10457 8 6Z" fill="currentColor"></path>
        </svg>

        Copy To Clipboard

    </button>

</div>


<script>
// Add an event listener to the `copy_button` element
document.getElementById(`copy_button`).addEventListener(`click`, function() {

    // Retrieve the `textarea` element
    const textarea = document.getElementById(`textarea`);

    // Select the text inside the textarea
    textarea.select();

    // Copy the selected text to the clipboard
    document.execCommand(`copy`);

    // Change the inner HTML of the button to display a checkmark and the text `Copied!`
    // This is to provide visual feedback to the user that the text has been copied
    this.innerHTML = `

        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-sm">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M18.0633 5.67375C18.5196 5.98487 18.6374 6.607 18.3262 7.06331L10.8262 18.0633C10.6585 18.3093 10.3898 18.4678 10.0934 18.4956C9.79688 18.5234 9.50345 18.4176 9.29289 18.2071L4.79289 13.7071C4.40237 13.3166 4.40237 12.6834 4.79289 12.2929C5.18342 11.9023 5.81658 11.9023 6.20711 12.2929L9.85368 15.9394L16.6738 5.93664C16.9849 5.48033 17.607 5.36263 18.0633 5.67375Z" fill="currentColor"></path>
        </svg>

        Copied!

    `;

    // Set a timeout to revert the button content back to its original state after 2 seconds
    // This gives the user enough time to see the `Copied!` message before it disappears
    setTimeout(() => {

        this.innerHTML = `

            <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class="icon-sm">
                <path fill-rule="evenodd" clip-rule="evenodd" d="M12 4C10.8954 4 10 4.89543 10 6H14C14 4.89543 13.1046 4 12 4ZM8.53513 4C9.22675 2.8044 10.5194 2 12 2C13.4806 2 14.7733 2.8044 15.4649 4H17C18.6569 4 20 5.34315 20 7V19C20 20.6569 18.6569 22 17 22H7C5.34315 22 4 20.6569 4 19V7C4 5.34315 5.34315 4 7 4H8.53513ZM8 6H7C6.44772 6 6 6.44772 6 7V19C6 19.5523 6.44772 20 7 20H17C17.5523 20 18 19.5523 18 19V7C18 6.44772 17.5523 6 17 6H16C16 7.10457 15.1046 8 14 8H10C8.89543 8 8 7.10457 8 6Z" fill="currentColor"></path>
            </svg>

            Copy To Clipboard

        `;
    }, 2000);  // 2000 milliseconds = 2 seconds
});
</script>


</body>
</html>
```
