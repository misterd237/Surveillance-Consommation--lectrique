# Surveillance-Consommation--lectrique
Un projet pour surveiller et analyser la consommation électrique en temps réel
# Surveillance de la Consommation Électrique
# Ce script récupère et affiche les données de consommation électrique

import time
import random
import json
from flask import Flask, jsonify

app = Flask(__name__)

def get_power_usage():
    return round(random.uniform(50, 500), 2)

@app.route('/power', methods=['GET'])
def power_data():
    power = get_power_usage()
    return jsonify({"power_usage": power})

if __name__ == "__main__":
    print("Démarrage du serveur Flask pour la surveillance électrique...")
    app.run(host='0.0.0.0', port=5000)
