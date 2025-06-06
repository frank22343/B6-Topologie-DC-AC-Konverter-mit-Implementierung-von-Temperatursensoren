# B6-Topologie-DC-AC-Konverter-mit-Implementierung-von-Temperatursensoren

**Beschreibung:**
Im Rahmen dieses Projekts wurde ein dreiphasiger DC/AC-Konverter in B6-Topologie entwickelt, der aus einer Gleichspannungsquelle eine symmetrische dreiphasige Wechselspannung erzeugt. Der Aufbau umfasst eine vollständig integrierte Gate-Treiber-Sektion mit galvanischer Trennung sowie eine Temperaturüberwachung der Leistungshalbleiter zur Erhöhung der Betriebssicherheit. Ziel war ein kompakter, effizienter und thermisch überwachter Wechselrichter für industrielle Anwendungen oder Motoransteuerungen.

# Technische Hauptmerkmale

Topologie: Dreiphasiger Brückenwechselrichter (B6-Topologie)
Eingang: Gleichspannung (z. B. aus Batterie oder Netzgleichrichter)
Ausgang: Dreiphasige sinusähnliche Spannung (400V RMS)
Schaltfrequenz: z. B. 10–20 kHz
Leistungshalbleiter: IGBTs in Halbbrücken-Konfiguration
Gate-Treiber: Isolierte Treiber-ICs für sichere Ansteuerung der High- und Low-Side
Temperatursensoren: **TMP1075DGKR** zur Überwachung kritischer Komponenten
Schutzmechanismen: Temperaturabschaltung, Lüftersteuerung, Überspannungsschutz
Leiterplattenlayout: EMV-gerechtes Design mit Massekonzept und kurzen Gate-Leitungen

# 1. Leistungsteil (Rechts im Schaltplan)
Sechs Leistungstransistoren bilden die klassische B6-Brücke (3 Halbbrücken).
Jeder Zweig erzeugt eine Phase der Ausgangsspannung.
Zwischen den Brückenzweigen und dem Lastanschluss sind Freilaufdioden und Snubber-Netzwerke integriert.

# 2. Gate-Treiber (Links im Schaltplan)
Jede Halbbrücke wird über einen eigenen Gate-Treiber-IC angesteuert.
Die Ansteuerung erfolgt differenziell oder per PWM über isolierte Signale.
Galvanische Trennung (z. B. über Transformatoren oder Optokoppler) schützt die Steuerlogik.
Bootstrap-Kondensatoren ermöglichen High-Side-Ansteuerung.

# 3. Temperatursensorik (Mitte im Schaltplan)
Temperaturmessung an MOSFETs, Kühlkörper oder Transformator über TMP1075DGKR.
Verstärkung und Aufbereitung des Sensorsignals zur Weiterverarbeitung (z. B. durch ADC).
Bei Überschreitung eines Schwellwerts wird ein Schutzsignal ausgelöst oder ein Lüfter aktiviert.

# Entwicklungswerkzeuge
Schaltungsentwurf: Altium Designer
Simulation: LTspice(für Schaltverhalten und thermische Analyse)
Berechnungshilfen: TI Power Designer, WEBENCH
Messung & Validierung: Oszilloskop, Lastwiderstände

<img width="377" alt="image" src="https://github.com/user-attachments/assets/f6d65189-bcd3-462a-92f6-42a8efdda5ac" />

<img width="395" alt="image" src="https://github.com/user-attachments/assets/2a188489-aa51-4511-9cdc-9d84c0223dd1" />


