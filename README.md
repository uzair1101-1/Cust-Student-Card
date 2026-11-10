Student Card

A responsive, flippable university student ID card built with HTML, CSS and a little JavaScript. The front side shows the student's photo and details. The back side shows instructions, a scannable QR code, and the university address and contact information.

📑 Table of Contents
Overview
Features
Technologies Used
Project Structure
Getting Started
Usage
Customization
Responsive Design
Browser Support
Known Issues
Future Improvements
Author
License
📖 Overview

This project is a digital student ID card for Capital University of Science & Technology (CUST). It is a single-page design with no frameworks and no build tools, so it is easy to read, edit and run.

✨ Features
3D flip animation between the front and back of the card
Flip by clicking the card or the Flip card button
Front side: university logo, student photo, name, father name, student ID, program, issue date, issuing authority signature and validity date
Back side: card instructions, QR code, student ID text, university name, address, email and contact number
Real, scannable QR code generated with JavaScript
Fully responsive for desktop and small mobile screens
Keyboard-friendly button with a visible focus outline
Supports the "reduce motion" accessibility setting
Easy theme change through CSS variables
🛠 Technologies Used
Technology	Purpose
HTML5	Page structure
CSS3	Styling, Flexbox, Grid, 3D transforms, CSS variables
JavaScript (Vanilla)	Card flip and QR generation
QRCode.js	QR code generation (loaded from cdnjs)
📁 Project Structure
student-card/
├── index.html          # Card layout, flip logic and QR code script
├── style.css           # All styles for the card
├── images.png          # University logo
├── uzair.image.jpeg    # Student photo
└── README.md           # Project documentation
🚀 Getting Started
Requirements
A modern web browser (Chrome, Edge, Firefox, Safari)
Internet connection (only needed to load the QR code library)
Installation
Download or clone the project.
Make sure all files are in the same folder:
index.html
style.css
images.png
uzair.image.jpeg
Open index.html in your browser.

No installation, server or build step is needed.

💡 Usage
Click the card or the Flip card button to flip between front and back.
Scan the QR code on the back with a phone to see the stored data (by default, the student ID).
🎨 Customization
1. Change student details

In index.html:

html
<dt>Name:</dt><dd>Uzair Khan</dd>
<dt>Father Name:</dt><dd>Bahadur Khan</dd>
<dt>Student ID:</dt><dd>BSE241111</dd>
<dt>Program:</dt><dd>BSE</dd>
<dt>Date of Issuse:</dt><dd>02-feb-2024</dd>
2. Change the logo and photo

Replace the image files, or update the file names in index.html:

html
<img src="images.png" alt="University logo">
<img src="uzair.image.jpeg" alt="Student photo">
3. Change the signature and validity
html
<span class="signature-text">Uzair</span>
<span class="valid">Valid till - <span class="date">Feb 2028</span></span>
4. Change the QR code data

At the bottom of index.html, edit text. It can be a student ID, a link or any text:

js
new QRCode(document.getElementById('qr'), {
  text: 'BSE241111',
  width: 96,
  height: 96,
  colorDark: '#161b22',
  colorLight: '#ffffff',
  correctLevel: QRCode.CorrectLevel.M
});

Also update the text under the QR code:

html
<span class="code-text">BSE241111</span>
5. Change the QR size on the card

In style.css:

css
.qr {
  width: 48px;
  height: 48px;
}
6. Change the colors

In style.css, edit the variables at the top:

css
:root {
  --blue: #2a68b8;
  --blue-dark: #17407e;
  --red: #c9302a;
  --red-dark: #9e211c;
  --paper: #ffffff;
  --ink: #161b22;
  --muted: #5d6670;
  --page: #dfe3e8;
  --line: #d5dbe3;
}
7. Change instructions, address and contact

Edit the <ol class="rules"> list and the .back-bottom section in index.html.

📱 Responsive Design
The card width is min(400px, 100%) and keeps a standard ID-card ratio (1.586).
On screens 380px wide or smaller, font sizes, photo size and spacing are reduced so the card still fits.
🌐 Browser Support
Browser	Supported
Google Chrome	✅
Microsoft Edge	✅
Mozilla Firefox	✅
Safari	✅
⚠️ Known Issues
Spelling mistakes in the card: "Unversity" should be "University" and "Issuse" should be "Issue".
The contact number +92 51 000 0000 is a placeholder. Replace it with the real number.
The QR code library loads from the internet. Without internet, the QR code will not appear. To work offline, download qrcode.min.js and link it locally.
On very small cards, the QR code may be hard to scan. Increase .qr size if needed.
🔮 Future Improvements
Print-ready version of the card (front and back)
Download card as an image or PDF
Load student data from a JSON file or database
Dark mode for the page background
Multiple student cards from one template
👤 Author

Uzair Khan Student ID: BSE241111 Capital University of Science & Technology, Islamabad

📄 License

This project is for educational purposes. You are free to use and modify it for learning.
