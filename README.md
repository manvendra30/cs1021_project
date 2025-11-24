Phishing URL Detector

A lightweight, Python-based security tool that uses the Random Forest algorithm to detect potential phishing URLs. This system analyzes the lexical and structural properties of a URL to determine if it is legitimate or malicious without relying on external blocklists.

Features

Offline Analysis: fast detection without needing external API calls or internet access.

Entropy Analysis: Calculates Shannon Entropy to detect random gibberish (e.g., x82js-secure.com).

Pattern Recognition: Identifies common phishing tactics like IP address usage, excessive hyphens, and suspicious keywords (e.g., "verify", "paypal").

Confidence Scoring: Provides a percentage probability score for every prediction.

Interactive CLI: Simple command-line interface for real-time testing.

Prerequisites

To run this tool, you need Python 3 installed along with the following data science libraries:

pandas

numpy

scikit-learn

Installation

Clone or Download this repository.

Install dependencies using pip:

pip install pandas numpy scikit-learn


Usage

Run the script in your terminal:

python phishing_detector.py


The script will first train the model on the internal dataset.

Once the "URL CHECKER" prompt appears, paste a URL to test it.

Example Interaction

Link: [http://secure-paypal-update.xyz/login](http://secure-paypal-update.xyz/login)

Verdict: PHISHING 
Certainty: 94.00%
 Why it looks bad:
   - Suspicious keyword detected: 'paypal'
   - Suspicious keyword detected: 'secure'


How It Works

The Detector class extracts specific features from the raw URL string to feed into a Random Forest Classifier:

Structural Features: Length of the URL, length of the domain, and counts of special characters (dots, hyphens, @ symbols).

Lexical Features: Checks if the domain is a raw IP address or contains "social engineering" keywords often used by attackers.

Entropy Calculation: Measures the randomness of the text. Legitimate domains usually have low entropy (readable words), while malicious domains often have high entropy (random characters).

Disclaimer

This tool is for educational purposes only. While it uses effective heuristics, it is trained on a small demonstration dataset. For production security, always rely on comprehensive browser protections and verified threat intelligence feeds.

Author: Manvendra
License: Open Source
