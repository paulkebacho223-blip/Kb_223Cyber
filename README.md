
from flask import Flask, request, jsonify

app = Flask(__name__)

@app.route('/sms-webhook', methods=['POST'])
def receive_sms():
    data = request.json
    print("--- UJUMBE MPYA UMEINGIA ---")
    print(f"Kutoka: {data.get('from')}")
    print(f"Ujumbe: {data.get('message')}")
    return jsonify({"status": "success"}), 200

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)
