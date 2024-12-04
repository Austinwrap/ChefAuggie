<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chef Augustus</title>
    <style>
        /* General Styling */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f0f4ff;
            color: #333;
            text-align: center;
        }
        header {
            background-color: #4a90e2;
            color: white;
            padding: 20px 10px;
            border-bottom: 5px solid #356abd;
        }
        header h1 {
            font-size: 2.8em;
            margin: 0;
            letter-spacing: 1.5px;
            text-shadow: 1px 1px #2c5282;
        }
        header p {
            font-size: 1.3em;
            margin: 5px 0 15px;
            color: #dce7f8;
        }
        .container {
            max-width: 800px;
            margin: 30px auto;
            padding: 20px;
            background-color: #fff;
            border-radius: 15px;
            box-shadow: 0 6px 10px rgba(0, 0, 0, 0.1);
            border: 2px solid #a1c4fd;
        }
        form {
            text-align: left;
        }
        label {
            font-weight: bold;
            margin-top: 15px;
            display: block;
            color: #4a90e2;
        }
        select, input, textarea, button {
            width: 100%;
            margin-top: 10px;
            padding: 12px;
            font-size: 1.1em;
            border: 1px solid #a1c4fd;
            border-radius: 10px;
            background-color: #f9faff;
            outline: none;
            transition: all 0.3s ease;
        }
        select:hover, input:hover, textarea:hover {
            background-color: #eef4ff;
            border-color: #4a90e2;
        }
        button {
            background-color: #4a90e2;
            color: white;
            font-weight: bold;
            cursor: pointer;
            transition: transform 0.2s ease, background-color 0.3s ease;
        }
        button:hover {
            background-color: #356abd;
            transform: scale(1.05);
        }
        textarea {
            height: 120px;
        }
        .checkbox-group {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        .checkbox-group label {
            margin: 0;
            font-size: 1em;
            font-weight: normal;
            color: #333;
        }
        .about {
            margin-bottom: 20px;
            position: relative;
            background-color: #e1edfa;
            border: 2px solid #4a90e2;
            border-radius: 20px;
            padding: 15px;
            width: 85%;
            margin: 20px auto;
            font-size: 0.9em;
            text-align: left;
            line-height: 1.6;
        }
        .about:before {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 40px;
            width: 30px;
            height: 30px;
            background-color: #e1edfa;
            border: 2px solid #4a90e2;
            border-radius: 50%;
            transform: rotate(45deg);
            z-index: -1;
        }
        .hidden {
            display: none;
        }
        footer {
            margin-top: 30px;
            font-size: 0.9em;
            color: #6c757d;
        }
        footer p {
            margin: 0;
        }
    </style>
</head>
<body>

<header>
    <h1>Chef Augustus</h1>
    <p>Cooking up unforgettable experiences for any occasion!</p>
</header>

<div class="container">
    <div class="about">
        <p>
            Hi! I'm Augustus Griffen, a professional chef with years of experience in high-quality dining establishments. 
            I’ve toured with a band, preparing healthy, delicious meals three times a day, and I specialize in grocery 
            shopping, meal prep, and serving large parties of over 20 people. If you need a private chef for an event or a tour, I’m your guy!
        </p>
    </div>
    
    <form id="quoteForm">
        <h2>Get a Quote</h2>
        
        <label for="name">Your Name:</label>
        <input type="text" id="name" name="name" placeholder="Enter your full name" required>

        <label for="phone">Best Phone Number:</label>
        <input type="tel" id="phone" name="phone" placeholder="Enter your phone number" required>

        <label for="email">Your Email:</label>
        <input type="email" id="email" name="email" placeholder="Enter your email address" required>
        
        <label for="serviceType">What service do you need?</label>
        <select id="serviceType" name="serviceType" onchange="toggleFields()" required>
            <option value="privateChef">Private Chef for a Day</option>
            <option value="tourChef">Tour Chef Services</option>
        </select>

        <div id="tourPeopleField" class="hidden">
            <label for="tourPeople">Number of people on tour:</label>
            <input type="number" id="tourPeople" name="tourPeople" placeholder="Enter the number of people" min="1">
        </div>

        <div id="guestCountField">
            <label for="guestCount">Number of guests (for private chef):</label>
            <select id="guestCount" name="guestCount">
                <option value="2">2</option>
                <option value="3-8">3-8</option>
                <option value="9-20">9-20</option>
            </select>
        </div>

        <label for="date">Preferred Date:</label>
        <input type="date" id="date" name="date">

        <label for="addOns">Additional Services:</label>
        <div class="checkbox-group" id="addOns">
            <label><input type="checkbox" value="Server Assistance"> Server Assistance</label>
            <label><input type="checkbox" value="Custom Menu Planning"> Custom Menu Planning</label>
            <label><input type="checkbox" value="Wine Pairing Recommendations"> Wine Pairing Recommendations</label>
        </div>

        <label for="details">Any special requests or details?</label>
        <textarea id="details" name="details" placeholder="Let us know about dietary restrictions, themes, etc."></textarea>

        <button type="submit">Submit Your Request</button>
    </form>
</div>

<footer>
    <p>Chef Augustus &copy; 2024 | Let’s create something delicious!</p>
</footer>

<script>
    function toggleFields() {
        const serviceType = document.getElementById('serviceType').value;
        const tourField = document.getElementById('tourPeopleField');
        const guestField = document.getElementById('guestCountField');
        if (serviceType === 'tourChef') {
            tourField.classList.remove('hidden');
            guestField.classList.add('hidden');
        } else {
            tourField.classList.add('hidden');
            guestField.classList.remove('hidden');
        }
    }

    document.getElementById('quoteForm').addEventListener('submit', function(event) {
        event.preventDefault();

        // Collect form data
        const name = document.getElementById('name').value;
        const phone = document.getElementById('phone').value;
        const email = document.getElementById('email').value;
        const serviceType = document.getElementById('serviceType').value;
        const tourPeople = document.getElementById('tourPeople').value || 'N/A';
        const guestCount = document.getElementById('guestCount').value || 'N/A';
        const date = document.getElementById('date').value;
        const addOns = Array.from(document.querySelectorAll('#addOns input:checked'))
                            .map(checkbox => checkbox.value)
                            .join(', ');
        const details = document.getElementById('details').value;

        // Create email content
        const subject = encodeURIComponent('New Service Request for Chef Augustus');
        const body = encodeURIComponent(
            `=== Customer Details ===\n` +
            `Name: ${name}\n` +
            `Phone: ${phone}\n` +
            `Email: ${email}\n\n` +
            `=== Service Information ===\n` +
            `Service Type: ${serviceType}\n` +
            (serviceType === 'tourChef' ? `Number of People on Tour: ${tourPeople}\n` : `Number of Guests: ${guestCount}\n`) +
            `Preferred Date: ${date}\n\n` +
            `=== Additional Services ===\n` +
            `${addOns || 'None'}\n\n` +
            `=== Special Requests ===\n` +
            `${details || 'None'}`
        );

        // Open email client
        window.location.href = `mailto:aytmout@gmail.com?subject=${subject}&body=${body}`;
    });
</script>

</body>
</html>
