Das sind wichtige Zusatzinformationen zu der Hardware und den Firmware-Updates deiner CF-Drone (speziell für das Chenguang E1 Mini / 琛光E1 Mini Projekt).
Da die Firmware mittlerweile auch die neueren Chips ESP32-S3 und ESP32-C3 unterstützt, musst du bei der Board-Auswahl in der Arduino IDE genau aufpassen, welchen Chip deine Drohne tatsächlich verwendet.
Hier ist die angepasste Anleitung für deine Arduino IDE basierend auf den neuen Projektdaten:

🛠️ Ergänzende Schritte für die Board-Auswahl

Bevor du auf "Kompilieren" oder "Hochladen" klickst, überprüfe die Hardware deiner Drohne:
1. Den richtigen Chip (Board) auswählen:
Schaue auf die Beschriftung des silbernen oder schwarzen Hauptchips auf deiner Drohne. Wähle dann in der Arduino IDE unter Tools (Werkzeuge) > Board > esp32 das exakt passende Modell:
	• Klassischer ESP32 (30-PIN): Wähle ESP32 Dev Module oder WeMOS D1 MINI ESP32.
	• ESP32-S3: Wähle ESP32S3 Dev Module (oder das spezifische S3-Board, das du nutzt).
	• ESP32-C3: Wähle ESP32C3 Dev Module.
2. Wichtiger Hinweis zu den Updates:
Die Firmware enthält Sicherheitsfunktionen wie den Inversionsschutz (倒置保护 – schaltet die Motoren ab, wenn die Drohne zu lange auf dem Kopf steht) sowie automatische Sicherheitslandungen bei schwacher Batterie. Teste die Motoren daher beim ersten Mal am besten ohne montierte Propeller über die Konsole (Befehle: mfl, mfr, mrl, mrr).

📡 Erste Schritte nach dem Flashen (Kalibrierung)

Sobald der Code erfolgreich auf das Board geladen wurde, musst du die Drohne kalibrieren, damit sie stabil fliegt:
1. Verbinde dein Smartphone mit dem WLAN der Drohne (Drone_WIFI, Passwort: 12345678).
2. Öffne den Browser und rufe http://192.168.4.1 auf.
3. Klicke auf "Anpassen/Debug" (调试) und gib den Befehl ca ein, um den Lagesensor (IMU) in 6 Positionen zu kalibrieren. Befolge dabei einfach die Bildschirmanweisungen.
Lass mich wissen, falls du Hilfe beim Code brauchst:
• Welchen ESP32-Chip (Klassisch, S3 oder C3) hast du auf deiner Platine verbaut?
• Konntest du das Projekt in der Arduino IDE bereits fehlerfrei überprüfen (Verify)?
