# Pong AI Project - Unity Tutorial

## Inleiding

Welkom bij het Pong AI Project! Dit project is bedoeld als een leerervaring voor studenten die willen leren hoe ze AI kunnen implementeren in games, specifiek met behulp van de Unity-game-engine. We nemen de klassieke game "Pong" als basis en voegen AI toe voor de tegenstander, zodat je zowel een speler- als AI-gestuurd spel kunt bouwen. 

Dit project is ideaal voor beginners die vertrouwd willen raken met Unity, C#-scripting en de basisprincipes van game-AI.

## Doelstellingen van het project

In dit project leer je:
1. De basisbeginselen van Unity (scènes, objecten, componenten en physics).
2. Het opzetten van een klassieke Pong-game.
3. Hoe je een eenvoudige AI maakt die als tegenstander optreedt.
4. De balans tussen moeilijkheidsniveau en gameplay door middel van AI-aanpassingen.

## Vereisten

Voordat je begint, zorg ervoor dat je de volgende software en tools hebt geïnstalleerd:
- **Unity Hub** en de laatste versie van **Unity 3D**.
- **Visual Studio** of een andere C#-code-editor.
- Basiskennis van C# is aanbevolen maar niet strikt noodzakelijk.

## Projectstructuur

Hieronder volgt een overzicht van de belangrijkste onderdelen van dit project:

### 1. Scènes
- **MainScene**: Dit is de enige scène van de game waarin de volledige gameplay plaatsvindt. Hierin bevinden zich de bal, de twee paddles (de speler en de AI) en de scoreweergave.

### 2. Scripts
- **BallController.cs**: Regelt de beweging en botsingen van de bal in het spel.
- **PlayerController.cs**: Regelt de invoer van de speler voor het besturen van de paddle.
- **AIController.cs**: Regelt het gedrag van de AI-paddle en implementeert een eenvoudig algoritme om de bal te volgen.
- **GameManager.cs**: Beheert de algemene logica van het spel, zoals het bijhouden van de score en het resetten van de bal na een punt.

### 3. Prefabs
- **Paddle**: Een prefab voor de paddles, die zowel door de speler als door de AI gebruikt wordt.
- **Ball**: De prefab voor de bal die door beide paddles heen en weer geslagen wordt.

### 4. Physics
- De game maakt gebruik van Unity's 2D Physics-systeem om botsingen tussen de bal en de paddles af te handelen. 

## AI Logica

De AI in dit project volgt een eenvoudige strategie:
- Het probeert de positie van de bal te voorspellen en beweegt de paddle in de richting van de bal.
- De moeilijkheidsgraad kan aangepast worden door de reactiesnelheid of snelheid van de AI-paddle te verhogen of te verlagen.
- Voor beginners: de AI kan direct de Y-positie van de bal volgen.
- Voor gevorderden: je kunt proberen een meer geavanceerde AI te implementeren die rekening houdt met de snelheid van de bal en zijn toekomstige positie voorspelt.

**Voorbeeld van een eenvoudige AI-beweging:**

```csharp
public class AIController : MonoBehaviour
{
    public Transform ball; // Referentie naar de bal
    public float speed = 5f; // Snelheid van de paddle

    void Update()
    {
        // Paddle beweegt richting de Y-positie van de bal
        if (ball.position.y > transform.position.y)
        {
            transform.Translate(Vector2.up * speed * Time.deltaTime);
        }
        else if (ball.position.y < transform.position.y)
        {
            transform.Translate(Vector2.down * speed * Time.deltaTime);
        }
    }
}
```

## Aan de slag

1. **Clonen van het project**: 
   Download of clone de projectrepository naar je lokale machine.
   
2. **Openen in Unity**:
   - Open Unity Hub en voeg het project toe.
   - Start Unity en open het project.

3. **Scène configureren**:
   - Open `MainScene` in de Unity-editor.
   - Zorg ervoor dat de bal, paddles en scripts correct aan de objecten zijn gekoppeld.

4. **Spelen**:
   - Druk op de `Play`-knop in Unity om het spel te testen. Je kunt de AI tegen de speler laten spelen en aanpassingen maken aan de AI-logica.

## Uitbreidingen en uitdagingen

Om je verder te verdiepen in AI en game-ontwikkeling, kun je het project uitbreiden met de volgende ideeën:
- **Moeilijkheidsniveaus**: Pas de snelheid en reactietijd van de AI aan op basis van de score of een vooraf bepaalde moeilijkheidsgraad.
- **Voorspelling van balbaan**: Voeg meer complexiteit toe aan de AI door te berekenen waar de bal terecht zal komen in plaats van alleen de huidige positie van de bal te volgen.
- **Multiplayer**: Implementeer een lokale multiplayer-modus waarbij twee spelers tegen elkaar kunnen spelen.

## Conclusie

Dit Pong AI-project is een uitstekende introductie in het maken van een AI voor games in Unity. Door de AI te verbeteren en het spel uit te breiden, kun je je vaardigheden in zowel Unity als game-AI verder ontwikkelen. Veel succes en veel plezier!

## Auteur

Dit project is ontwikkeld door Dennis van Wakeren. Het is bedoeld als leerproject voor studenten en beginners in game-ontwikkeling. Voel je vrij om bij te dragen en verbeteringen aan te brengen!
