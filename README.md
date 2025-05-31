Μάλιστα, κατάλαβα! Θες να φτιάξουμε ένα **επαγγελματικό και εντυπωσιακό README.md** για το **Steam Verifier** σου, με όλα τα καλά: εικόνα στο κέντρο, markdown `TIP`, `WARNING`, `CAUTION`, πίνακες λειτουργιών, clean δομή, emoji icons και ωραίο copywriting. Ορίστε ένα έτοιμο πρότυπο που **μοιάζει με του Cially** και είναι έτοιμο να το βάλεις στο repo:

---

<p align="center">
  <img src="https://github.com/user-attachments/assets/196fe635-3d81-46ae-92c3-f34296ce02c0" alt="Steam Verifier Banner"/>
</p>

# 🛡️ Steam Verifier

**Steam Verifier** είναι ένα ελαφρύ, open-source script για FiveM που εμποδίζει τους παίκτες να συνδεθούν εάν δεν έχουν ανοικτό το Steam. Χρησιμοποιεί το event `playerConnecting` και παρέχει ασφαλή, σταθερή εμπειρία στο server σου εξασφαλίζοντας ότι όλοι οι παίκτες είναι πιστοποιημένοι μέσω Steam.

Ιδανικό για roleplay servers, whitelist κοινότητες και οποιοδήποτε server απαιτεί αξιοπιστία στον έλεγχο ταυτότητας.

---

## ✨ Features

| ✅  | Περιγραφή                                              |
| -- | ------------------------------------------------------ |
| ✔️ | Ελέγχει εάν ο χρήστης έχει ανοίξει το Steam            |
| ✔️ | Αν δεν εντοπιστεί Steam, ο χρήστης γίνεται kick        |
| ✔️ | Πλήρως συμβατό με `playerConnecting` deferrals         |
| ✔️ | Προστασία από περίεργες συνδέσεις (src == nil)         |
| ✔️ | Καθαρά μηνύματα για τον χρήστη (`deferrals.done(...)`) |
| ✔️ | Εύκολη ενσωμάτωση σε κάθε FiveM server                 |
| ✔️ | Μικρό αποτύπωμα και μηδενική καθυστέρηση               |

---

## 🔧 How it works

Το script ενεργοποιείται στο event `playerConnecting`. Ελέγχει τις ταυτότητες του παίκτη για `steam:` ID. Εάν δεν εντοπιστεί, η σύνδεση απορρίπτεται με μήνυμα σφάλματος. Ιδανικό για servers που απαιτούν Steam verification χωρίς χρήση βάσεων δεδομένων ή περίπλοκων auth συστημάτων.

```lua
AddEventHandler('playerConnecting', function(name, setKickReason, deferrals)
    -- Ο πλήρης κώδικας βρίσκεται στο `steamCheck.lua`
end)
```

---

## 📦 Installation

1. Κατέβασε ή αντέγραψε το αρχείο `steamCheck.lua`.
2. Βεβαιώσου πως βρίσκεται σε φάκελο resource (π.χ. `/resources/[local]/steam-verifier/`).
3. Πρόσθεσε στο `fxmanifest.lua` ή `__resource.lua` του φακέλου:

```lua
fx_version 'cerulean'
game 'gta5'

author 'Kaloudas'
description 'Kick players who have not Steam open'
version '1.0.0'

server_script 'steamCheck.lua'
```

4. Ενεργοποίησε το resource στο `server.cfg`:

```cfg
ensure steam-verifier
```

---

> \[!TIP]
> Το Steam πρέπει να είναι ανοικτό ΠΡΙΝ ξεκινήσει το FiveM, αλλιώς ο παίκτης θα απορριφθεί.

> \[!WARNING]
> Αν ο παίκτης προσπαθήσει να μπει χωρίς Steam, θα δει μήνυμα “Steam must be running to join this server.”

> \[!CAUTION]
> Παίκτες που έχουν προσωρινά προβλήματα με Steam σύνδεση ενδέχεται να χρειαστεί να επανεκκινήσουν Steam + FiveM.

---

## 🧪 Example Output

```
Connection denied. Steam must be running to join this server.
```

---

## 🤝 Contributing

Pull requests για προσθήκες (π.χ. whitelist fallback, logs, debug mode κλπ) είναι ευπρόσδεκτες!

* Μην στέλνετε spam PRs ή αλλαγές που δεν σχετίζονται με τον σκοπό του script
* Για ιδέες ή feature requests, άνοιξε Issue πρώτα

---

## 📜 License

MIT License
Ελεύθερη χρήση, τροποποίηση και διανομή. Δες [LICENSE](./LICENSE) για λεπτομέρειες.

---

## 👤 Author

Created with ❤️ by [Kaloudas](https://github.com/kaloudas)
Αν σου άρεσε, άφησε ένα ⭐ στο repo!

---

Αν θες, μπορώ να το κάνω απευθείας export ως αρχείο `README.md` ή να σου το κάνω paste με έτοιμο banner σε GitHub-style format. Να σου βάλω και `.gif` για την εμπειρία σύνδεσης (Steam OFF vs ON);
