from flask import Flask, jsonify
import random  # For simulating market data analysis

app = Flask(__name__)

# Mock function for market analysis (replace with actual market analysis)
def analyze_market():
    # Randomly pick "up" or "down" as a signal
    signal = random.choice(['up', 'down'])
    return signal

@app.route('/get-signal', methods=['GET'])
def get_signal():
    signal = analyze_market()  # Analyze market and get signal
    return jsonify({'signal': signal})

if __name__ == '__main__':
    app.run(debug=True)
