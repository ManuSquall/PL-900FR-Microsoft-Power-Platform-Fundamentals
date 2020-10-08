---
lab:
    title: 'Labo�: Power BI'
    module: 'Module�5�: Premiers pas avec Power BI'
---

# Module�5 : Premiers pas avec Power BI
## Labo�: Power BI

Sc�nario
========

Bellows College est une organisation �ducative disposant de plusieurs b�timents sur le campus. Les visiteurs du campus sont actuellement enregistr�s dans des journaux papier. Les informations ne sont pas entr�es de mani�re coh�rente et il n�y a aucun moyen de collecter ni d�analyser les donn�es concernant les visites sur l�ensemble du campus. 

L�administration du campus souhaite moderniser son syst�me d�inscription des visiteurs o� l�acc�s aux b�timents est contr�l� par le personnel de s�curit� et toutes les visites doivent �tre pr�-enregistr�es et enregistr�es par leurs h�tes.

Tout au long de ce cours, vous cr�erez des applications et effectuerez une automatisation pour permettre au personnel administratif et de s�curit� du Bellows College de g�rer et de contr�ler l�acc�s aux b�timents du campus. 

Dans ce labo, vous allez cr�er un tableau de bord Power BI qui visualise les donn�es sur les visites sur le campus.

�tapes de labo de haut niveau
======================

Nous allons suivre les �tapes ci-dessous pour concevoir et cr�er le tableau de bord Power BI�:

-   Connectez-vous � Common Data Service 
-   Transformez les donn�es pour inclure des descriptions conviviales pour les enregistrements associ�s (recherches)
-   Cr�ez et publiez un rapport avec diverses visualisations des informations sur les visites du campus
-   Utilisez un langage naturel pour cr�er des visualisations suppl�mentaires
-   Cr�er un affichage mobile


## Conditions pr�alables

* Ach�vement du labo 1 - Mod�lisation de donn�es

�l�ments � consid�rer avant de commencer
-----------------------------------

-   � quel public ce rapport est-il destin�?
-   Comment les participants utiliseront-t-il le rapport�? Appareil courant�? Emplacement�?
-   Avez-vous suffisamment de donn�es � visualiser ?
-   Quelles sont les caract�ristiques qu�il est possible d�utiliser pour analyser les donn�es sur les visites ?

Exercice \#1�: Cr�er des rapports Power BI 
===============================

**Objectif�:** Dans cet exercice, vous allez cr�er un rapport Power BI bas� sur les donn�es de la base de donn�es Common Data Service.

T�che \#1�: Pr�parez les donn�es
---------------------------

1.  D�couvrez l�URL de votre organisation

    * Acc�dez au Centre d�administration Power Platform � l�adresse https://admin.powerplatform.com
    * Dans le volet de navigation de gauche, s�lectionnez Environnements, puis ouvrez l�environnement cible.
    * Cliquez avec le bouton droit sur **URL de l�environnement** dans le panneau **D�tails**, puis s�lectionnez **Copier l�adresse du lien**.
2. Si vous n�avez pas install� Power BI Desktop, acc�dez � https://aka.ms/pbidesktopstore pour t�l�charger et installer l�application Power BI.

3. Ouvrez Power BI Desktop et connectez-vous si vous y �tes invit�.

4. S�lectionnez ** Obtenir les donn�es**.

5. S�lectionnez **Power Plateform** sur la gauche, puis **Common Data Service** et appuyez sur **Connecter**.

6. Collez l�URL d�environnement que vous avez copi�e pr�c�demment dans le champ **URL du serveur** et appuyez sur **OK**.

7. D�veloppez le n�ud **Entit�s**, s�lectionnez les entit�s **bc_Building** et **bc_Visit** et cliquez sur **Charger**.

8. Cliquez sur l�ic�ne **Mod�le** dans la barre d�outils verticale de gauche.

9. Faites glisser la colonne **bc_buildingid** du tableau **bc_Building** et d�posez-la sur la colonne **bc_building** dans le tableau **bc_Visit**. Cela cr�era une relation entre deux entit�s que Power BI pourra utiliser pour afficher les donn�es associ�es.

10. S�lectionnez l�ic�ne **Rapport** dans la barre d�outils de gauche.

11. D�veloppez le n�ud **bc_Visits** dans le panneau **Champs**.

12. Cliquez sur les points de suspension (��...��) affich�s en regard de **bc_Visits** et s�lectionnez **Nouvelle colonne**.

13. Terminez la formule comme suit

    ```
    Column = RELATED(bc_Building[bc_name])
    ```

    Appuyez ensuite sur Entr�e. Cela ajoutera un nouveau champ avec le nom du b�timent dans les donn�es de visites.

14. Cliquez sur les points de suspension (��...��) affich�s en regard du champ et s�lectionnez **Renommer**. Saisissez **B�timent** comme nom de champ.

15. Cliquez sur les points de suspension (��...��) affich�s en regard du champ **bc_visitid** et s�lectionnez **Renommer**. Saisissez **Visites** comme nom de champ.

16. Cliquez sur ... � c�t� du champ **bc_scheduledstart** et s�lectionnez **Renommer**. Entrez **D�marrer** comme nom de champ.

17. Enregistrez le travail en cours en appuyant sur **Fichier \| Enregistrez** en saisissant le nom de fichier de votre choix.

## T�che n�2�: Cr�er un graphique et des visualisations temporelles

1. Appuyez sur l�ic�ne de graphique en secteurs dans le panneau **Visualisations** pour ins�rer le graphique.
2. Faites glisser le champ **B�timent** et d�posez-le dans la zone **L�gende**.
3. Faites glisser le champ **Visites** et d�posez-le dans la zone cible **Valeurs**.
4. Redimensionnez le graphique en secteurs � l�aide des poign�es d�angle afin que tous les composants du graphique soient visibles.
5. Cliquez sur **Nouveau visuel** sur le ruban Power�BI, puis s�lectionnez le graphique empil� dans le volet **Visualisations**. 
6. Faites glisser le champ **Visites** et d�posez-le dans la zone cible **Valeurs**.
7. Faites glisser le champ **D�but** et d�posez-le dans la zone cible **Axe**.
8. Dans le panneau Visualisations, cliquez sur le signe **X** affich� en regard de **Jour** et de **Trimestre** pour ne laisser que les totaux **Ann�e** et **Mois** pour l�Axe.
9. Redimensionnez le graphique selon les besoins, � l�aide des poign�es d�angle.
10. Testez l�interactivit� du rapport�:
    * S�lectionnez diff�rents secteurs sur le graphique en secteurs et observez les changements sur le rapport de temps.
    * S�lectionnez diverses barres sur l�histogramme empil� de temps et observez les changements sur le graphique en secteurs.
    * Proc�dez � un �clatement au niveau mensuel � l�aide d�ic�nes ou utilisez **Data/Drill \| D�veloppez le niveau de commande suivant** dans le ruban.
11. Enregistrez le travail en cours en appuyant sur **Fichier \| Enregistrez**.

Exercice n�2�: Cr�er un tableau de bord Power BI
================================

## T�che #1�: Publier un rapport Power BI

1. Appuyez sur le bouton **Publier**, sous l�onglet Accueil du ruban.

2. S�lectionnez **Mon espace de travail** comme destination, puis appuyez sur **S�lectionner**.

3. Attendez la fin de la publication et cliquez sur **Ouvrez \<nom de votre rapport \>.pbix dans Power BI**.

## T�che n�2�: Cr�er un tableau de bord Power BI

1. Sur la page web ouverte � l��tape pr�c�dente, cliquez sur **Mon espace de travail** dans la partie sup�rieure.
2. S�lectionnez votre **rapport** dans la liste des �l�ments.
3. S�lectionnez **�pingler une page dynamique** sur le menu. Selon la disposition, vous devrez peut-�tre appuyer sur ... pour afficher des �l�ments de menu suppl�mentaires.
4. S�lectionnez **Nouveau tableau de bord** sur l�invite **�pingler au tableau de bord**.
5. Entrez **Gestion du campus** comme un **Nom du tableau de bord** puis appuyez sur **�pingler un �l�ment dynamique**.
6. S�lectionnez **Mon espace de travail** dans la partie sup�rieure, puis s�lectionnez le tableau de bord **Gestion du campus**.
7. Testez l�interactivit� des graphiques en secteurs et � barres affich�s.

## T�che n�3�: Ajouter des visualisations � l�aide du langage naturel

1. Dans le tableau de bord **Gestion du campus**, s�lectionnez **Poser une question sur vos donn�es** dans la partie sup�rieure.
2. Entrez **b�timents par nombre de visites** dans la zone Questions et r�ponses. Le graphique � barres s�affiche.
3. S�lectionnez **�pingler un �l�ment visuel**.
4. S�lectionnez **Tableau de bord existant**, s�lectionnez le tableau de bord **Gestion du campus** puis appuyez sur **�pingler**.
5. Testez le comportement en cliquant sur le graphique pour acc�der aux questions et r�ponses.
6. Cliquez sur **Quitter le questionnaire**.

## T�che�n�4�: Cr�er une vue de t�l�phone mobile

1. Dans le tableau de bord, s�lectionnez... \| Vue mobile.
2. R�organisez les vignettes comme vous le souhaitez.
3. Cliquez sur **Affichage t�l�phone** en haut � droite et remplacez cet affichage par **Affichage web**.
4. S�lectionnez **Mon espace de travail** dans la partie sup�rieure, puis s�lectionnez votre **rapport**.
5. S�lectionnez�: \| G�n�rer un code QR.
6. Si vous avez un appareil mobile, scannez le code � l�aide d�une application de scanner QR disponible sur les plates-formes iOS et Android. Connectez-vous � votre compte si vous y �tes invit�.
7. Parcourez et d�couvrez le rapport sur un appareil mobile.

# D�fis

* Tableaux de bord et rapports pour inclure les plans du campus et des b�timents.
* Signaler et analyser les sch�mas et tendances des visites
* Visualisation des visites qui ont dur� trop longtemps
* Diffuser Power BI en continu pour le traitement en temps quasi r�el d�un grand campus 
