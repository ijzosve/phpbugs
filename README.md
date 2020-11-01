# phpbugs
- Je stockerai ici les bugs que j'ai rencontré et fixé à main propre. Le développement c'est la recherche de solutions contre tout type de problèmes. Quand on voit la finalité d'un script, on oublie la sémantique du programme, comment il a été unifié par l'auteur, et le temps de travail que ça a coûté. Demandez à Mark Zuckerberg, combien de bug il a rencontré quand il développait facebook en alternance, il en rigolera. 
## Bug n°1
```PHP
$a = isset($_GET['x']);
$a_unser = unserialize($a);
```
- Réponse <br/>
<img src="https://media.discordapp.net/attachments/772278494977196032/772279077495111680/unknown.png"/><br/>
**Notice: unserialize(): Error at offset 0 of 1 bytes in C:\wamp\www\izjosve\x.php on line 13**
### Solution
```PHP
if(isset($_GET['x'])){
  $a = $_GET['x'];
  $a_unser = unserialize($a);
}
```
