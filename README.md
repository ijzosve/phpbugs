# phpbugs
- Je stockerai ici les bugs que j'ai rencontré et fixé à main propre
## Bug n°1
```PHP
$a = isset($_GET['x']);
$a_unser = unserialize($a);
```
- Réponse
<img src="https://media.discordapp.net/attachments/772278494977196032/772279077495111680/unknown.png"/><br/>
**Notice: unserialize(): Error at offset 0 of 1 bytes in C:\wamp\www\izjosve\x.php on line 13**
### Solution
```PHP
if(isset($_GET['x'])){
  $a = $_GET['x'];
  $a_unser = unserialize($a);
}
```
