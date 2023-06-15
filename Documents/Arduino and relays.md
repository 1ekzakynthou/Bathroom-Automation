﻿**Ηλεκτρονόμος / ρελέ (relay ) και relay module**

Ο ηλεκτρονόμος, ρελέ(*relay*)  είναι ένας ηλεκτρικός διακόπτης που ανοίγει και κλείνει ένα ηλεκτρικό κύκλωμα υπό τον έλεγχο ενός άλλου ηλεκτρικού κυκλώματος και χρησιμοποιείται κατά κόρον σε αυτοματισμούς. Μπορεί  να ελέγχει ένα κύκλωμα εξόδου υψηλότερης ισχύος από το κύκλωμα εισόδου χαμηλότερης ισχύος.

Αυτός είναι και ο λόγος που το χρησιμοποιούμε με τον μικροελεγκτή Arduino, αφού οι ακροδέκτες εξόδου μπορούν να δώσουν τάση  5 V ενώ μπορεί να θέλουμε να ελέγξουμε μια συσκευή που δουλεύει π.χ. στα 250 V  ,AC. Για τον έλεγχο περισσότερων συσκευών/φορτίων υπάρχουν relay module  δύο, τεσσάρων ,οκτώ κ.λ.π καναλιών.

![relay](https://github.com/1ekzakynthou/Bathroom-Automation/assets/80713520/d142e1f7-59a4-4428-b621-43ff29075d06)

             













Ανάλογα  με τον κατασκευαστή μπορούμε να έχουμε τις εξής περιπτώσεις:

HIGH trigger : σημαίνει οτι το ρελέ ενεργοποιείται όταν στην είσοδο έχουμε 5 Volt (HIGH)
LOW trigger : σημαίνει οτι το ρελέ ενεργοποιείται όταν στην είσοδο έχουμε 0 Volt (LOW)
Αντίστοιχα στις εξόδους μπορούμε να συνδέσουμε το φορτίο μας (π.χ λαμπτήρα) σε μια  επαφή 
NO (Normally Open) που θα αντιστοιχεί σε ανοιχτό διακόπτη όταν το ρελε δεν είναι ενεργοποιημένο και αντίθετα σε μια NC επαφή που θα αντιστοιχεί σε κλειστό διακόπτη όταν το ρελέ δεν είναι ενεργοποιημένο.

Για την καλύτερη κατανόηση δίνονται οι παρακάτω εικόνες (πηγή: <https://ncd.io/blog/relay-logic/>)

![relay1](https://github.com/1ekzakynthou/Bathroom-Automation/assets/80713520/695f328b-cc02-4c2e-b39d-c291299c87ca)


![relay2](https://github.com/1ekzakynthou/Bathroom-Automation/assets/80713520/38851588-caf8-4fab-af55-64115173d904)

















Όλοι οι δυνατοί συνδυασμοί φαίνονται στον παρακάτω πίνακα: 
(πηγή: https://arduinogetstarted.com/tutorials/arduino-relay)
![I_O relay state](https://github.com/1ekzakynthou/Bathroom-Automation/assets/80713520/0f7d9079-f1c4-4ff7-b271-8fa92e49dac2)



!!!!!! Ιδιαίτερη προσοχή χρειάζεται στην πλευρά εξόδου του Ηλεκτρονόμου όπου συνδέεται στη υψηλή Τάση . Να γίνεται από ενήλικο άτομο που είναι γνώστης.
![how-to-connect-device-to-relay](https://github.com/1ekzakynthou/Bathroom-Automation/assets/80713520/711be77a-9a9a-4db4-91aa-0f841740574e)

![relay-open_bb](https://github.com/1ekzakynthou/Bathroom-Automation/assets/80713520/08dd22db-9371-4199-920e-2aa473b83c5d)


## <a name="arduino-example-code"></a>**Παράδειγμα κώδικα Arduino**
Ο έλεγχος μιας μονάδας ρελέ με το Arduino είναι τόσο εύκολος όσο ο έλεγχος ενός LED. Εδώ είναι ένας απλός κωδικός που θα ενεργοποιήσει το ρελέ για 5 δευτερόλεπτα και στη συνέχεια θα το απενεργοποιήσει για 5 δευτερόλεπτα. Στο παράδειγμα αυτό το ρελέ είναι Low trigger και η είσοδος του ρελέ (ΙΝ) αποτελεί έξοδο(OUTPUT) για το Arduino (pin 6)


int RelayPin = 6;

void setup() {

`        `// Set RelayPin as an output pin

`        `pinMode(RelayPin, OUTPUT);

}

void loop() {

`        `// Turn on the relay...

`        `digitalWrite(RelayPin, LOW);

`        `delay(5000);



`        `// Turn off the relay...

`        `digitalWrite(RelayPin, HIGH);

`        `delay(5000);

}
###
