<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Website with Dummy Data</title>
</head>
<body>
    <h1>Dummy Data</h1>
    <ul id="dummy-list"></ul>
       <script>
        // Fetch dummy data from the server
        fetch('/get_dummy_data')
            .then(response => response.json())
            .then(data => {
                const dummyList = document.getElementById('dummy-list');
                data.forEach(item => {
                    const listItem = document.createElement('li');
                    listItem.textContent = item.name;
                    dummyList.appendChild(listItem);
                });
            })
            .catch(error => console.error(error));
    </script>
</body>
</html>
