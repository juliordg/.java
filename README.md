Para modelar as funções do iPhone como Reprodutor Musical, Aparelho Telefônico e Navegador na Internet usando UML e depois implementar em Java, podemos seguir os seguintes passos.

### Diagrama UML

```
+---------------------+
|      iPhone         |
+---------------------+
| -musicalPlayer: MusicalPlayer |
| -phone: Phone               |
| -browser: Browser           |
+---------------------+
| +playMusic()               |
| +makeCall()                |
| +browseInternet()          |
+---------------------+

+---------------------+
|   MusicalPlayer      |
+---------------------+
| -playlist: List<Song> |
+---------------------+
| +play()               |
| +pause()              |
| +addSong(Song song)  |
| +removeSong(Song song)|
+---------------------+

+---------------------+
|        Phone         |
+---------------------+
| -contacts: List<Contact> |
+---------------------+
| +call(Contact contact)   |
| +sendMessage(Contact contact, String message) |
+---------------------+

+---------------------+
|      Browser         |
+---------------------+
| -history: List<URL>  |
+---------------------+
| +navigate(URL url)   |
| +search(String query) |
+---------------------+

+---------------------+
|        Song          |
+---------------------+
| -title: String       |
| -artist: String      |
+---------------------+

+---------------------+
|       Contact        |
+---------------------+
| -name: String        |
| -phoneNumber: String |
+---------------------+
```

### Classes e Interfaces em Java

Agora, vamos implementar essas classes e interfaces em arquivos `.java`.

#### iPhone.java

```java
public class iPhone {
    private MusicalPlayer musicalPlayer;
    private Phone phone;
    private Browser browser;

    public iPhone() {
        musicalPlayer = new MusicalPlayer();
        phone = new Phone();
        browser = new Browser();
    }

    public void playMusic() {
        musicalPlayer.play();
    }

    public void makeCall(Contact contact) {
        phone.call(contact);
    }

    public void browseInternet(URL url) {
        browser.navigate(url);
    }
}
```

#### MusicalPlayer.java

```java
import java.util.ArrayList;
import java.util.List;

public class MusicalPlayer {
    private List<Song> playlist;

    public MusicalPlayer() {
        playlist = new ArrayList<>();
    }

    public void play() {
        System.out.println("Playing music...");
    }

    public void pause() {
        System.out.println("Music paused.");
    }

    public void addSong(Song song) {
        playlist.add(song);
    }

    public void removeSong(Song song) {
        playlist.remove(song);
    }
}
```

#### Phone.java

```java
import java.util.ArrayList;
import java.util.List;

public class Phone {
    private List<Contact> contacts;

    public Phone() {
        contacts = new ArrayList<>();
    }

    public void call(Contact contact) {
        System.out.println("Calling " + contact.getName() + "...");
    }

    public void sendMessage(Contact contact, String message) {
        System.out.println("Sending message to " + contact.getName() + ": " + message);
    }
}
```

#### Browser.java

```java
import java.util.ArrayList;
import java.util.List;

public class Browser {
    private List<URL> history;

    public Browser() {
        history = new ArrayList<>();
    }

    public void navigate(URL url) {
        history.add(url);
        System.out.println("Navigating to " + url.toString());
    }

    public void search(String query) {
        System.out.println("Searching for " + query);
    }
}
```

#### Song.java

```java
public class Song {
    private String title;
    private String artist;

    public Song(String title, String artist) {
        this.title = title;
        this.artist = artist;
    }

    public String getTitle() {
        return title;
    }

    public String getArtist() {
        return artist;
    }
}
```

#### Contact.java

```java
public class Contact {
    private String name;
    private String phoneNumber;

    public Contact(String name, String phoneNumber) {
        this.name = name;
        this.phoneNumber = phoneNumber;
    }

    public String getName() {
        return name;
    }

    public String getPhoneNumber() {
        return phoneNumber;
    }
}
```

### Considerações Finais

1. **Dependências**: As classes podem precisar de importações adicionais, como `java.net.URL` se estiver usando URL.
2. **Extensões**: Você pode adicionar mais funcionalidades ou métodos conforme necessário.
3. **Testes**: É importante criar testes para validar o comportamento das classes.

Esses códigos oferecem uma base sólida para modelar as funcionalidades do iPhone. Você pode expandir e adaptar conforme necessário!

# .java
dio
