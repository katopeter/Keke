index.html:

<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Davun Utility</title>

    <link rel="stylesheet" href="styles.css">

</head>

<body>

    <h1>Save Utility</h1>

    <div class="container">

        <form id="save-form">

            <label for="data">Data:</label>

            <textarea id="data" name="data"></textarea>

            <button id="save-btn">Save</button>

        </form>

        <button id="load-btn">Load</button>

        <div id="loaded-data"></div>

    </div>

    <script src="script.js"></script>

</body>

</html>



styles.css:

body {

    font-family: Arial, sans-serif;

}



.container {

    max-width: 800px;

    margin: 40px auto;

    padding: 20px;

    background-color: #f9f9f9;

    border: 1px solid #ddd;

    border-radius: 10px;

    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);

}



script.js:

const saveForm = document.getElementById('save-form');

const saveBtn = document.getElementById('save-btn');

const loadBtn = document.getElementById('load-btn');

const loadedData = document.getElementById('loaded-data');



saveBtn.addEventListener('click', (e) => {

    e.preventDefault();

    const data = document.getElementById('data').value;

    localStorage.setItem('davun-data', data);

    alert('Data saved successfully!');

});



loadBtn.addEventListener('click', () => {

    const data = localStorage.getItem('davun-data');

    if (data) {

        loadedData.innerText = data;

    } else {

        alert('No data found!');

    }

}); 
