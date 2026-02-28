Dotfiles Management (Bare Repo Approach)
Diese Dotfiles werden über ein Bare Git Repository verwaltet. Das bedeutet, die Dateien liegen direkt im `$HOME`, aber die Git-Historie ist separat in `~/.dotfiles`.

Setup auf einem neuen Rechner

1. Alias temporär definieren: `alias dot='/usr/bin/git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME'`
2. Repo klonen: `git clone --bare  $HOME/.dotfiles`
3. Konfiguration setzen: `dot config --local status.showUntrackedFiles no`
4. Checkout (Achtung: evtl. vorhandene Dateien sichern): `dot checkout`

Tägliche Nutzung

• Status prüfen: `dot status`
• Datei hinzufügen: `dot add .zshrc`
• Speichern: `dot commit -m "Update"`
• Hochladen: `dot push`

Secrets

• Private Keys oder Tokens niemals adden!
• Nutze `~/.zsh_local` für lokale Secrets (ist in .gitignore).

