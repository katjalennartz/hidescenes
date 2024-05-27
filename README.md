# verstecke Szenen
Mit diesem Plugin können einzelne Szenen bewusst versteckt werden und so 'geheim' bleiben. Entweder können sie für alle 'nicht Teilnehmenden' komplett versteckt werden, oder sie nur nicht mehr lesbar gemacht werden. (Szeneninfos werden noch angezeigt).

    
## Kompatibel mit:
- Szenentracker von risuena
- Inplaytracker 2.0 von Jule
- Inplaytracker 3.0 von Jule

## Einstellungen
- Welcher Tracker wird verwenden?
- Gruppen die alle Szenen immer sehen kann
- Ingamebereich/Archiv
- Wie soll versteckt werden
  - Komplett
  - Die Szene kann nicht gelesen werden, Titel/Teilnemer und Szeneninfos werden gezeigt
  - Der User darf das pro Szene entscheiden


## Änderungen die das plugin vornimmt
### eingefügte variablen:
Die Variablen sollten eigentlich automatisch eingefügt werden, hat hier etwas nicht funktioniert, könnt ihr hier nachschauen was getan werden muss. 
  
    
  **forumdisplay_thread**  
  ```<tr class="inline_row">```   
    ersetzt mit:   
  ```<tr class="inline_row" {$hiderow}>```
      
 ```<a href="{$thread['lastpostlink']}">{$lang->lastpost}</a>: {$lastposterlink}</span>```  
 ersetzt mit  
 ```{$hidewrap_start}<a href="{$thread['lastpostlink']}">{$lang->lastpost}</a>: {$lastposterlink}</span>{$hidewrap_end}```
  
  
  ***search_results_threads_thread***   
  ```<tr class="inline_row">```   
    ersetzt mit:   
  ```<tr class="inline_row" {$hiderow}>```  
    
    
 ```<a href="{$thread['lastpostlink']}">{$lang->lastpost}</a>: {$lastposterlink}</span>```  
 ersetzt mit  
 ```{$hidewrap_start}<a href="{$thread['lastpostlink']}">{$lang->lastpost}</a>: {$lastposterlink}</span>{$hidewrap_end}```    
      
      
  ***newthread***   
  ```{$posticons}```   
  ersetzen mit  
 ```{$hidescenes_newthread}{$posticons} ```    
    
  ***member_profile***   
  ```{$footer}```   
  ersetzen mit  
   ```{$footer}{$hidescene_js} ```   
     
***member_profile_inplaytracker_bit***  

***Achtung, das ist nur beim IPT 2.0 nötig (dafür aber zwingend, damit das Javascript und das verstecken der Szenen funktioniert***
    ```class="trow1"```   
  ersetzen mit  
   ```class="trow1 ipt-jule"```   
   
  
### eingefügte Tabellenspalten
#### threads:
  **hidescene_readable** - int(1) NOT NULL DEFAULT 1  
    0: komplett verstecken  
    1: Szenentital/szeneninfos werden gezeigt  
    2: User darf entscheiden  
  
  **hidescene_type** - int(1) NOT NULL DEFAULT 1  
    0:komplett vestecken  
    1: Szenentital/szeneninfos werden gezeigt  

