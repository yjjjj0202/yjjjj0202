<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Volunteer Hub</title>
    <style>
        /* Minimalist Styles */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background: #f0f8ff;
        }
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        .card {
            background: white;
            border-radius: 10px;
            padding: 20px;
            margin: 20px 0;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        select, button {
            width: 100%;
            padding: 12px;
            margin: 10px 0;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        button {
            background: #4CAF50;
            color: white;
            font-weight: bold;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Help Selection Card -->
        <div class="card">
            <h2>🌍 How Would You Like to Help?</h2>
            
            <!-- Step 1: Select Help Type -->
            <select id="helpType">
                <option value="">-- Select How to Help --</option>
                <option value="time">Volunteer Time</option>
                <option value="donate">Make a Donation</option>
                <option value="contact">Request More Info</option>
            </select>

            <!-- Step 2: Dynamic Content -->
            <div id="dynamicContent"></div>
        </div>
    </div>

    <script>
        const helpType = document.getElementById('helpType');
        const dynamicContent = document.getElementById('dynamicContent');

        helpType.addEventListener('change', (e) => {
            let html = '';
            switch(e.target.value) {
                case 'time':
                    html = `
                        <select id="activity">
                            <option>Select Volunteer Area</option>
                            <option>📚 Education Support</option>
                            <option>🌳 Environmental Protection</option>
                            <option>🏥 Medical Assistance</option>
                        </select>
                        <select id="frequency">
                            <option>Select Availability</option>
                            <option>Weekly</option>
                            <option>Monthly</option>
                            <option>Single Event</option>
                        </select>
                        <button onclick="submitForm()">Submit Application</button>
                    `;
                    break;

                case 'donate':
                    html = `
                        <select id="donateType">
                            <option>Select Donation Type</option>
                            <option>💰 Monetary Donation</option>
                            <option>🎁 Material Donation</option>
                        </select>
                        <select id="amount">
                            <option>Select Amount</option>
                            <option>$100 - $500</option>
                            <option>$500 - $1000</option>
                            <option>Other Amount</option>
                        </select>
                        <button onclick="submitForm()">Continue</button>
                    `;
                    break;

                case 'contact':
                    html = `
                        <input type="email" placeholder="Your Email" required>
                        <textarea placeholder="Message (Optional)" rows="3"></textarea>
                        <button onclick="submitForm()">Submit Request</button>
                    `;
                    break;
            }
            dynamicContent.innerHTML = html;
        });

        function submitForm() {
            alert('Thank you! Your submission has been received.');
            helpType.value = '';
            dynamicContent.innerHTML = '';
        }
    </script>
</body>
</html>

<!---
yjjjj0202/yjjjj0202 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
