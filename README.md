# LINQDb
-Per prima cosa dobbiamo creare una cartella con il nome giusto\
-Poi dobbiamo aprire la cartella su visual studio code\
-Nel terminale scrivere 'dotnet new console'\
-Cliccare sul link che segue https://www.sqlitetutorial.net/sqlite-sample-database/ e scaricare il file per poi inserirlo nella cartella dove dobbiamo lavorare
![235087869-6c102804-fa96-4d1c-939b-7b4fe0c36987](https://user-images.githubusercontent.com/116791046/236850632-7c789f8c-c005-4710-a40f-c0bbc00725cc.png)

-Poi possiamo iniziare a scrivere il codice\
-Prima cosa ricordarsi di aggiungere 'using SQLite;'\
-Fondamentale aggiungere tramite il terminale la libreria che serve per il programma\
![235085335-e5c5da92-495e-462a-83e5-8345c106b4ea](https://user-images.githubusercontent.com/116791046/236850462-7671171d-d328-4d9b-b190-a7de7cf9ca18.png)

-Ora possiamo iniziare a scrivere il nostro codice\
-La riga di codice che permette di accedere a alla libreria è: 
###
    SQLiteConnection cn1 = new SQLiteConnection("chinook.db");
###
-Quella che ci permette di selezionare quello che vogliamo dal DB è:
###
    var tblArtist = cn1.Query<Artist>("select * from artists");
###
-Il comando che ci permette di ordinare gli ID degli artisti è:
###
    var temporanea = tblArtist.OrderByDescending(x => x.Name).Max( y => y.ArtistId );
###
-Poi facciamo un foreach (si passa tutti i record e scrive il nome), e poi stampiamo anche il numero di record che sono presenti:
###
    foreach(var record in tblArtist)
    {
        Console.WriteLine( $"{record.Name}" );
    }
    Console.WriteLine($"{temporanea}");
###

-Il rusultato finale dovrebbe essere simile a questo:\
![image](https://user-images.githubusercontent.com/116791046/236854125-4da88d4d-65a3-4655-8d51-cacb5ba07861.png)

-Il programma per ora termina in qui in caso di nuovi aggiornamenti al codice verranno inseriti qui.
