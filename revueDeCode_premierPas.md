# Une première revue de code

*Formulaire permettant de sensibiliser à la notion de revue de code en s'appuyant sur les notions étudiées dans les modules de [conception objet (M2104)](https://github.com/iblasquez/enseignement-iut-m2104-conception) et [conception objet avancée (M3105)](https://github.com/iblasquez/enseignement-iut-m3105-conception-avancee)*

- [1. Premières impressions (M2104-M3105)](#premieresImpressions) 
- [2. Zoom sur les règles de simplicité (Rules of simple Design (M2104))](#reglesSimplicite)
- [3. Zoom sur la simplicité YAGNI / KISS : Eviter l'over engineering (M2104)](#KISS)
- [4. Zoom sur les cas limites (M2104 – M3301 – M3105)](#casLimites)
- [5. Zoom sur un logiciel opérationnel (minimum) (M3301 : MVP)](#mvp)
- [6. Zoom sur les principes SOLID (M3105)](#SOLID)
- [7. Zoom sur d’éventuels design patterns (M3105)](#pattern)
- [8. Bilan](#bilan)




<!-- 
https://github.com/StylishThemes/GitHub-Dark/wiki/Emoji  
https://gist.github.com/rxaviers/7360908 -->

## 1. Premières impressions (M2104-M3105) <a id="premieresImpressions"></a>

**Jetez un *petit coup d’œil rapide* au code devant vous, puis répondez aux questions suivantes…**

**Le code a-t-il été écrit ?**
  
:black_square_button: Anglais  
:black_square_button: Français  
:black_square_button: Franglais      


**Y a-t-il des tests qui couvrent le code ?**  
:black_square_button: Oui  
:black_square_button: Non 
   
*Si oui :*   
Combien de tests ont été écrits ? _______  
Combien de tests passent AU VERT ?   _______  
Quelle est le % de couverture de code ? _______

*Si oui*, pensez-vous que les tests ont été écrits :  
:black_square_button: A priori (via un cycle de développement TDD)   
:black_square_button: A posteriori (une fois le code de production écrit)   


**Le programme est-il fonctionnel ?**    
:black_square_button: Oui  
:black_square_button: Non 
  
*Si oui*, que peut-on faire avec ?  ______________________________



**Le code a-t-il été versionné (git) ?**  
:black_square_button: Oui  
:black_square_button: Non 

*Si oui*, combien de commits ont été réalisés ? _______



**De combien de fichiers (classes), le code est-il composé ?** _______

**Combien de lignes de code ont été écrites ?** _______




***Explorez maintenant un petit plus précisément le code à revoir en répondant aux questions suivantes***


##2. Zoom sur les règles de simplicité (Rules of simple Design (M2104)) <a id="reglesSimplicite"></a>


###2.1. Tous les tests passent   

**Si des tests ont été écrits, est-ce qu’ils passent TOUS AU VERT ?**  
:black_square_button: Oui  
:black_square_button: Non   

###2.2. Révéler l'intention du code  

 
**Retrouve-t-on la terminologie métier en lisant le code ?**  
:black_square_button: Oui    
:black_square_button: Non  
   
*Si non*, expliquez :_______


**Les classes sont-elles bien nommées ?**  
:black_square_button: Oui    
:black_square_button: Non  
   
*Si non*, expliquez :_______


**Les méthodes sont-elles bien nommées ?**  
:black_square_button: Oui    
:black_square_button: Non  
   
*Si non*, expliquez :_______


**Les variables sont-elles bien nommées ?**  
:black_square_button: Oui    
:black_square_button: Non  
   
*Si non*, expliquez :_______


**Le code est-il consistant ?**   
Par exemple : si le camelCase est utilisé pour nommer les méthodes, le camelCase est utilisé partout, si le nommage est du snake_case (avec des underscores), le snake_case partout, mais pas de une fois camelCase, une fois snake_case    
:black_square_button: Oui    
:black_square_button: Non  
   
*Si non*, expliquez :_______


**Le code est-il correctement indenté/formaté ?**  
:black_square_button: Oui    
:black_square_button: Non  
   
*Si non*, expliquez :_______


###2.3. Pas de duplication: DRY (Don't Repeat Yourself)
   
**Y-a-t-il de la duplication dans le code ?**  
:black_square_button: Oui    
:black_square_button: Non  
   

*Si oui*, expliquez où se situe la duplication, ce qu’elle concerne dans le code :_______


###2.4. Le plus petit nombre d'éléments (réduction de la complexité)

**Combien de classes ?** _______


**Que pensez-vous de la taille des classes ? (nombre de méthodes par classe)** _______


**Que pensez-vous de la taille des méthodes (nombre de lignes de code) ?** _______   


**Y-a-t-il des méthodes de plus de 20 lignes ?**  
:black_square_button: Oui    
:black_square_button: Non  


**Que pensez-vous de la complexité cyclomatique des méthodes (c-a-d nb de niveaux imbriqués)** _______

**Voyez-vous des méthodes avec une trop grande complexité cyclomatique (c-a-d des méthodes où des extract method auraient pu améliorer la lisibilité du code de ces méthodes)**  
:black_square_button: Oui    
:black_square_button: Non  
 
*Si oui*, indiquez lesquelles : _______ 



##3. Zoom sur la simplicité YAGNI / KISS : Eviter l'over engineering 😉 (M2104) <a id="KISS"></a>

**Y-a-t-il des choses dans le code qui ont été implémentées mais qui ne sont pas utilisées ?**  
(comme un attribut `taille` pour le robot, des getteurs et setteurs que l'on n’utilise pas dans le code déjà écrit, etc)    
:black_square_button: Oui    
:black_square_button: Non  

*Si oui*, indiquez ce que vous pensez avoir détecté comme over engineering dans l’état actuel 
du code :  _______ 



##4. Zoom sur les cas limites (M2104 – M3301 – M3105) <a id="casLimites"></a>

**Les cas limites techniques ont-ils été implémentés ?**   
(Débordement, ... , déclenchement d’exception,...)  

:black_square_button: Oui    
:black_square_button: Non 
 
*Si non*, expliquez :  _______ 

**Les cas limites fonctionnels ont-ils été traités ?**   
*Et oui, la planète mars est ronde !!! Attention aux exceptions et bordure.   
Si on est en (0,0) vers l’ouest et on avance de 1, on doit se trouver sur une case de la grille (laquelle ?) et surtout ne pas avoir un null pointer !!! En effet, on ne peut pas se permettre de perdre notre robot sur Mars, juste parce que les développeurs ont négligé un pointeur null*  

:black_square_button: Oui    
:black_square_button: Non  
   
*Si non*, expliquez : _______ 



**Voyez-vous un ou plusieurs cas limites qui n’ont pas été implémentés (et auraient dû l'être) ?**  
:black_square_button: Oui    
:black_square_button: Non   
    
*Si oui*, indiquez lesquels :  _______ 


##5. Zoom sur un logiciel opérationnel (minimum) (M3301 : MVP) <a id="mvp"></a>


**Le code écrit est-il opérationnel (utilisable, fonctionne-t-il) ?**  
:black_square_button: Oui    
:black_square_button: Non   


**La détection d’obstacle a-t-elle été implémentée ?**  
:black_square_button: Oui    
:black_square_button: Non  


##6. Zoom sur les principes SOLID (M3105) <a id="SOLID"></a>


###6.1. Principe SRP (Single Responsibility Principle : Principe de Responsabilité Unique)
   
**Le principe SRP vous parait-il toujours respecté ?**  
:black_square_button: Oui    
:black_square_button: Non   

**Si non,** indiquez le(s) endroit(s) dans le code où vous pensez que ce principe n'est pas respecté : _______ 



###6.2. Principe OCP (Open Closed Principle : Principe Ouvert/Fermé)
   
**Le principe OCP vous parait-il toujours respecté ?**  
:black_square_button: Oui    
:black_square_button: Non   

**Si non,** indiquez le(s) endroit(s) dans le code où vous pensez que ce principe n'est pas respecté : _______   



###6.3. Principe LSP (Liskov Substitution Principle : Principe de substitution de Liskov)
   
**Le principe LSP vous parait-il toujours respecté ?**  
:black_square_button: Oui    
:black_square_button: Non   

**Si non,** indiquez le(s) endroit(s) dans le code où vous pensez que ce principe n'est pas respecté : _______   


###6.4. Principe ISP (Interface Segregation Principle : Principe de ségrégation des interfaces)
   
**Le principe ISP vous parait-il toujours respecté ?**  
:black_square_button: Oui    
:black_square_button: Non   

**Si non,** indiquez le(s) endroit(s) dans le code où vous pensez que ce principe n'est pas respecté : _______  
 
 
###6.5. Principe DIP (Dependency Inversion Principle : Principe d’inversion de dépendances)
   
**Le principe DIP vous parait-il toujours respecté ?**  
:black_square_button: Oui    
:black_square_button: Non    

**Si non,** indiquez le(s) endroit(s) dans le code où vous pensez que ce principe n'est pas respecté : _______ 


##7. Zoom sur d’éventuels design patterns (M3105) <a id="pattern"></a>  

Si vous pensez qu'à certains endroits du code, certains patterns auraient pu être utilisés, n’hésitez pas à le faire remarquer et indiquez au travers de suggestions/conseils le(s) endroit(s) dans le code où vous pensez que ce(s) éventuel(s) pattern(s) pourrai(en)t être implémenté(s)



##8. Bilan <a id="bilan"></a>  

Rédigez ci-après un bilan de votre revue de code suite à votre lecture du code et aux remarques que vous a inspiré ce code (remarques venues en remplissant la fiche précédente et/ou en tenant compte de vos propres impressions/réactions face à ce code).
La revue de code devra faire remonter les bad smells que vous avez identifiés dans le code au travers de remarques bienveillantes accompagnées de conseils/suggestions d'amélioration pour que le(s) auteur(s) de ce code puisse(nt) l'améliorer


##En fin de séance    
 
Rubrique à compléter par le(s) auteur(s) du code, pas ceux qui font la revue  
  
**Avez-vous utilisé le TDD pour développer ce bout de code ?**  
:black_square_button: Oui    
:black_square_button: Non   


**Est-ce que la revue de code qui vous a été faite vous a permis d'améliorer votre code**  
:black_square_button: Oui    
:black_square_button: Non    


**Justifiez en quoi cette revue de code vous a permis d'améliorer ou pas votre code :** _______ 



**Indiquez également quelles ont été les premières modifications que vous avez effectué dans votre code suite aux remarques/conseils de cette revue :** _______ 




