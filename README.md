# LernberichtM183
# Lern-Bericht


## Einleitung

Bei diesem Projekt geht es darum, dass ich mir die Sicherheitslücke Direct Access, bei dem URLs nicht geschützt sind, angeschaut habe und dafür eine Lösung in Java gemacht habe.


## Was habe ich gelernt?

Ich habe gelernt, dass URLs nicht immer sicher sind und dass z.B. man als nicht eingeloggter User in geschützen Bereichen nur für Administrator gehen kann. Dafür habe ich eine passende Lösung gefunden. ich habe ein Filter hinzugefügt, das die URL kontrolliert.

## Beschreibung

Ich habe ein Filter erstellt, der für die Dateien /secured/* anwendbar ist. Ich habe ein Login Controller erstelltl. Dann habe ich in der Klasse doFilter den passenden Code geschrieben, so dass URL richtig verglichen werden.

```java
    public void doFilter(ServletRequest request, ServletResponse response,
            FilterChain chain)
            throws IOException, ServletException {
        
        final HttpServletRequest httpRequest = (HttpServletRequest) request;
        final HttpServletResponse httpResponse = (HttpServletResponse) response;
        final String loginURL = httpRequest.getContextPath() + "/index.xhtml";
        //vergleichung
        if (loginController.getUser() == null) {
            httpResponse.sendRedirect(loginURL);
        } 
        
        chain.doFilter(request, response); 
    }
```

* Eine textliche Beschreibung
* Ein deutliches, aussagekräftiges Bild oder eine kommentierte Bildschirm-Aufnahme
* Ein gut dokumentierter Code-Fetzen
* Ein Link zu einem *selbst aufgenommenen* youtube-Video oder `.gif`.

## Verifikation

✍️ Erklären Sie kurz und bündig, inwiefern die von Ihnen verwendeten Medien zeigen, was Sie gelernt haben.

# Reflektion zum Arbeitsprozess

👍 Überlegen Sie sich jeweils etwas, was gut an Ihrer Arbeit lief; 

👎 und etwas, was nicht gut lief.

**VBV**: ✍️ Formulieren Sie davon ausgehend einen *handelbaren* Verbesserungsvorschlag.
