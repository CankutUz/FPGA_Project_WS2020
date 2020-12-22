# signal_processing

Die Signalverarbeitung erhält gemessene Beschleunigungsdaten von der SPI-Schnittstelle und verarbeitet diese.

Die Daten werden in einen Zwischenspeicher geschoben, welcher die Rohdaten  an eine UART-Schnittstelle übergibt oder als zweiten Datenpfad an eine Bildsignalberechnung zur anschließenden Ausgabe an einer VGA-Schnittstelle weiterreicht.

Nachfolgend die Schnittstellen aus Sicht der Signalverarbeitung:


## --------------------------Sensor Modul----------------------------------

Eingänge:

* **EN** 	  : std_logic = 1 {Enable Signal}
* **Reset** :	std_logic = 0 {Reset Signal}
* **Clk**   :	std_logic     {Clock Signal}

* **acc_x** : signed integer range) {in m/s²}
* **acc_y** : signed integer range) {in m/s²}
* **acc_z** : signed integer range) {in m/s²}

* **EN** : std_logic = 1 {Enable Signal}
* **Reset** : std_logic = 0 {Reset Signal}


## -------------------------------UART -------------------------------------

Eingänge:

* **TX_BUSY**    : std_logic {Busy Signal des UART}

**NICHT IMPLEMENTIERT:**
* **RX_EN**
* **RX_DATA[]**
* **RX_ERROR**


Ausgänge:

* **Reset**      : std_logic = 0 {Reset Signal}
* **Clk**        : std_logic     {Clock Signal}
* **TX_EN**      : std_logic = 0 {Enable Signal des UART}
* **TX_DATA[]**  : std_logic_vector[7..0] = x00 {Daten zum UART}

**NICHT IMPLEMENTIERT:**
* **RX_BUSY**

## -------------------------------VGA --------------------------------------

Eingänge:

Ausgänge:
