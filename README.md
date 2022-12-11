# LernberichtM183
# Lern-Bericht


## Einleitung

Bei diesem Projekt geht es darum, dass ich mir die Sicherheitslücke Direct Access, bei dem URLs nicht geschützt sind, angeschaut habe und dafür eine Lösung in Java gemacht habe.


## Was habe ich gelernt?

Ich habe gelernt, dass URLs nicht immer sicher sind und dass z.B. man als nicht eingeloggter User in geschützen Bereichen nur für Administrator gehen kann. Dafür habe ich eine passende Lösung gefunden. ich habe ein Filter hinzugefügt, das die URL kontrolliert.

## Beschreibung

Ich habe ein Filter erstellt, der für die Dateien /secured/* anwendbar ist. Das habe ich gemacht, indem ich bei Filter Mappings die richtigen Dateien dann geschrieben habe. Ich habe ein Login Controller erstellt. Dann habe ich in der Methode doFilter den passenden Code geschrieben, so dass URL richtig verglichen werden.

```java
    @inject
    Login Controller loginController;

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

[Youtube Video Direct Access](https://youtu.be/S7qHKhebR3c)



## Verifikation

Mit der Beschreibung sieht man, wie ich den Filter erstellt habe und wie ich für die passende Dateien anwendar machte. 
Beim Code sieht man, wie ich das dann in der Methode umgesetzt habe.
Beim Youtube Video sieht man das Ergebnis, dass die URLs geschützt sind.

# Reflektion zum Arbeitsprozess

Es gab als Vorlage eine Filter Klasse mit der richtige Methode, sodass es für mich einfach war dieser Filter korrekt umzusetzten.
Auch die Klasse an sich zu erstellen war für mich kein grosser Aufwand, da ich das schon einmal benutzt habe. 
Es gabt keine grosse Schwierigkeiten bei diesem Projekt.


