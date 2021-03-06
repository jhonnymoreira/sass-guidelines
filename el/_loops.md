
# Loops

Επειδή η Sass παρέχει πολύπλοκες δομές δεδομένων όπως [lists](#lists) και [maps](#maps), δεν αποτελεί έκπληξη το γεγονός ότι δίνει επίσης τη δυνατότητα στους συγγραφείς να μπορούν να σαρώσουν τις εν λόγω οντότητες.

Ωστόσο, η παρουσία των loops συνήθως συνεπάγεται με σχετικά σύνθετη λογική που κατά πάσα πιθανότητα δεν ανήκει στην Sass. Πριν χρησιμοποιήσεις ένα loop, βεβαιώσου ότι έχει νόημα και ότι λύνει πραγματικά ένα πρόβλημα.

## Each

Από τα τρία loops που παρέχονται από τη Sass, το `@each` loop είναι σίγουρα αυτό που χρησιμοποιείται πιο συχνά. Παρέχει ένα καθαρό API για να μπορείς να σαρώσεις ένα list ή ένα map.

{% include snippets/loops/01/index.html %}

Οταν σαρώνεις ένα map, πρέπει πάντοτε να χρησιμοποιείς `$key` και `$value` ως ονόματα στις μεταβλητές για να υπάρχει συνοχή.

{% include snippets/loops/02/index.html %}

Επίσης, φρόντισε να σεβαστείς τα παρακάτω guidelines για τη διατήρηση της αναγνωσιμότητας:

* Να αφήνεις πάντα καινούργια γραμμή πριν το `@each`·
* Να αφήνεις πάντα καινούργια γραμμή μετά το δεξί άγκιστρο (`}`) εκτός και εαν η επόμενη γραμμή περιέχει δεξί άγκιστρο (`}`).

## For

Το `@for` loop μπορεί να φανεί χρήσιμο όταν συνδυάζεται με τις ψευδοκλάσεις της CSS’ `:nth-*`. Εκτός από αυτά τα σενάρια, να προτιμάς ένα `@each` loop αν *πρέπει* να σαρώσεις κάτι.

{% include snippets/loops/03/index.html %}

Να χρησιμοποιείς πάντα `$i` ως όνομα μεταβλητής για να διατηρήσεις τη συνήθη σύμβαση, και μην χρησιμοποιείς ποτέ την λέξη κλειδί `to`: πάντοτε να χρησιμοποιείς `through`, εκτός κι αν έχεις πραγματικά καλό λόγο. Πολλοί developers δεν γνωρίζουν καν ότι η Sass προσφέρει αυτή την παραλλαγή· με τη χρήση του ενδέχεται να προκαλέσει σύγχυση.

Επίσης, φρόντισε να σεβαστείς τα παρακάτω guidelines για τη διατήρηση της αναγνωσιμότητας:

* Να αφήνεις πάντα καινούργια γραμμή πριν το `@for`·
* Να αφήνεις πάντα καινούργια γραμμή μετα το δεξί άγκιστρο (`}`) εκτός και εαν η επόμενη γραμμή περιέχει το δεξί άγκιστρο (`}`).

## While

Το `@while` loop δεν έχει καμία απολύτως χρησιμότητα σε ένα πραγματικό Sass project, ιδίως επειδή δεν υπάρχει τρόπος να κάνεις break από το loop από μέσα. **Μην το χρησιμοποιήσεις**.
