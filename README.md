# Uncommon HTML Error: innerHTML and Event Listener Misuse

This repository demonstrates a potential issue when using `innerHTML` within an event listener in HTML.  Improper use of `innerHTML` can lead to cross-site scripting (XSS) vulnerabilities and unexpected behavior, such as broken images.

## The Bug
The bug lies in how `innerHTML` is used to modify the content of the `div` element.  If the content being added via `innerHTML` comes from an untrusted source, it can introduce XSS vulnerabilities.
Additionally, the bug also uses a non-existent image, 'broken-image.jpg' which results in a broken image error. 

## The Solution
The solution avoids directly manipulating `innerHTML`. Instead, it uses DOM manipulation methods (`textContent` and `appendChild`) to add content more securely. The `textContent` approach avoids script injection and the `appendChild` method ensures the image is handled correctly. This ensures that the content is less vulnerable to XSS attacks and handles potential image issues gracefully.

## How to Reproduce
1. Clone this repository.
2. Open `bug.html` in your web browser.
3. Click on the div element.  Observe the change and potential errors.
4. Open `bugSolution.html` to see the corrected version.
