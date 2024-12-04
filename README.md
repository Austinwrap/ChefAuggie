<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chef Augustus Co</title>
    <style>
        /* General Styling */
        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #fff5f7;
            color: #4c4c4c;
            text-align: center;
        }
        header {
            background-color: #ff7675;
            color: white;
            padding: 20px 10px;
            border-bottom: 5px solid #fab1a0;
        }
        header h1 {
            font-size: 3em;
            margin: 0;
            letter-spacing: 2px;
            text-shadow: 2px 2px #d63031;
        }
        header p {
            font-size: 1.4em;
            margin: 5px 0 15px;
            color: #fdebd0;
        }
        .container {
            max-width: 800px;
            margin: 30px auto;
            padding: 20px;
            background-color: #ffffff;
            border-radius: 20px;
            box-shadow: 0 8px 15px rgba(0, 0, 0, 0.15);
            border: 2px dashed #fab1a0;
        }
        form {
            text-align: left;
        }
        label {
            font-weight: bold;
            margin-top: 20px;
            display: flex;
            align-items: center;
            color: #d63031;
        }
        label::before {
            content: '🍴';
            margin-right: 10px;
            font-size: 1.2em;
        }
        select, input, textarea, button {
            width: 100%;
            margin-top: 10px;
            padding: 12px;
            font-size: 1.1em;
            border: 2px solid #fab1a0;
            border-radius: 15px;
            background-color: #fff7f7;
            outline: none;
            transition: all 0.3s ease;
        }
        select:hover, input:hover, textarea:hover {
            background-color: #ffebec;
            border-color: #d63031;
        }
        button {
            background-color: #ff7675;
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.2s ease, background-color 0.3s ease;
        }
        button:hover {
            background-color: #d63031;
            transform: scale(1.05);
        }
        textarea {
            height: 120px;
        }
        footer {
            margin-top: 30px;
            font-size: 0.9em;
            color: #9ca3af;
        }
        footer p {
            margin: 0;
        }
        /* Icon enhancements */
        label[for="serviceType"]::before {
            content: '🧑‍🍳';
        }
        label[for="guestCount"]::before {
            content: '🍽️';
        }
        label[for="tourDuration"]::before {
            content: '🛻';
        }
        label[for="date"]::before {
            content: '📅';
        }
        label[for="addOns"]::before {
            content: '✨';
        }
        label[for="details"]::before {
            content: '📝';
        }
    </style>
</head>
<body>

<header>
    <h1>Chef Augustus</h1>
    <p>Cooking up unforgettable experiences!</p>
</header>

<div class="container">
    <form id="quoteForm">
        <h2>Get a Quote</h2>
        
        <label for="serviceType">What service do you need?</label>
        <select id="serviceType" name="serviceType">
            <option value="privateChef">Private Chef for a Day</option>
            <option value="tourChef">Tour Chef Services</option>
        </select>

        <label for="guestCount">Number of guests (for private chef):</label>
        <select id="guestCount" name="guestCount">
            <option value="2">2</option>
            <option value="3-8">3-8</option>
            <option value="9-20">9-20</option>
        </select>

        <label for="tourDuration">Duration of tour (for tour chef):</label>
        <select id="tourDuration" name="tourDuration">
            <option value="1-week">1 Week</option>
            <option value="2-weeks">2 Weeks</option>
            <option value="1-month">1 Month</option>
            <option value="custom">Custom Duration</option>
        </select>

        <label for="date">Preferred Date:</label>
        <input type="date" id="date" name="date">

        <label for="addOns">Additional Services:</label>
        <select id="addOns" name="addOns" multiple>
            <option value="server">Server Assistance</option>
            <option value="customMenu">Custom Menu Planning</option>
            <option value="winePairing">Wine Pairing Recommendations</option>
        </select>

        <label for="details">Any special requests or details?</label>
        <textarea id="details" name="details" placeholder="Let us know about dietary restrictions, themes, etc."></textarea>

        <button type="submit">Submit Your Request</button>
    </form>
</div>

<footer>
    <p>Chef Augustus Co &copy; 2024 | Let's Make Something Delicious!</p>
</footer>

<script>
    document.getElementById('quoteForm').addEventListener('submit', function(event) {
        event.preventDefault();

        // Collect form data
        const serviceType = document.getElementById('serviceType').value;
        const guestCount = document.getElementById('guestCount').value;
        const tourDuration = document.getElementById('tourDuration').value;
        const date = document.getElementById('date').value;
        const addOns = Array.from(document.getElementById('addOns').selectedOptions).map(option => option.text).join(', ');
        const details = document.getElementById('details').value;

        // Create email content
        const subject = encodeURIComponent('New Service Request for Chef Augustus Co');
        const body = encodeURIComponent(
            `Service Type: ${serviceType}\n` +
            `Guest Count: ${guestCount}\n` +
            `Tour Duration: ${tourDuration}\n` +
            `Preferred Date: ${date}\n` +
            `Additional Services: ${addOns}\n` +
            `Details: ${details}`
        );

        // Open email client
        window.location.href = `mailto:aytmout@gmail.com?subject=${subject}&body=${body}`;
    });
</script>

</body>
</html>
