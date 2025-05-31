Κατάλαβα! Παρακάτω το README με **μόνο τους τίτλους στα Αγγλικά** όπως ζήτησες, και το υπόλοιπο κείμενο στα Ελληνικά, πολύ σοβαρό και επαγγελματικό:

---

# 🛡️ Steam Verifier

Το **Steam Verifier** είναι ένα ελαφρύ, ανοιχτού κώδικα script για FiveM server, που επιβάλλει την ταυτοποίηση μέσω Steam, αποτρέποντας παίκτες από το να συνδεθούν αν δεν έχουν ενεργό client Steam. Χρησιμοποιώντας το event `playerConnecting`, εξασφαλίζει ασφαλές και αξιόπιστο περιβάλλον σύνδεσης για τον server σου, επιβεβαιώνοντας ότι όλοι οι χρήστες είναι πιστοποιημένοι μέσω Steam.

Ιδανικό για roleplay servers, whitelist κοινότητες, καθώς και οποιονδήποτε server απαιτεί αυστηρό έλεγχο ταυτότητας.

---

## ✨ Features

| ✅  | Περιγραφή                                                  |
| -- | ---------------------------------------------------------- |
| ✔️ | Ελέγχει αν ο παίκτης έχει ενεργή σύνδεση με Steam          |
| ✔️ | Κάνει kick τους παίκτες που δεν έχουν ανοιχτό Steam        |
| ✔️ | Πλήρης συμβατότητα με `playerConnecting` deferrals         |
| ✔️ | Αντιμετωπίζει μη έγκυρες συνδέσεις (π.χ. `src == nil`)     |
| ✔️ | Καθαρά και κατανοητά μηνύματα kick (`deferrals.done(...)`) |
| ✔️ | Εύκολη ενσωμάτωση σε οποιονδήποτε FiveM server             |
| ✔️ | Ελάχιστη χρήση πόρων και μηδενική επιβάρυνση στην απόδοση  |

---

## 🔧 How It Works

Το script ενεργοποιείται στο event `playerConnecting`. Ελέγχει τις ταυτότητες του παίκτη για το αναγνωριστικό `steam:`. Αν δεν εντοπιστεί, η σύνδεση απορρίπτεται με σαφές μήνυμα.

Η λύση αυτή δεν απαιτεί βάσεις δεδομένων ή περίπλοκα συστήματα αυθεντικοποίησης, προσφέροντας έναν απλό αλλά αποτελεσματικό τρόπο επιβολής Steam-only συνδέσεων.

```lua
AddEventHandler('playerConnecting', function(name, setKickReason, deferrals)
    -- Ο πλήρης κώδικας βρίσκεται στο `steamCheck.lua`
end)
```

---

## 📦 Installation

1. Κατέβασε ή αντιγράψε το αρχείο `steamCheck.lua`.
2. Τοποθέτησέ το σε φάκελο resource, π.χ. `/resources/[local]/steam-verifier/`.
3. Πρόσθεσε το παρακάτω στο αρχείο `fxmanifest.lua` του φακέλου:

```lua
fx_version 'cerulean'
game 'gta5'

author 'Kaloudas'
description 'Resource που αποβάλλει παίκτες χωρίς ενεργό Steam'
version '1.0.0'

server_script 'steamCheck.lua'
```

4. Ενεργοποίησε το resource στο `server.cfg`:

```cfg
ensure steam-verifier
```

---

> **Tip:**
> Ο Steam client **πρέπει να είναι ανοιχτός πριν την εκκίνηση του FiveM**, διαφορετικά η σύνδεση του παίκτη θα απορριφθεί.

> **Warning:**
> Οι παίκτες που προσπαθούν να μπουν χωρίς ανοιχτό Steam θα δουν το μήνυμα:
> *“Steam must be running to join this server.”*

> **Caution:**
> Σε περιπτώσεις προσωρινών προβλημάτων σύνδεσης με Steam, ίσως χρειαστεί επανεκκίνηση Steam και FiveM.

---

## 🧪 Example Kick Message

```
Connection denied. Steam must be running to join this server.
```

---
