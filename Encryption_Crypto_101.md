Encryption Crypto 101

---------------------------------------------------------------------------------------------------------------------------------

Ciphertext - Le résultat du cryptage d'un texte en clair, des données cryptées

Chiffrement - Une méthode de chiffrement ou de déchiffrement des données. Les chiffrements modernes sont cryptographiques, mais il existe de nombreux chiffrements non cryptographiques comme César.

Texte clair - Données avant le cryptage, souvent du texte mais pas toujours. Peut-être une photo ou un autre fichier

Chiffrement - Transformation des données en texte chiffré, à l'aide d'un chiffrement.

Encodage - PAS une forme de cryptage, juste une forme de représentation de données comme base64. Immédiatement réversible.

Clé - Certaines informations nécessaires pour décrypter correctement le texte chiffré et obtenir le texte en clair.

Phrase secrète - Séparée de la clé, une phrase secrète est similaire à un mot de passe et utilisée pour protéger une clé.

Cryptage asymétrique - Utilise différentes clés pour crypter et décrypter.

Cryptage symétrique - Utilise la même clé pour crypter et décrypter

Brute force - Attaquer la cryptographie en essayant chaque mot de passe différent ou chaque clé différente

Cryptanalyse - Attaquer la cryptographie en trouvant une faiblesse dans les mathématiques sous-jacentes

---------------------------------------------------------------------------------------------------------------------------------

SSH = Secure shell 
On prouve son identité via un certificat 

Carte de Crédit utilile le standart PCI-DSS

Modulo = reste d'une division 

---------------------------------------------------------------------------------------------------------------------------------

Type de chiffrement: 
    symétrique : Chiffrement et déchiffrement avec la même clé 
        DES (ne pas utilisé) : Data Encryption Standard
            56 bits
        Triple DES
        AES : Advanced Encryption Standard
            128 ou 256 bit
    asymétrique: Chiffrement et déchiffrement avec deux clés différents 
        RSA : Rivest Shamir  Adleman
            outil pour cassé RSA https://github.com/Ganapati/RsaCtfTool  , https://github.com/ius/rsatool
            En savoir plus : https://muirlandoracle.co.uk/2020/01/29/rsa-encryption/ 
            Notion de clé public (a partagé ) et clé privé(ne surtout pas partagé ) 
            2048 à 4096 bit

---------------------------------------------------------------------------------------------------------------------------------

 Certicat est délivré par une autorité de Certification CA 
 Le certificat est signé.

 ---------------------------------------------------------------------------------------------------------------------------------

Brute force passphrase d'une clé rsa privé :
Avoir ssh2john version la plus récente  sur : https://github.com/openwall/john/blob/bleeding-jumbo/run/ssh2john.py 
Sur Kali /usr/share/john/ssh2john.py 
Utilisation /usr/share/john/ssh2john.py file_avec_clé_a_déchiffré > crack.txt
Ensuite john --wordlist /usr/share/wordlists/rockyou.txt crack.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (SSH [RSA/DSA/EC/OPENSSH (SSH private keys) 32/64])
Cost 1 (KDF/cipher [0=MD5/AES 1=MD5/3DES 2=Bcrypt/AES]) is 0 for all loaded hashes
Cost 2 (iteration count) is 1 for all loaded hashes
Will run 2 OpenMP threads
Note: This format may emit false positives, so it will keep trying even after
finding a possible candidate.
Press 'q' or Ctrl-C to abort, almost any other key for status
delicious        (Téléchargements/idrsa.id_rsa)                     <--------------------------------passphrase
1g 0:00:00:10 DONE (2021-04-12 23:01) 0.09487g/s 1360Kp/s 1360Kc/s 1360KC/sa6_123..*7¡Vamos!
Session completed

---------------------------------------------------------------------------------------------------------------------------------

Diffie Hellman Key Exchange:

Alice et Bob ont chacun une clé privé A et B 
Il existe une clé publique C 
Chacun va faire une association de ça clé priver avec la clé publique AC et AB 
Il s'envoie chacun ce bout de clé l'un a l'autre et y associe leur propre clé ils ont donc chacun une clé ABC 

---------------------------------------------------------------------------------------------------------------------------------

PGP (Pretty Good Privacy) : logiciel de chiffrement avec signature numérique.
GPG ou GnuPG : implémentation opensource de PGP via le projet GNU

Utilisation de gpg: 

root•~/Try_hack_me» gpg --import tryhackme.key message.gpg                                                                                                  [23:46:04]
gpg: clef FFA4B5252BAEB2E6 : « TryHackMe (Example Key) » n'est pas modifiée
gpg: clef FFA4B5252BAEB2E6 : clef secrète importée
gpg:       Quantité totale traitée : 1
gpg:                 non modifiées : 1
gpg:           clefs secrètes lues : 1
gpg:  clefs secrètes non modifiées : 1

root•~/Try_hack_me» gpg --decrypt  message.gpg                                                                                                              [23:49:11]
gpg: chiffré avec une clef RSA de 1024 bits, identifiant 2A0A5FDC5081B1C5, créée le 2020-06-30
      « TryHackMe (Example Key) »
You decrypted the file!
The secret word is Pineapple.


   
