!pip install mmh3
!pip install bitarray
Ακολουθεί μια σύντομη περιγραφή κάθε βιβλιοθήκης:
mmh3: Η βιβλιοθήκη mmh3 (MurmurHash3) είναι μία βιβλιοθήκη η οποία περιέχει
συναρτήσεις κατακερματισμού (hush functions). Τα δεδομένα που εισάγονται σε μια
συνάρτηση μετατρέπονται σε μία ακολουθία από bits σταθερού μήκους, σύμφωνα με
τον τύπο της συνάρτησης. Αξίζει να σημειωθεί πως η συνάρτηση δεν έχει δημιουργηθεί
για να δυσκολέψει τον κακόβουλο χρήστη να βρει την αντίστροφη διαδικασία για την
παραγωγή της εν λόγο ακολουθίας σταθερού μεγέθους, αλλά για να γίνεται μία
γρήγορη και ευέλικτη αναζήτηση μεταξύ των αποτελεσμάτων της ώστε να βρίσκεται
τυχόν ταύτιση ενός δείγματος με την βάση μας.
bitarray: Η βιβλιοθήκη bitarray είναι μία συνάρτηση που αποσκοπεί στην διαχείριση
των πινάκων που αποτελούνται απά στοιχεία 0 και 1. Οι παραπάνω πίνακες είναι
ακολουθίες ή συμβολοσειρές εύκολα διαχειρίσιμες που πάνω σε αυτούς βασίζεται η
λειτουργία των bloom filters, σύμφωνα με όσα έχουν περιγραφεί σε όλη την έκταση της
εργασίας.
5.2 Λειτουργίες
Ο κώδικας υλοποιεί ένα bloom filter, το οποίο είναι μια αποδοτική δομή δεδομένων
που χρησιμοποιείται για τον έλεγχο της ύπαρξης στοιχείων σε μια συλλογή με χαμηλό
κόστος μνήμης. Το bloom filter επιτρέπει ψευδώς ϑετικά αποτελέσματα, αλλά ποτέ
ψευδώς αρνητικά.
Περιγραφή
Ο κώδικας περιλαμβάνει:
• Μια συνάρτηση για τη δημιουργία του bloom filter.
• Μια συνάρτηση για την προσθήκη ψηφιακών υπογραφών.
• Μια συνάρτηση για τον έλεγχο ύπαρξης μιας ψηφιακής υπογραφής.
• Την κλάση bloom filter που υλοποιεί το φίλτρο.
Κύρια Συνάρτηση
Η συνάρτηση main() εκτελεί τα παρακάτω βήματα:
1. ∆ημιουργεί ένα bloom filter με μέγεθος 70,000 bits και 5 συναρτήσεις
κατακερματισμού.
2. Προσθέτει μια λίστα από κακόβουλες ψηφιακές υπογραφές στο bloom filter.
3. Ελέγχει αν η υπογραφή "mal_sig1" υπάρχει στο bloom filters και εμφανίζει το
αποτέλεσμα.
Αναμενόμενο Αποτέλεσμα:
Ο κώδικας ϑα εμφανίσει το μήνυμα: ¨Η ψηφιακή υπογραφή που ψάχνεις υπάρχει στη
βάση του bloom filters¨, καθώς η υπογραφή "mal_sig1" έχει προστεθεί στο bloom filters
και ϑα αναγνωριστεί ως υπαρκτή από τον έλεγχο.
