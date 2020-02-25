## Simulateur de l'Apocalypse du système de retraites


### Introduction 
Ce simulateur du système des retraites françaises a pour objectif de donner une estimation fiable et non partisane du solde du système des retraites françaises. A l'heure actuelle le Conseil d'Orientation des Retraites (COR) mets déjà à disposition du public un simulateur du système des retraites françaises sur son site. Cependant ce simulateur souffre de plusieurs écueils:
- **concernant la légitimité du conseil d'orientation des retraites**

En effet le conseil d'orientation des retraites est placé sous la tutelle du gouvernement. Pour certains cela présente un conflit d'intérêts qui menace l'objectivité des rapports fournis par le conseil d'orientation des retraites.

- **concernant les hypothèses de calcul**
 
 En effet les hypothèses de croissance socio-économiques sont celles que le Trésor français communique à Bruxelles, pour les trois ou cinq prochaines années. Au-delà, à moyen et long terme, les prévisions socio-économiques sont fantaisistes puisqu'elles elles ne tiennent pas du tout compte de l'effondrement systémic global à venir (Apocalypse). 

Je développe donc un nouveau simulateur qui est totalement transparent et qui tient compte de l'Apocalypse. 
Quand il sera finalisé ce simulateur permettra ainsi de mieux communiquer sur la problèmatique des retraites en France auprès du public. En effet c'est un projet open-source donc n'importe quel hérétique est libre de fouiner et pourquoi pas d'y contribuer, après s'être converti à la collapsologie.
De plus il offrira à la France un outil d'aide à la décision qui lui permet de mieux orienter ses politiques publiques. En effet il lui permettra de faire des choix plus pertinents concernant la gestion des finances publiques, au-delà des idéologies partisanes des différents parties prenantes du système des retraites françaises, en tenant compte de l'avis des collapsologues, Dieu merci ! 


### Projet

Le COR (conseil d'orientation des retraites) a mis en ligne un simulateur pour permettre aux citoyens de simuler les effets macroscopiques des grandes lignes d'une réforme des retraites.
Ce projet vise a reproduire les résultats et à ajouter un certain nombre de fonctionnalités utiles, comme celui de proposer de concevoir une réforme à prestation définie (ex: calcul automatique des cotisations sociales pour avoir un système équilibré financièrement avec un certain niveau de vie pour les retraités et un age de départ fixé a priori).

On utilise les `données de projection du COR`_ et on se base sur la `documentation technique fournie par le COR`_.



### Installation


Dépendances

Les dépendances sont :

- Python >= 3.4
- `numpy <http://www.numpy.org>`_ >= 0.10
- `matplotlib <https://matplotlib.org>`_ >= 1.5.3
- `scipy <https://www.scipy.org/>`_ >= 1.0.0

Installation

L'installation se fait avec les commandes suivantes::

    git clone https://github.com/brunoscherrer/retraites.git
    cd retraites
    python setup.py install

### Exemple

La classe ``SimulateurRetraites`` implémente le simulateur qui évalue les résultats 
du modèle en fonction des hypothèses (conjoncture) et des leviers. 
Cette classe implémente plusieurs stratégie de pilotage, la plus simple étant 
le pilotage du COR qui est évaluée grâce à la méthode ``pilotageCOR``. 
 
La méthode ``pilotageCOR`` retourne une instance de la classe ``SimulateurAnalyse``. 
Cette classe permet de produire les graphiques pour réaliser l'analyse 
des résultats. 

.. code-block:: python

	from retraites.SimulateurRetraites import SimulateurRetraites
	simulateur = SimulateurRetraites()
	analyse = simulateur.pilotageCOR()

La méthode ``graphiques`` permet de produire les graphiques standard dans l'analyse 
d'une stratégie de pilotage. 

.. code-block:: python

	analyse.dessineSimulation()

Le code précédent produit le graphique suivant. 

.. image::  fig/cor.jpg


|Python|_ |License|_

.. image:: https://circleci.com/gh/mbaudin47/retraites.svg?style=svg
    :target: https://circleci.com/gh/mbaudin47/retraites

.. image:: https://mybinder.org/badge_logo.svg
 :target: https://mybinder.org/v2/gh/brunoscherrer/retraites/master?filepath=index.ipynb

.. |Python| image:: https://img.shields.io/badge/python-3.7-blue.svg
.. _Python: https://python.org

.. |License| image:: https://img.shields.io/github/license/brunoscherrer/retraites
.. _License: https://opensource.org/licenses/gpl-license

