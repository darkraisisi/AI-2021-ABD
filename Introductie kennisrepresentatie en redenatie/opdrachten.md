# Opdracht 2.1

Door alleen in de eerste T werk/stappen te verichten die de performance verbeterd, alles wat daarna komt wordt niet meegerekend dus zou de agent niks kunnen doen.


# Opdracht 2.4

1. False - An agent that senses only partial information about the state cannot be perfectly rational.
    Het is onmogelijk voor een agent om alles van zijn omgeving te weten, ze acteren op het geen wat ze weten.
2. True - There exist task environments in which no pure reflex agent can behave rationally.
    Als er tegenstrijdige task gegeven worden, remmen als een auto voor je te dichtbij is/ gas geven als een auto achter je te dichtbij is dit zou allebij tegelijk kunnen gebeuren.
3. True - There exists a task environment in which every agent is rational.
    Bij hetzelfde voorbeeld zou je door penalty's toe te voegen voor botsen kunnen voorkomen dat een agent doorrijd ookal is hij te dichtbij.
4. False - The input to an agent program is the same as the input to the agent function.
    De informatie die een agent weerneemt is niet de enige informatie die hij tot zijn beschikking heeft.
5. False - Every agent function is implementable by some program/machine combination.
    Je kan ook agent based denken gebruiken in de echte wereld/ propositielogicha.
6. True - Suppose an agent selects its action uniformly at random from the set of possible actions. There exists a deterministic task environment in which this agent is rational.
    Dit zou je kunnen doen door een agent te hebben die maar 1 actie kan uitvoeren of door een enviroment te hebben waar elke actie die uitgevoerd wordt dezelfde score levert aan de agent.
7. It is possible for a given agent to be perfectly rational in two distinct task environments.
    ~
8. False - Every agent is rational in an unobservable environment.
    De gevolgen van een actie kunnen nog geevalueerd worden door de agents.
9. Fasle - A perfectly rational poker-playing agent never loses.
    Ook al maak je de beste zetten met de informatie die je hebt kan je nogsteeds verliezen omdat poker een element van willekeur heeft.


# Opdracht 13.8

Given the full joint distribution shown in Figure 13.3, calculate the following:
1. P(toothache).
2. P(Cavity).
3. P(Toothache AND cavity).
4. P(Cavity| toothache ∨ catch).

1. 
P(toothache) = 0.2

2. 
P(Catch) = 0.34

3. 
<!-- P(toothache|cavity) = P(ta) P(c|ta)     / P(ta) P(c|ta)     + P(¬ta) P(c|¬ta)
P(0.272~)           = P(0.2) P(0.108)   / P(0.2) P(0.108)   + P(0.8) P(0.072) -->
P(toothache AND cavity) = 0.12 = 0.108 + 0.012


4. 
P(Cavity|toothache ∨ catch) = P(cav) P(ta v cat | cav)  / P(cav) P(ta v cat | cav)  + P(¬cav) P(ta v cat | ¬cav)
P(0.000~)                   = P(0.2) P(0.192)           / P(0.2) P(0.192)           + P(0.8) P(ta v cat | ¬cav)


# Opdracht 14.3

After your yearly checkup, the doctor has bad news and good news. The bad news is that you tested positive for a serious disease, and that the test is 99% accurate (i.e., the probability of testing positive given that you have the disease is 0.99, as is the probability of testing negative given that you don't have the disease). The good news is that this is a rare disease, striking only one in 10,000 people. Why is it good news that the disease is rare? What are the chances that you actually have the disease

P(T) = 0.99
P(D) = 1/10000 = 0.0001
P(T|D) = 0.99
P(¬T|¬D) = 0.99
P(T|¬D) = 0.9999

P(D|T) = P(D) P(T|D) / P(T) = P(D) P(T|D) / ( P(D) P(T|D) + P(!D) P(T|!D) )
P(0.009804) = 0.99 * 0.0001 / 0.0001 * 0.99 + 0.0001 * 0.9999


# Opdracht 14.11

(Adapted from Pearl (1988).) You are a witness of a night-time hit-and-run accident involving a taxi in Athens. All taxis in Athens are blue or green. You swear, under oath, that the taxi was blue. Extensive testing shows that under the dim lighting conditions, discrimination between blue and green is 75% reliable. Is it possible to calculate the most likely color for the taxi? (Hint: distinguish carefully between the proposition that the taxi is blue and the proposition
that it appears blue.)

What now, given that 9 out of 10 Athenian taxis are green?

P(B) = 0.1 Blue taxi
P(S) = 0.75 Seen color, 100 zeker * 75% 
P(B|S) =  P(B) P(S|B)   / P(B) P(S|B)   + P(¬B) P(S|¬B)
P(B|S) =  0.1 * 0.75    / 0.1 * 0.75    + 0.9 * 0.25 = 0.75
Dus het is ondanks de verklaring nogsteeds aannemelijk dat het een groene taxi was.


# Wumpus opdracht

4 (kolommen) * 4 (rijen) wumpus wereld, origin links onder 1,1, startpositie speler 1,2.
Verder op fig. 13.5 en 13.6.
Al ontdekt: 1,1 1,2 2,1.
R = waarschijnlijkheden van de Rest.

Waarschijnlijkheid dat er op 1,3 een pit is.
P(p1,3 | R)     = P(p1,3) * P(R | p1,3)         , P(¬p1,3) * P(R | ¬p1,3)
P(0.072, 0.16)   = 0.2     * (0.04 + 0.16 + 0.16), 0.8      * (0.04 + 0.16)
P(0.31, 0.69)   = 0.072 / (0.072 + 0.16), 0.16 / (0.072 + 0.16)

Waarschijnlijkheid dat er op 2,2 een pit is.
P(p2,2 | R)     = P(p2,2) * P(R | p2,2)         , P(¬p2,2) * P(R | ¬p2,2)
P(0.2, 0.032)   = 0.2     * (0.04 + 0.16 + 0.16 + 0.64), 0.8      * (0.04)
P(0.862, 0.137)   = 0.2 / (0.2 + 0.032), 0.032 / (0.2 + 0.032)

Nu neemt de speler en stap naar boven naar 1,3.
Dit aan de hand van de kans dat er aan de zijkanten (31% kans) of in het midden(86% kans) een pit zit.
Bovenaan is inderdaad geen pit, en de speler zet nu nog een stap naar rechts (nu op 2,3 boven de vermoedde pit van 86,2% kans)
De speler voelt weer een BREEZE, met hoeveel zekerheid kunnen we nu zeggen dat die pit er echt zit op 2,2?

P(p2,2 | R)     = P(p2,2) * P(R | p2,2)                , P(¬p2,2)   * P(R | ¬p2,2)
P(0.862, 0.04932) = 0.862   * (0.04 + 0.16 + 0.16 + 0.64), 0.137      * (0.04 + 0.16 + 0.16)
P(0.945, 0.045)   = 0.862 / (0.862 + 0.04932), 0.04932 / (0.862 + 0.04932)

Nu door de Bayes rule nog eens toe te passen op onze hypothese is het mogelijk om nog zekerder te worden dat er daar een pit zit.