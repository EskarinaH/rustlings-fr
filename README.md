# rustlings 🦀❤️

Salutations et bienvenue sur le projet `rustlings` ! Il contient de petits exercices pour s'habituer à lire et écrire du code en Rust. Cela comprend le fait de lire les messages du compilateur et d'y répondre !

_...à la recherche de l'ancienne version de Rustlings, sous forme d'appli web ? Essayez [ici](https://github.com/rust-lang/rustlings/tree/rustlings-1)_

Alternativement, pour les personnes qui débutent en Rust, il y a plusieurs autres ressources :

- [The Book](https://doc.rust-lang.org/book/index.html) (en anglais) ou sa [traduction](https://jimskapt.github.io/rust-book-fr/) non officielle en français) - La ressource la plus complète pour apprendre Rust, mais parfois un peu théorique. Vous l'utiliserez en parallèle de Rustlings !
- [Rust By Example](https://doc.rust-lang.org/rust-by-example/index.html) (en anglais) - Apprenez Rust en résolvant de petits exercices ! C'est presque comme `rustlings`, mais en ligne.

## Pour commencer

_Note : Sur MacOS, assurez-vous d'avoir installé Xcode et ses "developer tools" avec cette commande : `xcode-select --install`._
_Note : Sur Linux, assurez-vous d'avoir installé gcc. Deb : `sudo apt install gcc`. Yum : `sudo yum -y install gcc`._

Vous aurez besoin d'avoir installé Rust. Vous pouvez l'obtenir sur la page https://rustup.rs. Cela installera aussi Cargo, le gestionnaire de paquets et de projets de Rust.

## MacOS/Linux

Executez les lignes suivantes :

```bash
curl -L https://raw.githubusercontent.com/EskarinaH/rustlings-fr/main/install.sh | bash
# Ou si vous voulez l'installer dans un autre répertoire :
curl -L https://raw.githubusercontent.com/EskarinaH/rustlings-fr/main/install.sh | bash -s mypath/
```

Cela va installer Rustlings et vous donner accès à la commande `rustlings`. Exécutez-là pour commencer !

## Windows

Dans PowerShell (exécuté en tant qu'administrateur), mettre `ExecutionPolicy` à `RemoteSigned` :

```ps1
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Ensuite, installer Rustlings :

```ps1
Start-BitsTransfer -Source https://raw.githubusercontent.com/EskarinaH/rustlings-fr/main/install.ps1 -Destination $env:TMP/install_rustlings.ps1; Unblock-File $env:TMP/install_rustlings.ps1; Invoke-Expression $env:TMP/install_rustlings.ps1
```

Comme pour MacOS/Linux, vous aurez ensuite accès à la commande `rustlings`.

Si vous obtenez le message "permission denied", vous devez configurer votre anti-virus pour exclure le répertoire où vous avez placé rustlings.

## Navigateur :

[Sur Repl.it](https://replit.com/github/EskarinaH/rustlings-fr)

[![Ouvrir dans Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/EskarinaH/rustlings-fr)

## Installation manuelle

Clonez le dépôt au niveau du dernier tag, puis exécutez `cargo install`. 

```bash
# Trouvez la dernière version sur https://github.com/EskarinaH/rustlings-fr/latest (4.7.1 au moment de l'édition de ce README.) 
git clone -b 4.7.1 --depth 1 https://github.com/EskarinaH/rustlings-fr
cd rustlings-fr
cargo install --force --path .
```

S'il y a des erreurs lors de l'installation, assurez-vous que votre toolchain est à jour. Pour cela, exécutez :

```bash
rustup update
```

Ensuite, comme plus haut, exécutez `rustlings` pour commencer.

## Faire les exercices

Les exercices sont triés par sujet et se trouvent dans le sous-dossier `rustlings/exercises/<sujet>`. Pour chaque sujet il y a un fichier README ("lisez-moi") supplémentaire avec des ressources pour démarrer sur le sujet. Nous recommandons vivement d'y jeter un œil avant de commencer.

Le principe est simple. La plupart des exercices contiennent une erreur qui les empêche de compiler, et c'est à vous de la réparer ! Certains exercices sont aussi exécutés comme des tests, mais rustlings les traite de la même façon. Pour faire les exercices dans l'ordre recommandé, exécutez :

```bash
rustlings watch
```

Cela va essayer de vérifier la résolution de chaque exercice dans un ordre prédéterminé (que nous pensons être le meilleur pour découvrir Rust.) Cela va aussi se ré-exécuter à chaque fois que vous changez un fichier dans le dossier `exercises/`. Si vous voulez l'exécuter une seule fois, vous pouvez utiliser :

```bash
rustlings verify
```

Cela va faire la même chose que `watch`, mais s'arrêter après une exécution.

Si vous voulez y aller dans un ordre de votre choix, ou si vous voulez vérifier un seul exercice, vous pouvez exécuter :

```bash
rustlings run myExercise1
```

Ou simplement utiliser la commande suivante pour exécuter le prochain exercice non résolu :

```bash
rustlings run next
```

Si vous bloquez sur un exercice, vous pouvez exécuter la commande suivante pour obtenir un indice :

```bash
rustlings hint myExercise1
```

Vous pouvez aussi obtenir l'indice pour le prochain exercice non résolu avec la commande suivante :

```bash
rustlings hint next
```

Pour vérifier votre progression, vous pouvez exécuter la commande suivante :

```bash
rustlings list
```

## Tester ses connaissances

Toutes les 2 ou 3 sections, `rustlings` vous propose un quiz pour tester vos connaissances sur plusieurs sections d'un coup. Ces quiz se trouvent dans `exercises/quizN.rs`.

## Activer `rust-analyzer`

`rust-analyzer` est supporté, mais la question de savoir s'il est activé par défaut dépend de votre éditeur. (RLS n'est pas supporté.)

Pour activer `rust-analyzer`, vous devrez dire à Cargo de compiler le projet avec la fonctionnalité `exercises`, ce qui inclura automatiquement le sous-dossier `exercises/` dans le projet. La façon la plus simple de faire cela est de dire à votre éditeur de compiler le projet avec toutes les fonctionnalités (l'équivalent de `cargo build --all-features`).
Voici les instructions spécifiques par éditeur :

- **VSCode**: Ajouter un fichier `.vscode/settings.json` avec la ligne suivante :
```json
{
    "rust-analyzer.cargo.features": ["exercises"]
}
```
- **IntelliJ-based Editors**: Avec le plugin Rust, tout devrait fonctionner par défaut.

- _Votre éditeur manque à l'appel ? N'hésitez pas à contribuer pour ajouter des instructions !_

## Pour continuer

Une fois que vous avez complété Rustlings, faites bon usage de vos nouvelles connaissances ! Continuez à vous exercer en Rust en créant vos propres projets, en contribuant à Rustlings, ou en trouvant d'autres projets Open-Source auxquels contribuer.

## Désinstaller Rustlings

Si vous voulez désinstaller Rustlings, il y a deux étapes. D'abord, retirez le dossier `exercises/` que le script d'installation a créé pour vous :

```bash
rm -rf rustlings # ou le nom personnalisé de votre dossier, si vous avez choisi de le renommer.
```

Ensuite, comme Rustlings a été installé via `cargo install`, il est tout à fait raisonnable de partir du principe que vous pouvez aussi le supprimer en utilisant Cargo, et c'est le cas. Exécutez `cargo uninstall` pour retirer le binaire `rustlings` :

```bash
cargo uninstall rustlings
```

C'est bon !

## Pour compléter

Rustlings n'est pas terminé ; plusieurs sections sont très expérimentales et n'ont pas de vraie documentation. Cela concerne entre autres :

- Errors (`exercises/errors/`)
- Option (`exercises/option/`)
- Result (`exercises/result/`)
- Move Semantics (pourrait encore être améliorée, `exercises/move_semantics/`)

De plus, des exercices sur certains sujets supplémentaires seraient utiles :

- Structs
- Des meilleurs exercices sur la possession (ownership)
- `impl`
- ??? probablement d'autres sujets

Si cela vous intéresse d'améliorer ou d'ajouter des exercices, n'hésitez pas à contribuer ! (De préférence sur le [site d'origine en anglais](https://github.com/rust-lang/rustlings). Lisez la suite pour plus d'informations :)

Si vous souhaitez compléter ou améliorer cette traduction, n'hésitez pas à ouvrir une issue ou une pull request sur ce dépôt :)

## Contribuer

Cf. [CONTRIBUTING.md](./CONTRIBUTING.md).

## Contributeurs ✨

Merci à tous les gens merveilleux listés dans [AUTHORS.md](./AUTHORS.md) 🎉
