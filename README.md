# B6-Topologie-DC-AC-Konverter-mit-Implementierung-von-Temperatursensoren

**Beschreibung:**
Im Rahmen dieses Projekts wurde ein dreiphasiger DC/AC-Konverter in B6-Topologie entwickelt, der aus einer Gleichspannungsquelle eine symmetrische dreiphasige Wechselspannung erzeugt. Der Aufbau umfasst eine vollständig integrierte Gate-Treiber-Sektion mit galvanischer Trennung sowie eine Temperaturüberwachung der Leistungshalbleiter zur Erhöhung der Betriebssicherheit. Ziel war ein kompakter, effizienter und thermisch überwachter Wechselrichter für industrielle Anwendungen oder Motoransteuerungen.

![Screenshot 2025-06-12 030200](https://github.com/user-attachments/assets/7fd6c711-e7ef-49f9-9825-48bb0435c78f)


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

# 1. Leistungsteil (Oben im Zentrum)
Sechs Leistungstransistoren bilden die klassische B6-Brücke (3 Halbbrücken).
Jeder Zweig erzeugt eine Phase der Ausgangsspannung.
Zwischen den Brückenzweigen und dem Lastanschluss sind Freilaufdioden und Snubber-Netzwerke integriert.

# 2. Gate-Treiber (im Zentrum)
Jede Halbbrücke wird über einen eigenen Gate-Treiber-IC angesteuert.
Die Ansteuerung erfolgt differenziell oder per PWM über isolierte Signale.
Galvanische Trennung (z. B. über Transformatoren oder Optokoppler) schützt die Steuerlogik.
Bootstrap-Kondensatoren ermöglichen High-Side-Ansteuerung.

# 3. Temperatursensorik (Neben Leistungsschalter)
Temperaturmessung an MOSFETs, Kühlkörper oder Transformator über TMP1075DGKR.
Verstärkung und Aufbereitung des Sensorsignals zur Weiterverarbeitung (z. B. durch ADC).
Bei Überschreitung eines Schwellwerts wird ein Schutzsignal ausgelöst oder ein Lüfter aktiviert.

# Entwicklungswerkzeuge
Schaltungsentwurf: Altium Designer
Simulation: LTspice(für Schaltverhalten und thermische Analyse)
Berechnungshilfen: TI Power Designer, WEBENCH
Messung & Validierung: Oszilloskop, Lastwiderstände

![Screenshot 2025-06-08 131743](https://github.com/user-attachments/assets/7da861ab-5359-49b0-b9ef-6324045455c4)


![Screenshot 2025-06-08 131802](https://github.com/user-attachments/assets/78947583-a677-43be-9cd3-44ddfb636bf1)



