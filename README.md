# verstecke Szenen
Mit diesem Plugin könnt ihr Szenen verstecken.  
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


## Änderungen
### eingefügte variablen:
  **forumdisplay_thread**  
  ```<tr class="inline_row">```   
    ersetzt mit:   
  ```<tr class="inline_row" {$hiderow}>```
      
 ```<a href="{$thread['lastpostlink']}">{$lang->lastpost}</a>: {$lastposterlink}</span>```  
 ersetzt mit  
 ```{$hidewrap_start}<a href="{$thread['lastpostlink']}">{$lang->lastpost}</a>: {$lastposterlink}</span>{$hidewrap_end}```
  

### eingefügte Tabellenspalten
#### threads:
  **hidescene_readable** - int(1) NOT NULL DEFAULT 1  
    0: komplett verstecken  
    1: Szenentital/szeneninfos werden gezeigt  
    2: User darf entscheiden  
  
  **hidescene_type** - int(1) NOT NULL DEFAULT 1  
    0:komplett vestecken  
    1: Szenentital/szeneninfos werden gezeigt  

